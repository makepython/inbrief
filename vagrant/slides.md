# Vagrant
## Stefano Borini
### 2019-06-15

---

# What is it?

Command line tool to "script" virtual machine control.
Start, control and configure multiple virtual machines across multiple virtual
machine "providers" (e.g. VirtualBox, VMWare, Docker)

Provider: The entity providing the actual virtual machine functionality (e.g. virtualbox, docker) 


---

# Who needs it?

Anyone who needs to configure and control virtual machines with a known
configuration: DevOps engineers, Developers, possibly IT.

---

# Why do I need it?

Simplify administration and setup of virtual machines with a well defined configuration, e.g.
- run tests for continuous integration on various linux distros and operating systems.
- control VM clusters.

---

# Similar previous technologies

Manual creation and curation of virtual machines, using incompatible providers.

---

# Supported platforms

Runs on Linux, windows and macOS.
OS for the virtual machines depends on the provider.

---

# Ease of use

- Trivial to install.
- Requires a virtual machine provider to be installed as well (e.g. virtualbox)
- Usage requires basic understanding of Ruby for Vagrantfiles.

---

# Main Features

- Supports setup of virtual machines in a repeatable way.
- Allows for easy scriptability of the control and configuration of multiple machines at once.
- Has basic provisioner, as well as interface with more flexible systems (Salt, Puppet, Chef, Ansible)


Provisioning: automated phase that installs software for your specific use case once a machine is created.


---

# Killer feature

- Allows to abstract away the virtual machine provider.

---

# Alternatives

- AWS?

# False alternatives

---

# Similarities to AWS

To be filled. Not very expert with AWS.

---

# Price and license

Price: Free. License: MIT. 

---

# Brief example

Create a new virtualbox machine running ubuntu.
```
vagrant init ubuntu/trusty64
vagrant up
```
These commands create a basic Vagrantfile, download the OS image from a remote, create the VirtualBox VM, and start it.

---

# Brief example

```
Vagrant.configure("2") do |config|
  config.vm.define "node-1" do |node|
    node.vm.box = "ubuntu/trusty64"
  end 

  config.vm.define "node-2" do |node|
    node.vm.box = "ubuntu/trusty64"
  end 
end
```

This Vagrantfile configures two headless, basic machines (node-1 and node-2) with ubuntu Trusty.
The image "ubuntu/trusty64" is downloaded from the "Vagrant Box" repository.
``vagrant up`` will start these machines. ``vagrant halt`` will stop them.

---

# Links

Relevant links to know more.
