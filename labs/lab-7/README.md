# Introducing Ansible Tower
Red Hat Ansible Tower (build from the Open Source project, AWX) helps you scale out your Ansible automation
Running Ansible from a command line is all good, until you start to automate more things. When you do that, you get a number of concerns, primarily:

>How can I control who can run what playbooks where?

This is a central concerns which stimms from the fact that sharing access is difficult. Because of this, some companies don't even allow people to share access, because of (valid) security concerns.

Very often, you fail to automate things because it was not possible to share access. As an example, if you want to automate
the configuration of SAN storage at your company, your SAN storage switches may not allow granular enough access so that the users which you use to do the automation - can only do what you need it to do (which in that case would be to zone-in a disk to one or more specific servers).

Because of this, it's not uncommon that attempts to automate things fails with conversations like:

>If I were to give you access to XYZ, you would be able to destroy all data at the company. And you don't even have XYZ training.

Ansible tower allows you to share access safely to other people via it's web GUI, a CLI client and a REST API. Let's explore how this works.

>First step, go unto your Ansible Tower server: https://<your-tower-server> and login with your assigned user.

What we'll do first is to create an inventory in Ansible Tower, an inventory is a collection of hosts you can run playbooks against in Tower. Inventories are assigned to organizations, while permissions to launch playbooks against inventories are controlled at the user, team or playbook level.

>Create an inventory called "yourUSERNAME-inventory" by following the instructions below.

* To create a new inventory, click on the 'Inventories' tab and click the add button.

 ![Creating an inventory](https://github.com/mglantz/ansible-roadshow/blob/master/content/create-new-inventory.png?raw=true)

Next thing that we'll do is to create a project. A Project is a logical collection of Ansible playbooks, represented in Tower.
You can manage playbooks and playbook directories by either placing them manually under the Project Base Path on your Tower server, or by placing your playbooks into a source code management (SCM) system supported by Tower, including Git, Subversion, and Mercurial.

>Create a project called "yourUSERNAME-playbooks" by following the instructions below.
  
* To create a new project, click on the 'Projects' tab and click on the add button. Make sure to link your project to the GitHub repository, which [you created earlier in lab-6](https://github.com/mglantz/ansible-roadshow/tree/master/labs/lab-6).

 ![Create a project](https://github.com/mglantz/ansible-roadshow/blob/master/content/create-project.png?raw=true)

Next you will provide access to the playbook which [you put onto GitHub earlier in lab-6](https://github.com/mglantz/ansible-roadshow/tree/master/labs/lab-6). This is done using so called job templates. A job template combines an Ansible playbook from a project and the settings required to launch it.





>How can I see who ran what playbook where?

>

Centralize and control your IT infrastructure with a visual dashboard, role-based access control, job scheduling, integrated notifications and graphical inventory management. 
And Ansible Tower's REST API and CLI make it easy to embed Ansible Tower into existing tools and processes.