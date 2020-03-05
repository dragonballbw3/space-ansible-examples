<!-- omit in toc -->
# Space Ansible Collection - Lab Guide

*Written by [@mtucker502](https://github.com/mtucker502)*

<!-- omit in toc -->
## Table of Contents

- [Chapter 1 - Lab Setup](#chapter-1---lab-setup)
  - [Step 1.1](#step-11)
  - [Step 1.2](#step-12)
  - [Step 1.3](#step-13)
  - [Step 1.4](#step-14)
  - [Step 1.5](#step-15)
  - [Step 1.6](#step-16)
- [Chapter 2 - Configure Ansible](#chapter-2---configure-ansible)
  - [Step 2.1](#step-21)
  - [Step 2.2](#step-22)
  - [Step 2.3](#step-23)
  - [Step 2.4](#step-24)
  - [Step 2.5](#step-25)
  - [Step 2.6](#step-26)
- [Chapter 3 - Managing Devices](#chapter-3---managing-devices)
  - [Step 3.1](#step-31)
  - [Step 3.2](#step-32)
  - [Step 3.3](#step-33)
  - [Step 3.4](#step-34)
  - [Step 3.5](#step-35)
  - [Step 3.6](#step-36)
  - [Step 3.7](#step-37)
  - [Step 3.8](#step-38)
- [Chapter 4 - Manipulating Data](#chapter-4---manipulating-data)
  - [Step 4.1](#step-41)
  - [Step 4.2](#step-42)
  - [Step 4.3](#step-43)
  - [Step 4.4](#step-44)
  - [Final thoughts](#final-thoughts)
- [Chapter 5 - Managing Addresses](#chapter-5---managing-addresses)
  - [Step 5.1](#step-51)
  - [Step 5.2](#step-52)
  - [Step 5.3](#step-53)
  - [Step 5.4](#step-54)
  - [Step 5.5](#step-55)
  - [Step 5.6](#step-56)
  - [Step 5.7](#step-57)
  - [Step 5.8](#step-58)
  - [Step 5.9](#step-59)
  - [Step 5.10](#step-510)
  - [Step 5.11](#step-511)

<!-- omit in toc -->
## How to use this lab guide

- Each chapter is seperated into easy to follow steps
- Below are examples of differrent text formats you will find in this lab guide

> **this is a command you need to enter**

```
Expected command output goes here
Expected command output goes here
Expected command output goes here
Expected command output goes here
Expected command output goes here
Expected command output goes here
Expected command output goes here
Expected command output goes here
Expected command output goes here
```

# Chapter 1 - Lab Setup

## Step 1.1

Install Python's virtualenv module

> **python3.6 -m pip install --user virtualenv**

**Output**:

```bash
[lab@desktop ~]$ python3.6 -m pip install --user virtualenv
Collecting virtualenv
  Using cached https://files.pythonhosted.org/packages/33/4e/9f3e70ed2bf3de603bf4de46cb60af1309c8d97fd81cbde317507a57573e/virtualenv-20.0.5-py2.py3-none
-any.whl
Collecting appdirs<2,>=1.4.3 (from virtualenv)
  Using cached https://files.pythonhosted.org/packages/56/eb/810e700ed1349edde4cbdc1b2a21e28cdf115f9faf263f6bbf8447c1abf3/appdirs-1.4.3-py2.py3-none-any
.whl
Collecting importlib-resources<2,>=1.0; python_version < "3.7" (from virtualenv)
  Using cached https://files.pythonhosted.org/packages/2f/f7/b4aa02cdd3ee7ebba375969d77c00826aa15c5db84247d23c89522dccbfa/importlib_resources-1.0.2-py2.
py3-none-any.whl
Collecting importlib-metadata<2,>=0.12; python_version < "3.8" (from virtualenv)
  Using cached https://files.pythonhosted.org/packages/8b/03/a00d504808808912751e64ccf414be53c29cad620e3de2421135fcae3025/importlib_metadata-1.5.0-py2.p
y3-none-any.whl
Collecting filelock<4,>=3.0.0 (from virtualenv)
  Using cached https://files.pythonhosted.org/packages/93/83/71a2ee6158bb9f39a90c0dea1637f81d5eef866e188e1971a1b1ab01a35a/filelock-3.0.12-py3-none-any.w
hl
Collecting six<2,>=1.9.0 (from virtualenv)
  Cache entry deserialization failed, entry ignored
  Using cached https://files.pythonhosted.org/packages/65/eb/1f97cb97bfc2390a276969c6fae16075da282f5058082d4cb10c6c5c1dba/six-1.14.0-py2.py3-none-any.wh
l
Collecting distlib<1,>=0.3.0 (from virtualenv)
  Using cached https://files.pythonhosted.org/packages/7d/29/694a3a4d7c0e1aef76092e9167fbe372e0f7da055f5dcf4e1313ec21d96a/distlib-0.3.0.zip
Collecting zipp>=0.5 (from importlib-metadata<2,>=0.12; python_version < "3.8"->virtualenv)
  Using cached https://files.pythonhosted.org/packages/6f/6d/a55f6e81ac213942b9a19cbc05b560c726c3e16f8fb17555f059c17d65f2/zipp-3.0.0-py3-none-any.whl
Installing collected packages: appdirs, importlib-resources, zipp, importlib-metadata, filelock, six, distlib, virtualenv
  Running setup.py install for distlib ... done
Successfully installed appdirs-1.4.3 distlib-0.3.0 filelock-3.0.12 importlib-metadata-1.5.0 importlib-resources-1.0.2 six-1.14.0 virtualenv-20.0.5 zipp-
3.0.0
You are using pip version 9.0.1, however version 20.0.2 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
```

## Step 1.2 

Create the Virtual Environment

> **python3.6 -m virtualenv venv**

**Output**:

```bash
[lab@desktop ~]$ python3.6 -m virtualenv venv
created virtual environment CPython3.6.1.final.0-64 in 313ms
  creator CPython3Posix(dest=/home/lab/venv, clear=False, global=False)
  seeder FromAppData(download=False, pip=latest, setuptools=latest, wheel=latest, via=copy, app_data_dir=/home/lab/.local/share/virtualenv/seed-v1)
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator
```

## Step 1.3

Activate the Virtual Environment

> **source venv/bin/activate**

**Output**:

```bash
[lab@desktop ~]$ source venv/bin/activate
(venv) [lab@desktop ~]$
```

Notice how the prompt is prepended with `(venv)`

## Step 1.4

Verify the virtual environment is supplying python correctly

> **which python**

**Output:**

```bash
(venv) [lab@desktop ~]$ which python
~/venv/bin/python
```

If your output does not match the above stop and notify your instructor!

## Step 1.5

Install Ansible

> **pip install ansible**

**Output**:

```bash
(venv) [lab@desktop ~]$ pip install ansible

####.....previous lines omitted.....####

Successfully built ansible PyYAML pycparser
Installing collected packages: MarkupSafe, jinja2, PyYAML, six, pycparser, cffi, cryptography, ansible
Successfully installed MarkupSafe-1.1.1 PyYAML-5.3 ansible-2.9.5 cffi-1.14.0 cryptography-2.8 jinja2-2.11.1 pycparser-2.19 six-1.14.0
(venv) [lab@desktop ~]$ 
```

## Step 1.6

Install Junos Space Ansible Collection

> **ansible-galaxy collection install juniper.space**

**Output:**

```bash
(venv) [lab@desktop ~]$ ansible-galaxy collection install juniper.space
Process install dependency map
Starting collection install process
Installing 'juniper.space:0.1.0' to '/home/lab/.ansible/collections/ansible_collections/juniper/space'
```

# Chapter 2 - Configure Ansible

## Step 2.1

Create a project directory

First we will create a folder to hold our project related files

> **mkdir ~/space_is_awesome**

This will create a folder named 'space_is_awesome' in your home directory.

## Step 2.2

Change directory to the new folder

Now that we have a directory we need to change directories to it

> **cd ~/space_is_awesome**

## Step 2.3

Create Ansible config file

Now we will create an `ansible.cfg` file which contain defaults to make using the ansible-playbooks easier to use. Specifically this config file will point to an inventory file containing details on how to connect to the Space API. We will create this file in a later step.

Use your preferred editor to create the `ansible.cfg` file with the following contents:

```ini
[defaults]
log_path = ./ansible.log
inventory = hosts
```

*nano is an easy editor to use on the Linux CLI*

## Step 2.4

Create the Ansible inventory

Again, use your preferred edit to create a file named `hosts`
```ini
[space]
space01 ansible_host=172.25.11.100

[space:vars]
ansible_network_os=juniper.space.space
ansible_connection=httpapi
ansible_user=super
ansible_password=lab123
ansible_httpapi_validate_certs=False
ansible_httpapi_use_ssl=True
```

## Step 2.5

Create a test playbook

Create a new file named `pb.get.devices.yml` with the following lines:

```yaml
---
- name: Chapter 2
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  tasks:
    - name: Get all devices
      space_device_info:
      register: output

    - debug:
        var: output
```

## Step 2.6

Run the test playbook

> **ansible-playbook pb.get.devices.yml**

**Output:**

```bash
$ ansible-playbook pb.get.devices.yml

PLAY [Chapter 2] **********************************************************************************************************************************************

TASK [Get all devices] ****************************************************************************************************************************************************
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.

ok: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python"
        },
        "changed": false,
        "devices": null,
        "failed": false,
        "warnings": [
            "Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information."
        ]
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

Note that the `devices` key is `null` but this is because we haven't discovered any devices yet.

# Chapter 3 - Managing Devices

In this chapter we will add and remove devices as well as retrieve device info using filters

## Step 3.1

First we need to create the playbook which uses the `space_device` module. Create a file named `pb.add.device.yml` with the following contents:
```yaml
---
- name: Chapter 3
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  tasks:
    - name: Create Device
      space_device:
        ip_address: 172.25.11.1
        state: present
        username: jcluser
        password: Juniper!1
        use_ping: True
      register: output

    - debug:
        var: output
```

## Step 3.2

Run the new playbook to discover the device:

> **ansible-playbook pb.add.device.yml**

```bash
$ ansible-playbook pb.add.device.yml

PLAY [Chapter 3] **********************************************************************************************************************************************

TASK [Create Device] **************************************************************************************************************************************************
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.

changed: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python"
        },
        "changed": true,
        "device": [
            {
                "@href": "/api/space/device-management/devices/6",
                "@key": "6",
                "@uri": "/api/space/device-management/devices/6",
                "OSVersion": "18.3R1.9",
                "authentication-status": "CREDENTIAL_UNVERIFIED",
                "config-status": "DEVICE_STATE_IN_SYNC",
                "connection-type": "Junos Space initiated",
                "connectionStatus": "up",
                "device-id": 6,
                "deviceFamily": "junos-es",
                "domain-id": 2,
                "domain-name": "Global",
                "fingerprint": "b1:a4:0e:f4:e7:8d:50:e0:0a:7f:f6:01:e9:ab:47:01",
                "hosting-deviceId": 0,
                "ipAddr": "100.123.12.0",
                "lsys-count": 0,
                "managedStatus": "In Sync",
                "name": "vSRX-addr-0",
                "platform": "VSRX",
                "serialNumber": "7E9C45E29F82",
                "use-nat": false,
                "web-mgmt": "https"
            }
        ],
        "failed": false,
        "job_status": "DONE",
        "task_id": 458773,
        "warnings": [
            "Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information."
        ]
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

Notice `ok=2` and `changed=1`. This indidcates that both tasks, create device and debug, completed successfully and only one change was made.

## Step 3.3

Run the test playbook again and see that the device now appears:

> **ansible-playbook pb.get.devices.yml**

**Output:**

*Your output may differ based on your lab environment*

```bash
$ ansible-playbook pb.get.devices.yml

PLAY [Chapter 3] **********************************************************************************************************************************************

TASK [All devices] ****************************************************************************************************************************************************
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.

ok: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python"
        },
        "changed": false,
        "devices": [
            {
                "@href": "/api/space/device-management/devices/5",
                "@key": "5",
                "@uri": "/api/space/device-management/devices/5",
                "OSVersion": "18.3R1.9",
                "authentication-status": "CREDENTIAL_UNVERIFIED",
                "config-status": "DEVICE_STATE_IN_SYNC",
                "connection-type": "Junos Space initiated",
                "connectionStatus": "up",
                "device-id": 5,
                "deviceFamily": "junos-es",
                "domain-id": 2,
                "domain-name": "Global",
                "fingerprint": "b1:a4:0e:f4:e7:8d:50:e0:0a:7f:f6:01:e9:ab:47:01",
                "hosting-deviceId": 0,
                "ipAddr": "100.123.12.0",
                "lsys-count": 0,
                "managedStatus": "In Sync",
                "name": "vSRX-addr-0",
                "platform": "VSRX",
                "serialNumber": "7E9C45E29F82",
                "use-nat": false,
                "web-mgmt": "https"
            }
        ],
        "failed": false,
        "warnings": [
            "Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information."
        ]
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

## Step 3.4

Now lets run the same `pb.add.device.yml` again. Will any changes be made?

> **ansible-playbook pb.add.device.yml**

**Output:**

```bash
$ ansible-playbook pb.space.device.yml

PLAY [Chapter 3] **********************************************************************************************************************************************

TASK [Create Device] **************************************************************************************************************************************************
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.

ok: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python"
        },
        "changed": false,
        "device": {
            "@uri": "/api/space/device-management/devices/6",
            "OSVersion": "18.3R1.9",
            "activate-modeled-device": {
                "@href": "/api/space/device-management/devices/6/activate-modeled-device"
            },
            "applicable-configlets": {
                "@href": "/api/space/device-management/devices/6/applicable-configlets"
            },
            "apply-cli-configlet": {
                "@href": "/api/space/device-management/devices/6/apply-cli-configlet"
            },
            "associated-scripts": {
                "@href": "/api/space/device-management/devices/6/associated-scripts"
            },
            "associated-softwares": {
                "@href": "/api/space/device-management/devices/6/associated-softwares"
            },
            "authentication-status": "CREDENTIAL_UNVERIFIED",
            "change-requests": {
                "@uri": "/api/space/device-management/devices/6/change-requests"
            },
            "clone": {
                "@href": "/api/space/device-management/devices/6/clone"
            },
            "compute-configlet-parameter-values": {
                "@href": "/api/space/device-management/devices/6/compute-configlet-parameter-values"
            },
            "config-files": {
                "@href": "/api/space/config-file-management/config-files?filter=(deviceId eq 6)"
            },
            "config-status": "DEVICE_STATE_IN_SYNC",
            "configlet": {
                "@href": "/api/space/device-management/devices/6/configlet"
            },
            "configurations": {
                "@href": "/api/space/device-management/devices/6/configurations"
            },
            "connection-status": {
                "@uri": "/api/space/device-management/devices/6/connection-status",
                "status": "up"
            },
            "connection-type": "Junos Space initiated",
            "customized-attribute-values": {
                "@href": "/api/space/device-management/devices/6/customized-attribute-values"
            },
            "device-id": 6,
            "deviceFamily": "junos-es",
            "domain": {
                "@href": "/api/space/domain-management/domains/2"
            },
            "domain-id": 2,
            "domain-name": "Global",
            "hostName": "vSRX-addr-0",
            "hosting-deviceId": 0,
            "id": 6,
            "ipAddr": "100.123.12.0",
            "lsys-count": 0,
            "managed-elements": {
                "@uri": "/api/space/device-management/devices/6/managed-elements",
                "managed-element": {
                    "@href": "/api/space/managed-domain/managed-elements/475",
                    "deviceId": 6,
                    "id": 475,
                    "ipAddr": "100.123.12.0"
                }
            },
            "managed-status": {
                "@uri": "/api/space/device-management/devices/6/managed-status",
                "status": "In Sync"
            },
            "modify-device-target-ip": {
                "@href": "/api/space/device-management/devices/6/modify-device-target-ip"
            },
            "name": "vSRX-addr-0",
            "platform": "VSRX",
            "rpc": {
                "@href": "/api/space/device-management/devices/6/exec-rpc"
            },
            "schema-version": "junos-es_18.3R1.9",
            "serialNumber": "7E9C45E29F82",
            "submit-cli-configlet": {
                "@href": "/api/space/device-management/devices/6/submit-cli-configlet"
            },
            "use-nat": false,
            "validate-cli-configlet": {
                "@href": "/api/space/device-management/devices/6/validate-cli-configlet"
            },
            "web-mgmt": "https"
        },
        "failed": false,
        "msg": "Device already present",
        "warnings": [
            "Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information."
        ]
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

This time `ok=2` but `changed=0` indicating both tasks completed successfully but no changes were made. Also notice the `msg` key in the output: `"msg": "Device already present"`.

This is because in our playbook we have set `state: present` which is already the current state. This playbook can be ran repeatedly no changes will be made.

## Step 3.5

How can we remove the device? Easy! Just copy change `state: absent` and re-run the playbook.

First lets create a copy of our playbook:

> **cp pb.add.device.yml pb.remove.device.yml**

Modify your `pb.remove.device.yml` file to match the following:

```yaml
---
- name: Chapter 3
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  tasks:
    - name: Remove Device     #<------------Changed
      space_device:
        ip_address: 100.123.12.0
        state: absent         #<------------Changed
        username: jcluser
        password: Juniper!1
        use_ping: True
      register: output

    - debug:
        var: output
```

## Step 3.6

Run the playbook to remove the device

> **ansible-playbook pb.remove.device.yml**

**Output:**

```bash
$ ansible-playbook pb.remove.device.yml

PLAY [Chapter 3] **********************************************************************************************************************************************

TASK [Remove Device] **************************************************************************************************************************************************
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.

changed: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python"
        },
        "changed": true,
        "failed": false,
        "task_id": 458775,
        "warnings": [
            "Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information."
        ]
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

## Step 3.7

Now let us add mutliple devices. In the lab topology there are 4 vsrx devices. We could add one task for each device. With only 4 devices this would be relatively easy but it wouldn't scale very well.

Instead, let's use a list. Create a new file named `pb.add.device.list.yml` with the following content:

```yaml
---
- name: Chapter 3
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  tasks:
    - name: Create Device
      space_device:
        ip_address: "{{ item }}"
        state: present
        username: jcluser
        password: Juniper!1
        use_ping: True
      register: output
      with_items:
        - 172.25.11.1
        - 172.25.11.2
        - 172.25.11.3
        - 172.25.11.4

    - debug:
        var: output
```

## Step 3.8

Now run the new playbook.

> **ansible-playbook pb.add.device.list.yml**


```bash
$ ansible-playbook pb.add.device.list.yml

PLAY [Chapter 3] **********************************************************************************************************************************************

TASK [Create Device] **************************************************************************************************************************************************
changed: [space01] => (item=172.25.11.1)
changed: [space01] => (item=172.25.11.2)
changed: [space01] => (item=172.25.11.3)
changed: [space01] => (item=172.25.11.4)
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.


TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
      #######################
      ##OMITTED FOR BREVITY##
      #######################
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=4    changed=4    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

# Chapter 4 - Manipulating Data

Let's revisit the `pb.get.devices.yml` playbook we created in Chapter 2. This playbook uses the `space_device_info` module.

The `debug` module inside of the playbook outputs everthing that the `space_device_info` module outputs which is quite a bit of data.

What if we only wanted to output some specific subset of that data? Since the data is in a JSON format it is very easy to only display the keys we're interested in.

## Step 4.1

Rerun the `pb.get.devices.yml` playbook to examine the level of detail that is displayed.


## Step 4.2

First we will extract the OSVersion:

Modify the `pb.get.devices.yml` playbook's `debug` task to match the following:

```yaml
---
- name: Space API Example
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  tasks:
    # - name: All devices
    #   space_device_info:
    #     # ip_address: 100.123.12.0
    #   register: output

    # - debug:
    #     var: output

    - name: All devices
      space_device_info:
      register: output

    - debug:
        msg: "{{ item.OSVersion }}"
      with_items: "{{ output.devices.device }}"
```

## Step 4.3

> **ansible-playbook pb.get.devices.yml**

**Output:**

```bash
#######################
##OMITTED FOR BREVITY##
#######################
```

Note: Instead of using the `debug` module to write data to the screen we could just as easily save this output to a file using the `local_action: copy content` module.

## Step 4.4

Try only displaying other specific data in the debug msg such as the serial number.

No examples provided here, try this on your own!

## Final thoughts

Being able to drill down and only grab a device's properties will allow you to use this data in future tasks.

Examples:

1. Update credentials only for devices where `authentication-status` is in a failed state.
2. Using the `device-id` from the `sd_device_info` module to assign firewall policies.
3. Generating reports which only contain the specific data you need 

# Chapter 5 - Managing Addresses

Before we can create firewall policies+rules we need to create the building blocks of a policy: addresses and services. In this chapter we will focus on address management.

The `sd_address` and `sd_address_info` modules allow you to manage address objects and obtain information on those objects.

SD comes bundled with predefined address objects that may be useful in building policies. Let's take a look at those predefined address objects.

## Step 5.1

Create a new playbook with the following contents:

```yaml
---
- name: Chapter 5
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  tasks:
    - name: Get Addresses
      sd_address_info:
      register: output

    - debug:
        var: output
```

## Step 5.2

Run the playbook:

> **ansible-playbook pb.get.addresses.yml**

**Output:**

```bash
$ ansible-playbook pb.sd.address.info.yml

PLAY [Chapter 4] **********************************************************************************************************************************************

TASK [Get Addresses] **************************************************************************************************************************************************
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.

ok: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "addresses": [
            {
                "addr_name": "Any",
                "address_type": "ANY",
                "address_version": "IPV4",
                "definition_type": "PREDEFINED",
                "description": "Predefined any address",
                "domain-id": 1,
                "edit_version": 1,
                "host_name": "",
                "href": "/api/juniper/sd/address-management/v5/address/196608",
                "id_perms": {
                    "created": "2018-12-21T18:44:52.000026",
                    "created-time": 1545417892026,
                    "creator": "Juniper Networks Inc.",
                    "last-modified-time": 1545417892026,
                    "last_modified": "2018-12-21T18:44:52.000026"
                },
                "name": "Any",
                "update_number": 0,
                "uri": "/api/juniper/sd/address-management/v5/address/196608",
                "uuid": "196608"
            },
            {
                "addr_name": "Any-IPv4",
                "address_type": "ANY_IPV4",
                "address_version": "IPV4",
                "definition_type": "PREDEFINED",
                "description": "Predefined any-ipv4 address",
                "domain-id": 1,
                "edit_version": 1,
                "host_name": "",
                "href": "/api/juniper/sd/address-management/v5/address/196609",
                "id_perms": {
                    "created": "2018-12-21T18:44:52.000032",
                    "created-time": 1545417892032,
                    "creator": "Juniper Networks Inc.",
                    "last-modified-time": 1545417892032,
                    "last_modified": "2018-12-21T18:44:52.000032"
                },
                "name": "Any-IPv4",
                "update_number": 0,
                "uri": "/api/juniper/sd/address-management/v5/address/196609",
                "uuid": "196609"
            },
            {
                "addr_name": "Any-IPv6",
                "address_type": "ANY_IPV6",
                "address_version": "IPV6",
                "definition_type": "PREDEFINED",
                "description": "Predefined any-ipv6 address",
                "domain-id": 1,
                "edit_version": 1,
                "host_name": "",
                "href": "/api/juniper/sd/address-management/v5/address/196610",
                "id_perms": {
                    "created": "2018-12-21T18:44:52.000035",
                    "created-time": 1545417892035,
                    "creator": "Juniper Networks Inc.",
                    "last-modified-time": 1545417892035,
                    "last_modified": "2018-12-21T18:44:52.000035"
                },
                "name": "Any-IPv6",
                "update_number": 0,
                "uri": "/api/juniper/sd/address-management/v5/address/196610",
                "uuid": "196610"
            }
        ],
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python"
        },
        "changed": false,
        "failed": false,
        "warnings": [
            "Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information."
        ]
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

## Step 5.3

In this chapter, we will use vars stored in the playbook itself. These vars however could come from an Ansible inventory, another IPAM service, or a group_vars/host_vars file.

Also, we will focus on using lists and `with_items` to make future modificiations to the playbook easier.

Create a playbook named `pb.add.addresses.yml` with the following content:

```yaml
---
- name: Chapter 5
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  vars:
    gtac_servers:
      - name: gtac1
        ip_address: 172.16.10.50

  tasks:
    - name: Create GTAC Addresses
      sd_address:
        name: "{{ item.name }}"
        ip_address: "{{ item.ip_address }}"
        state: present
      register: output
      with_items: "{{ gtac_servers }}"

    - debug:
        var: output

```

## Step 5.4

Run the new playbook:

> **ansible-playbook pb.sd.addresses.yml**

**Output:**

```bash
$ ansible-playbook pb.sd.address.yml

PLAY [Chapter 5] **********************************************************************************************************************************************

TASK [Create GTAC Addresses] ******************************************************************************************************************************************
changed: [space01] => (item={'name': 'gtac1', 'ip_address': '172.16.10.50'})
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.


TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
#######################
##OMITTED FOR BREVITY##
#######################
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

## Step 5.5

As expected there has been a new GTAC server provisioned and we now need to add this new server to our playbook.

Because we planned ahead and are using `with_items` this is an easy change.

Modify the `vars` section in the `pb.sd.address.yml` to match the following:

```yaml
  vars:
    gtac_servers:
      - name: gtac1
        ip_address: 172.16.10.50
      - name: gtac2
        ip_address: 172.16.10.51
```

## Step 5.6

Run the `pb.add.addresses.yml` playbook again to add the new GTAC server:

> **ansible-playbook pb.add.addresses.yml**

**Output:**

```bash
$ ansible-playbook pb.sd.address.yml

PLAY [Chapter 5] **********************************************************************************************************************************************

TASK [Create GTAC Addresses] ******************************************************************************************************************************************
ok: [space01] => (item={'name': 'gtac1', 'ip_address': '172.16.10.50'})
changed: [space01] => (item={'name': 'gtac2', 'ip_address': '172.16.10.51'})
[WARNING]: Platform darwin on host space01 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could
change this. See https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.


TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
#######################
##OMITTED FOR BREVITY##
#######################
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

## Step 5.7

Currently to allow traffic to the GTAC servers in a firewall policy we would need to add each address object individually to the policy.

We can simplify the policy and make updates easier by adding the address objects to an address group and only referencing the address group in the firewall policy.

Add the following task so we can examine how the `gtac_servers` variable currently is organized:

```yaml
    - debug:
        var: gtac_servers
```

## Step 5.8

Rerun the `pb.add.addresses.yml` playbook:

> **ansible-playbook pb.add.addresses.yml**

**Output:**

```bash
#######################
##OMITTED FOR BREVITY##
#######################
TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "gtac_servers": [
        {
            "ip_address": "172.16.10.50",
            "name": "gtac1"
        },
        {
            "ip_address": "172.16.10.51",
            "name": "gtac2"
        }
    ]
}
```

You can see the `gtac_servers` variable contains both name and ip_address keys:

## Step 5.9

Since the `sd_address` module expects group members to only be a list of member names we need to first trim down the `gtac_servers` variable to only include a list of names.

We can do this with the `set_fact` module.

Add the following tasks to the end of the `pb.sd.address.yml` playbook:

```yaml
    - set_fact:
        gtac_server_names: "{{ gtac_servers | map(attribute='name') | list }}"

    - debug:
        var: gtac_server_names
```

**Output:**

```bash
#######################
##OMITTED FOR BREVITY##
#######################
TASK [set_fact] *******************************************************************************************************************************************************
ok: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "gtac_server_names": [
        "gtac1",
        "gtac2"
    ]
}
```

Perfect. This is a variable containing only the list of names of the GTAC servers. We can use this new variable in the next task.

## Step 5.10

Add the following final tasks to the `pb.add.addresses.yml` playbook:

```yaml
    - name: Create GTAC Address Group
      sd_address:
        name: gtac-servers
        state: present
        type: group
        members: "{{ gtac_server_names }}"
      register: output

    - debug:
        var: output
```

Your `pb.add.addresses.yml` playbook should now match the following:

```yaml
---
- name: Chapter 5
  hosts: all
  connection: httpapi
  gather_facts: no
  collections:
    - juniper.space

  vars:
    gtac_servers:
      - name: gtac1
        ip_address: 172.16.10.50
      - name: gtac2
        ip_address: 172.16.10.51

  tasks:
    - name: Create GTAC Addresses
      sd_address:
        name: "{{ item.name }}"
        ip_address: "{{ item.ip_address }}"
        state: present
      register: output
      with_items: "{{ gtac_servers }}"

    - debug:
        var: output

    - debug:
        var: gtac_servers

    - set_fact:
        gtac_server_names: "{{ gtac_servers | map(attribute='name') | list }}"

    - debug:
        var: gtac_server_names

    - name: Create GTAC Address Group
      sd_address:
        name: gtac-servers
        state: present
        type: group
        members: "{{ gtac_server_names }}"
      register: output

    - debug:
        var: output
```

## Step 5.11

Rerun the `pb.add.addresses.yml` playbook:

> **ansible-playbook pb.add.addresses.yml**

**Output:**

```yaml
#######################
##OMITTED FOR BREVITY##
#######################
TASK [Create GTAC Address Group] **************************************************************************************************************************************
changed: [space01]

TASK [debug] **********************************************************************************************************************************************************
ok: [space01] => {
    "output": {
        "address": {
            "addr_name": "gtac-servers",
            "address_refs": [
                {
                    "addr_name": "gtac1",
                    "address_refs": [],
                    "address_type": "IPADDRESS",
                    "address_version": "IPV4",
                    "associated_metadata": "",
                    "definition_type": "CUSTOM",
                    "description": "",
                    "domain-id": 2,
                    "edit_version": 1,
                    "host_name": "",
                    "id_perms": {
                        "created": "2020-03-05T15:18:22.000760",
                        "created-time": 1583421502760,
                        "creator": "jcluser",
                        "last-modified-by-user-name": "jcluser",
                        "last-modified-time": 1583421502760,
                        "last_modified": "2020-03-05T15:18:22.000760"
                    },
                    "ip_address": "172.16.10.50",
                    "name": "gtac1",
                    "update_number": 0,
                    "uuid": "327684"
                },
                {
                    "addr_name": "gtac2",
                    "address_refs": [],
                    "address_type": "IPADDRESS",
                    "address_version": "IPV4",
                    "associated_metadata": "",
                    "definition_type": "CUSTOM",
                    "description": "",
                    "domain-id": 2,
                    "edit_version": 1,
                    "host_name": "",
                    "id_perms": {
                        "created": "2020-03-05T15:24:31.000979",
                        "created-time": 1583421871979,
                        "creator": "jcluser",
                        "last-modified-by-user-name": "jcluser",
                        "last-modified-time": 1583421871979,
                        "last_modified": "2020-03-05T15:24:31.000979"
                    },
                    "ip_address": "172.16.10.51",
                    "name": "gtac2",
                    "update_number": 0,
                    "uuid": "327685"
                }
            ],
            "address_type": "GROUP",
            "address_version": "IPV4",
            "associated_metadata": "",
            "definition_type": "CUSTOM",
            "description": "",
            "domain-id": 2,
            "edit_version": 1,
            "host_name": "",
            "id_perms": {
                "created": "2020-03-05T15:45:57.000397",
                "created-time": 1583423157397,
                "creator": "jcluser",
                "last-modified-by-user-name": "jcluser",
                "last-modified-time": 1583423157397,
                "last_modified": "2020-03-05T15:45:57.000397"
            },
            "name": "gtac-servers",
            "update_number": 0,
            "uri": "/api/juniper/sd/address-management/v5/address/327686",
            "uuid": "327686"
        },
        "changed": true,
        "failed": false
    }
}

PLAY RECAP ************************************************************************************************************************************************************
space01                    : ok=7    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```