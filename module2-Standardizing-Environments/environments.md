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

Here are five reasons to manage configuration and app settings variations per environment in a deployment tool:

* More maintainable: You can manage variables and secrets at multiple levels. The variables that are needed in many release definitions can be stored in a project. You can also define configuration variables that are scoped to a specific release definition or to a specific environment in a release definition. 

* Fewer locations to update: By storing your configuration and app settings in a deployment tool, if settings change at a given time, you only need to update the settings in the deployment tool rather than in every possible file in which the setting is hard-coded. Furthermore, by storing them at the right scope, you do not have to update all the release definitions or environments in which they are used.

* Fewer mistakes: When you store the appropriate settings for each environment in the environment itself in the deployment tool, you won’t accidentally point to the development connection string when in production. The values for settings are siloed out per environment, making it difficult to actively mix up if you are using a deployment tool.

* More secure: When you have connection strings, passwords, or any other settings stored in plain text in a settings file (such as a web.config file), anyone who has access to the code can potentially access a database or machine. A deployment tool such as Visual Studio Team Services provides a rich permissions model that governs who can manage and use secrets at each scope.

* More reliable: By automating the process of transforming configurations through a deployment tool, you’ll be able to count on the transforms always happening during a deployment and setting the appropriate values.

---

#### Standardizing Environments   Deployment and Configuration   Infrastructure as Code

If you’ve ever received a middle-of-the-night emergency support call because of a crashed server, you know the pain of searching through multiple spreadsheets, or even your memory, to access the manual steps of setting up a new machine from scratch. There is also an age-old difficulty: keeping the development and production environments consistent. An easier way to remove the possibility of human error when initializing machines and treat environments like code so that they are stood up from a single consistent definition is to use Infrastructure as Code.

A common analogy for using Infrastructure as Code is the distinction between owning pets and cattle. When you own pets, you give them names, you treat them individually, and if something bad happens to them, you care a lot. If you have a herd of cattle, you might still name them, but you treat them as a herd. In infrastructure terms, without treating environments as code, there might be severe implications if a machine crashes and you need to replace it (pets). If you use Infrastructure as Code, if a machine goes down, you can just spin up another machine with no issues (cattle).

When designing scripts or definitions for Infrastructure as Code (IaC), it’s important to make sure that the code and tools are set up to be idempotent, or able to run multiple times without error and with consistency.

Infrastructure as Code can also be set up with developers' help because many tools offer the ability to write code in familiar programming languages, even ones as simple as JavaScript Object Notification (JSON) definitions. Some examples of common tools you use can to work with Infrastructure as Code are Vagrant, Ansible, Puppet, Chef, Docker, Microsoft Windows PowerShell DSC, and cloud-provided tools such as Azure Resource Management templates.

The following table lists the major differences between manual deployment and Infrastructure as Code:

**Manual Deployment:**
* Snowflakes server
* Deployment steps vary by environment
* More verification steps, and more elaborate manual processes
* Increased documentation to account for differences
* Deployment on weekends to allow time to recover from errors
* Slower release cadence to minimize pain and long weekends
* 

**Infrastructure as Code:**
* Consistent servers between enviroments
* Environments created of scaled easily
* Ensure infrastructure is code and fully automate creation and updates of environments
* Transistion to inmutable infrastructure
* Use blue/green deployments
* Treat servers as cattle, not cats

---

#### Standardizing Environments   Deployment and Configuration   Infrastructure as Code with Terraform

Terraform is an open-source Infrastructure as Code tool. You can use it to define a datacenter by building, changing, and versioning infrastructures.

Terraform has four key features:

Infrastructure as Code
Execution Plans
Resource Graph
Change Automation
The tool uses a high-level configuration from which it generates an execution plan describing what it will do to reach the desired state, and then executes it to build the described infrastructure.

If this configuration changes, Terraform is able to verify what changed and it creates incremental execution plans that can be applied.

Terraform builds a graph of your resources, and parallelizes the creation and modification of any non-dependent resources. It supports custom in-house infrastructures and popular cloud providers such as Microsoft Azure. Terraform can manage Azure low-level components such as Storage and Compute, and also high-level components such as Security Groups or Resource Groups.

Let's take the example of creating an Azure Resource Group. To do that, you should start by creating a new Terraform template (main.tf):

```
resource "azurerm_resource_group" "my-terraform-group" {
    name = "my-resource-group-name"
    location = "West US"
}
```
This should be followed by initializing a working directory containing Terraform configuration files.

    terraform init

Preview the resources to be created by the Terraform template with:

    terraform plan

Finally, provision the Azure resources with:

    terraform apply

After applying this latest change to your Azure infrastructure, the actual state of the new infrastructure is stored in a terraform.tfstate file that was created after the first run of Terraform. By default, Terraform stores the state locally in a file named terraform.tfstate.

The fact that this file is stored locally makes collaboration on a shared infrastructure complex, given the merge conflicts that could result. To let a team collaborate on a shared infrastructure, one state should be used, and that is why Terraform allows the remote state feature. This is done by configuring Terraform to use Azure as a back end and Azure Blob Storage as a storage tool.

Learn more
* [Install and configure Terraform to provision VMs and other infrastructure into Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/terraform-install-configure)
* [Create a complete Linux virtual machine infrastructure in Azure with Terraform](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/terraform-create-complete-vm)


---

#### Standardizing Environments   Deployment and Configuration   Video: Environment Deployment

#### Standardizing Environments   Deployment and Configuration   Configuration as Code

Configuration as code, along with Infrastructure as Code, can help you make the management and configuration of your environments automated and consistent. 

Configuration as code scripts and environment definitions, when used with tools for managing system configuration, are usually idempotent, or can be run multiple times because the scripts or definitions will look for the state of services and install and configure if not running.

Idempotence is the property that a deployment command always sets the target environment into the same configuration, regardless of the environment’s starting state. Idempotency is achieved by either automatically configuring an existing target or by discarding the existing target and re-creating a fresh environment.

The following table lists the major differences between manual configuration and configuration as code:

**Manual configuration**
* Configuration bugs difficult to ID
* Error prone
* More verification steps, and more elaborate manual processes
* Increased documentations
* Deployment on weekends to allow time to recover from errors
* Slower release cadence to minimize pain and long weekends

**Configuration as Code**
* Bugs easily reproducible
* Consistent configurations
* Increase deployment cadence to reduce amount of incremental change
* Treat enviroments and configuration scripts as executable documentation

---

#### Standardizing Environments   Deployment and Configuration   Video: Environment Configuration




