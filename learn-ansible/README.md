# [Ansible for the Absolute Beginner - Hands-On - DevOps](https://www.udemy.com/course/learn-ansible/)

## 1. **Introduction**

**Ansible** is simple open source IT engine which automates application deployment, intra service orchestration, cloud provisioning and many other IT tools.

Ansible is easy to deploy because it does not use any agents or custom security infrastructure.

![How To Install and Test Ansible on Linux - Cộng Đồng Linux](https://congdonglinux.com/wp-content/uploads/2020/11/Ansible.png)

## Infrastructure as Code

Infrastructure as code (IaC) means to manage your IT infrastructure using configuration files.

## 2. **Ansible Inventory**

- Linux: SSH
- Windows: PowerShell Remoting
- Host and Group
Ansible Inventory is the file descibe host and group (ini, yaml).
Ansible works against multiple systems in your infrastructure at the same time. It does this by selecting portions of systems listed in Ansible’s inventory file, which defaults to being saved in the location /etc/ansible/hosts.

## 3. **Ansible Playbooks**

**Playbooks**

Playbooks are the language by which Ansible orchestrates, configures, administers, or deploys systems. They are called playbooks partially because it’s a sports analogy, and it’s supposed to be fun using them. They aren’t workbooks :)

**Plays**

A [playbook](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-playbooks) is a list of plays. A play is minimally a mapping between a set of [hosts](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-host) selected by a host specifier (usually chosen by [groups](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-group) but sometimes by hostname [globs](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-globbing)) and the [tasks](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html#term-tasks) which run on those hosts to define the role that those systems will perform. There can be one or many plays in a playbook.

## 4. **Ansible Modules**

### 1. Command

### 2. Script

### 3. Services

### 4. Idempotency

### 5. Lineinfile



## 5. **Ansible Variables**

## 6. **Conditionals**

## 7. **Loops**

## 8. **Ansible Roles**

Roles let you automatically load related vars, files, tasks, handlers, and other Ansible artifacts based on a known file structure. After you group your content in roles, you can easily reuse them and share them with other users.
