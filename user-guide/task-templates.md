# Task Templates

Templates define how to run an Ansible Playbook. The template allows you to specify the following parameters:

* Playbook repository&#x20;
* Playbook filename
* Inventory
* Environment
* Vault password file
* Extra CLI arguments
* and much more

![](../.gitbook/assets/template\_new\_ipad.png)

The task template can be one of the following types:

* [Task](task-templates.md#task)
* [Build](task-templates.md#build)
* [Deploy](task-templates.md#deploy)

### Task

Just runs specified playbooks with specified parameters.

### Build

This type of template should be used to create [artifacts](https://en.wikipedia.org/wiki/Artifact\_\(software\_development\)). The start version of the artifact can be specified in a template parameter. Each run increments the artifact version.

![](<../.gitbook/assets/template\_new\_build\_ipad (1).png>)

Semaphore doesn't support artifacts out-of-box, it only provides task versioning. You should implement the artifact creation yourself. Read the article [CI/CD](../administration-guide/cicd.md) to know how to do this.

### Deploy

This type of template should be used to deploy artifacts to the destination servers. Each `deploy` template is associated with a `build` template.

![](../.gitbook/assets/template\_new\_deploy\_ipad.png)

This allows you to deploy a specific version of the artifact to the servers.

