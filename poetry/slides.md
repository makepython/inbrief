# Poetry
## Stefano Borini - Aug 2019

---

# What is it?

Python utility. Administers virtual environments, dependency download and installation, and building of python packages.

---

# Glossary

- __virtual environment__: technique to create a self-contained, fully
separated python executable with installed packages. This way your project A
does not pollute project B.

---

# Who needs it?

Python developers. Python packagers. DevOps for Continuous Integration.

---

# Why do I need it?

- Makes your life _much_ easier in handling your development environment.
- Ensure reproducible and self-contained python environment.
- Provides also a solution to build your package.

---

# Similar previous technologies

- venv and pip: not obsoleted. poetry is a meta-tool
- pipenv: very similar, but of the two Poetry seem to be better.

---

# Supported platforms

All platforms

---

# Main Features

One stop solution for your packaging needs.

- Creates and manages virtual environments
- Install dependencies and subdependencies
- Fast!
- Also a package builder. Supports new standard pyproject.toml.

---

# Killer feature

Clean, fast, well documented, one-stop solution.

---

# Drawbacks

- Still young but quickly improving.
- Build has no support for C extension. Only pure python wheels. Use setuptools in case.

---

# Ease of use

- Installation with ``pip install poetry``
- Excellent command line help.
- Quick and easy start with ``poetry init``

---

# Alternatives 

- Pipenv
- the "old way": venv, pip, distutils, setuptools, requirements.txt

# False alternatives

- pyinstaller

---

# Similarities to Pipenv

Pipenv:
- very opinionated
- Poor community support
- Slow, occasionally broken dependency resolution.
- No build, only env management
- No support for pyproject.toml

---

# Similarities to "the old way"

- The "old way" uses venv, pip, setuptools, requirements.txt
  - Well established but clunky and hard to understand
  - Setuptools dependency

---

# False alternative "pyinstaller"

  - not for package/dependency management.
  - Targets the need to create a final executable (".exe")

---

# Price and license

Free. MIT license.

---

# Brief example (max 3 slides)

A real case example (e.g. configuration file, or real world scenario on how to use it)

---

# Links

Relevant links to know more.
