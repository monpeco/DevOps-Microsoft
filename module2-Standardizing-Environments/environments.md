### Learning Objectives
After completing this module, you will be able to:

* Describe why configuration management should be used in a DevOps culture and how it can improve the delivery of value to customers.
* Identify an infrastructure as code (IaC) strategy and a configuration as code strategy.
* Explain how to use infrastructure as code to standardize your environment deployments, and how to use configuration as code to standardize environment configuration.
* Differentiate how environments differ across infrastructure as a service (IaaS), platform as a service (PaaS), and containers.
* Identify Microsoft tools that you can use to support configuration management.

---

#### Standardizing Environments   Deployment and Configuration   Configuration Management

### Configuration Management

Configuration management is the management of the configuration of all environments for an application. Typically, configuration management is done in the form of scripts that are version controlled. Here are some key characteristics:

* Configuration management in the DevOps world is less formal than traditional configuration management.

* It emphasizes encapsulation of configuration in code over formal documentation.

* It means lighter weight, executable configurations that allow us to have configuration and environments as code.

Both Infrastructure as Code (IaC) and configuration as code fall under configuration management, and both relate to defining or scripting for environments:

* **Infrastructure as Code**. IaC entails defining environments, including networks, servers, and other compute resources, as a text file (script or definition) that is checked into version control and used as the base source for creating or updating those environments. For instance, adding a new server should be done by editing a text file and running the release pipeline, not by remoting into the environment and spinning up one manually.

* **Configuration as code**. In this approach, you define the configuration of your servers, code, and other resources as a text file (script or definition) that is checked into version control and used as the base source for creating or updating those configurations. For instance, adding a new port to a firewall should be done by editing a text file and running the release pipeline, not by remoting into the environment and spinning up one manually.

Using tools such as SaltStack or Ansible in CI/CD means capitalizing a team's knowledge in a single tool and accelerating some processes, such as configuration management and deployment.


---

#### Standardizing Environments   Deployment and Configuration   Configuration management with Ansible

### Configuration Management with Ansible

Ansible is a configuration management and automation tool. It's an [open-source](https://github.com/ansible/ansible) tool based on Python.

It uses declarative YAML configuration files called playbooks to describe a state or a policy that you want your remote systems to enforce, or execute. Playbooks are Ansible's configuration, deployment, and orchestration language.

Ansible uses Secure Shell (SSH) to execute commands on remote machines which makes it agent-less. It ships with a number of modules that can be executed directly, remotely, or through Playbooks. These modules are reusable components that can be used by Ansible API, or by Ansible or Ansible Playbook programs. Developers can also create their own modules.

Ansible cloud modules are used to automate different tasks like cloud provisioning and workloads automation. Ansible supports different public clouds like Azure.

Using these modules and Playbook language, you can provision and manage the lifecycle of a virtual machine (VM) in Microsoft Azure, manage different services and resources such as availability sets, auto-scaling policies, Azure Container Service, Azure DNS, Azure Function Apps, Azure load balancers, disks, and network interfaces.

Below is an example of a playbook that creates an Azure VM and configures SSH credentials.

```
- name: Create Azure VM
  hosts: localhost
  connection: local
  tasks:
  - name: Create VM
    azure_rm_virtualmachine:
      resource_group: myResourceGroup
      name: myVM
      vm_size: Standard_GS5-8
      admin_username: azureuser
      ssh_password_enabled: false
      ssh_public_keys: 
        - path: /home/azureuser/.ssh/authorized_keys
          key_data: "ssh-rsa CCDDV2aZ...WXhad10h"
      image:
        offer: UbuntuServer
        publisher: Canonical
        sku: '16.04-LTS'
        version: latest
```

You can add other configurations for your VM in the same playbook, for instance: creating a Network Security Group that allows SSH, creating a virtual network interface card that uses this Security Group and attaching this network interface to your VM.

Learn more
* [Create a basic virtual machine in Azure with Ansible](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ansible-create-vm)
* [Install and configure Ansible to manage virtual machines in Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ansible-install-configure)

---

#### Standardizing Environments   Deployment and Configuration   Configuration management with SaltStack

Configuration Management with SaltStack
Salt (or SaltStack) is an open-source project, and you can read and modify its source code under the Apache license. 
Its source code is available on [GitHub](https://github.com/saltstack/salt).

Salt improves the way that system administrators, integrators, and developers configure and manage various aspects of a datacenter infrastructure, and it provides a different approach to some existing alternatives.

Salt is built on a platform running relatively fast while enabling remote control of distributed infrastructures, code, and data. A layer of security is established while having two-way communication between the different components of the platform (Masters and Minions, among others).

The infrastructure that you can manage by using this tool can be on-premises virtual machines, cloud infrastructure (such as Microsoft Azure), containers (Docker, for example), or bare-metal machines. You can also use Salt to manage hosted applications and platforms that rely on configuration files.

You can use Salt as a tool to manage infrastructure and configuration as code, and to automate DevOps toolchains, because it automates source code and configuration management, event-driven tasks and scheduling jobs, as well as cloud and containers provisioning.

Automating a cloud infrastructure such as Azure could be done by connecting Salt to Azure, thereby enabling testing and production environments to be managed using Salt CLI.

SaltStack has four main axes:

* Remote execution
* Configuration automation
* Cloud control
* Event-driven orchestration

Salt platform comes with different components such as Salt Masters, Salt Minions, Top Files, and Salt Cloud.

By using Salt Cloud, you can orchestrate your Azure infrastructure by managing services such as storage accounts or affinity groups, or Azure Resource Manager and resources including VMs, disks, Blob storage virtual networks, or service certificates.

When you create an Azure VM by using Salt, you generally do that from a remote machine where Salt Master is installed. To add a new Azure VM with Minions installed by default and managed by the Salt Master, the easiest way is to use Salt Cloud.

Using a preconfigured virtual machine from Azure VM Depot or Azure Marketplace, you can easily enroll a Salt Master in Azure, then use Salt Cloud to create VMs with predefined configurations.

It is also possible to use Salt Formulas to reproduce any VM configuration while keeping documentation of what is installed on your VMs.

Formulas are pre-written Salt States that you use for various tasks such as installing, configuring, and managing a service lifecycle; managing packages installation; administrating users' accounts and their permissions; and many other common tasks.

To orchestrate your Azure Cloud by using Salt, you will need Microsoft Azure SDK for Python, Microsoft Azure Storage SDK for Python, and the Python Requests library. Of course, you'll also need to have Salt installed and an Azure account.

Learn more
* [Provision and Configure your Infrastructure on Azure using SaltStack](https://www.microsoft.com/developerblog/2017/05/09/provision-configure-infrastructure-azure-using-saltstack/)

---

#### Standardizing Environments   Deployment and Configuration   Benefits of Configuration Management
