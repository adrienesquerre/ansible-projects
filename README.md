# Ansible Projects

Overview
    This project contains an Ansible playbook named py_shell_conf_playbook.yml designed to gather information about various Python installations and shell configurations on a local macOS system. It primarily focuses on retrieving details about the System Python and Homebrew Python installations, listing available shells on the system, and fetching .zshrc and .bashrc configuration files if they exist. Tailored for macOS environments and may require adjustments for other operating systems.

Playbook Details
    Hosts: Targets the localhost.
    Privilege Escalation: Uses sudo for privilege escalation.
    Tasks:
    Run Python Info Script with System Python: Executes a custom Python info script using the system Python interpreter and registers the output.
    Run Python Info Script with Homebrew Python: Executes the same script using the Homebrew Python interpreter.
    List all Available Shells: Lists all the available shells in the system.
    Add Descriptions to Shells: Adds descriptions to each shell and outputs them.
    Get .zshrc and .bashrc Files: Attempts to retrieve the contents of .zshrc and .bashrc files for the current user, if they exist.

Configuration File
    The ansible.cfg file contains default settings and configuration options, including paths for remote and local temporary files, vault password file settings, and privilege escalation settings.

Inventory File
    The inventory file specifies the local connection and sets the Python interpreter to the Homebrew Python path.

Usage:
    ansible-playbook -i inventory py_shell_conf_playbook.yml
    To use yaml lint: Library/Python/3.11/bin/yamllint -f parsable .