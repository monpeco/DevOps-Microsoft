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