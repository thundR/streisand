

arch-streisand
=========

Since Arch is not OpenRC based, and instead uses systemd for services, the setup process for an arch-based server is different, as is the final functionality of the software. Much of the automation process in the streisand setup assumes the system is a debian-based system, so much of the setup is fundamentall incompatible with Arch.

Additionally, Arch's package manager is different, though the yaourt script makes the process of compiling some elements from source much more streamlined. 

Ansible does support pacman natively, but yaourt support is spotty and has issues with the use of sudo in the yaourt script, since the script doesn't execute with sudo and instead asks for sudo sometime later in the runtime. 


### Execution ###
1. Clone the Streisand repository and enter the directory.

        git clone https://github.com/jlund/streisand.git && cd streisand


    ansible-playbook playbooks/streisand.yml

The servers should be accessible using SSH keys, and *root* is used as the connecting user by default (though this is simple to change by updating the streisand.yml file or ansible.cfg file). 


