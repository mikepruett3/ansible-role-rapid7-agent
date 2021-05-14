Ansible Role: Rapid7_Agent
=========

Ansible role to install/uninstall Rapid7 Insight agent on Linux servers

Requirements
------------

The role does not require anyting to run on RHEL and its derivatives. This role assumes that you have the software package located on a web server somewhere in your environment.

Role Variables
--------------

Available variables are listed below, along with default values (see ```defaults/main.yml```):

```
install: true
software_url: "http://www.example.org"
package_name: "rapid7-agent-installer.zip"
token_install: false
regionalID: "us"
UUID: "11111111-1111-1111-1111-11111111111"
```

```install:``` **(Required)** Used to control wether or not to install the agent, or uninstall a previously installed agent. Defaults to **true**.

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

```token_install``` **(Optional)** If the installation is to be completed using the **Token** install choice, than this var needs to be set as **true**. Otherwise, the installation will be completed using the **Certificate** based install. Certificates should be included in the Installer package for convenience. **(Defaults to Certificate Install)**

```regionalID``` **(Optional)** For **Token** installs, the Regional ID to be used. (i.e. **"us"**)

```UUID``` **(Optional)** For **Token** installs, the UUID to be used.

Role variables can be stored with the ```hosts.yaml``` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: mikepruett3.rapid7_agent
           vars:
             install: true
             software_url: "http://www.example.org"
             package_name: "rapid7-agent-installer.zip"

License
-------

MIT / BSD

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3)
