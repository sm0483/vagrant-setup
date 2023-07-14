# Vagrant and Ansible Provisioning

This project demonstrates how to use Vagrant and Ansible to provision virtual machines and automate the installation of Nginx and Docker on the target machines.

## Requirements

Before getting started, ensure that the following software is installed on your system:

-  Vagrant: [Download and install Vagrant](https://www.vagrantup.com/downloads).
-  VirtualBox: [Download and install VirtualBox](https://www.virtualbox.org/wiki/Downloads).
-  Ansible: [Installation instructions for Ansible](https://docs.ansible.com/ansible/latest/installation_guide/index.html).

## Usage

1. Clone this repository to your local machine.

2. Navigate to the project directory.

3. Customize the `Vagrantfile`:

   -  Update the number of machines or adjust their configuration (e.g., memory, CPU).
   -  Modify the base box if needed.
   -  Add or remove any additional configuration options as required.

4. Customize the `playbook.yml`:

   -  Add or modify tasks to install or configure additional software.
   -  Include any other desired configuration steps.

5. Customize the `inventory.ini`:

   -  Define the hosts or groups that the playbook should target.
   -  Update the hostnames and IP addresses as necessary.

6. Open a terminal or command prompt and navigate to the project directory.

7. Run the following command to provision the machines and execute the playbook:

```bash
vagrant up # used to up the machine
vagrant status # check status
vagrant halt # stop machine
vagrant destroy # remove all machines
vagrant provision # provision these machines
```

### important code snippet

```js

// used to work with ansible
machine.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.limit = "web-servers#{i}"
end
```
