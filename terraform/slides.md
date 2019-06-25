# Terraform
## Stefano Borini
### 2019-06-20

---

# What is it?

Command line tool to "script" deployment and configuration of machines on 
different cloud providers, such as heroku or AWS.

---

# Who needs it?

DevOps and infrastructure engineers that need to deploy network services in production.

---

# Why do I need it?

FIXME HERE
define resource, module, providers.

---

# Similar previous technologies


---

# Supported platforms

Runs on Linux, windows and macOS.

---

# Glossary

Provider: a terraform plugin, generally responsible for addressing a specific service provider (such as Amazon AWS)
Resource: anything that a service provider can deliver and terraform can therefore manage (e.g. a virtual machine providing a database)

---

# Ease of use

---

# Main Features

- define a desired state in the file. terraform comes up with a plan to migrate the current state to the requested state.
- handles resource dependencies.


---

# Killer feature

- Allows to abstract away the virtual machine provider.

---

# Alternatives

- AWS?

---

# Similarities to AWS

To be filled. Not very expert with AWS.

---

# Price and license

Price: Free. License: MIT. 

---

# Brief example


```
variable "region" {
    default = "eu"
}

provider "heroku" {
    email = "your heroku email"
    api_key = "your heroku api key"
}

resource "heroku_app" "arbitrary_name" {
  name   = "random-name-for-my-cool-app"
  region = "${var.region}"
}

output "whatever2" {
    value = "${var.foo}"
}
```

---

# Brief example

```
```

---

# Links

Relevant links to know more.
