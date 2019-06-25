# Airflow
## Stefano Borini
## 2019-06-25

---

# What is it?

Python focused system to schedule and execute jobs organised as a graph of
tasks.  Each task must be self-contained. 

---

# Who needs it?

Whoever needs a system to schedule data process to perform at 
regular intervals.

---

# Why do I need it?

- Organises the queue of requests neatly
- Allows description of complex graphs of tasks.
- Has both web and cli interface.

---

# Similar previous technologies

Queuing systems: similar in concept however they don't do scheduling
cron: scheduling system however has no queues.
celery: asynchronous execution but that's it.
make: dependencies of execution between entities.

---

# Supported platforms

Linux, OSX. Windows?

---

# Glossary (optional)

- DAG: Direct Acyclic Graph: a specific set of tasks, connected to each other by dependencies.
- Operator: The "abstract" task. It can perform some operation (e.g. start a bash script).
- Task: An actual instance of the operator that runs and performs what it is supposed to do.

---

# Main Features

- Allows scheduling of well-defined DAGs at specific intervals.
- DAG definitions in compact, declarative python.
- Very focused on time series.
- Nice web interface to keep track of the execution.
- Compatibility with various backends for database

---

# Killer feature

A great feature that only this Thing offers compared to the competition,
or one feature that Thing does really well.

---

# Drawbacks

- Not made for real-time processing:
  - Designed for scheduling in the order of minutes.
  - Designed for complex, long running DAGs.

---

# Ease of use

Easy to install in basic form. 

```
pip install airflow
```

Out of the box comes with basic examples and sqlite backend.
Support additional databases with python optional install syntax.

---

# Alternatives 

- Some AWS stuff?

---

# Price and license


Free. Apache License.

---

# Brief example: DAG file - 1

```python
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from datetime import datetime, timedelta


default_args = {
    'owner': 'airflow',
    'depends_on_past': False,
    'start_date': datetime(2015, 6, 1),
    'email': ['airflow@example.com'],
    'email_on_failure': False,
    'email_on_retry': False,
    'retries': 1,
    'retry_delay': timedelta(minutes=5),
}
```

---

# Brief example: DAG file - 2

```python

dag = DAG('tutorial', default_args=default_args, schedule_interval=timedelta(days=1))

t1 = BashOperator(task_id='print_date', bash_command='date', dag=dag)
t2 = BashOperator(task_id='sleep', bash_command='sleep 5', retries=3, dag=dag)

templated_command = """
    {% for i in range(5) %}
        echo "{{ ds }}"
        echo "{{ macros.ds_add(ds, 7)}}"
        echo "{{ params.my_param }}"
    {% endfor %}
"""

t3 = BashOperator(task_id='templated', bash_command=templated_command,
                  params={'my_param': 'Parameter I passed in'}, dag=dag)

t2.set_upstream(t1)
t3.set_upstream(t1)
```

---

# Links

https://apache.airflow.com
