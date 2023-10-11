# UU CKAN Ansible Playbook

This repository contains an Ansible playbook for building and minimally deploying a [CKAN](https://ckan.org/)-based metadata catalog for Utrecht University.

## Requirements

This Ansible playbook is confirmed to work on the following host operating systems:

- Debian 10
- Ubuntu 21.04
- macOS running on Intel-based processors

The following software is required to make use of the playbook:

- [Python](https://www.python.org/)
- [pip](https://pip.pypa.io/en/stable/)
- [Ansible](https://ansible.com) 
- [PostgreSQL collection for Ansible](https://galaxy.ansible.com/community/postgresql) 
- [Vagrant](https://www.vagrantup.com)
- [VirtualBox](https://www.virtualbox.org/) 

Furthermore, an SSH key pair should be placed in the `provisioning/files/`
directory. The filenames of the keypair files must begin with `id_` (e.g. `id_rsa` + `id_rsa.pub`).

## Installation & Setup

- Download the respository to your computer using `git clone`:

```
git clone git@github.com:UtrechtUniversity/uu-ckan-ansible.git
```

- The downloaded repository should contain the following folder structure at minimum: 

```
uu-ckan-ansible
├── .gitignore
├── LICENSE.md
├── README.md
├── Vagrantfile
└── provisioning
    ├── files
    └── main.yml
```

- If you will not be committing to the `uu-ckan-ansible` repository, please delete the `.git` folder that may have been downloaded as part of the repository contents.

- Copy the SSH keypair to the `provisioning/files/` directory. The `.gitignore` file should ensure the keys remain untracked and cannot be pushed to GitHub, but it would be good to double-check. 

## Usage

1. Navigate to the `uu-ckan-ansible` directory

```
cd uu-ckan-ansible
```

2. Start a vagrant environment, which creates and configures guest machines according to the Vagrantfile.

```
vagrant up
```

3. You can now access the CKAN environment at http://uu-ckan.test (the credentials for the default administrative user are: `admin:password`)

4. To log into the virtual machine using SSH, run:

```
vagrant ssh
```

5. To stop the machine, run:

```
vagrant halt
``` 

or 

```
vagrant suspend
```

This can also be done via VirtualBox if required.

6. To delete all the contents of the machine and clean up, you can use:

```
vagrant destory
```

This can also be done via VirtualBox.

## Support

While the project is ongoing, you can contact Neha Moopen and/or Pascal Pas for support. Issues can also be opened on the GitHub repository.

## Roadmap

- This repository is being developed alongside the uu-ckan-config and uu-ckan-theme repositories.

- Once the repositories are up-to-date, we hope to implement a CKAN catalog for the strategic theme, Dynamics of Youth as first use-case.

- We have not figured out how to run the VM on a Windows host machine, this could be something for the Roadmap.

## Contributing

Contributions are welcome in the form of feedback or pull requests!

## Authors & Acknowledgement

- Pascal Pas
- Neha Moopen
- Laurens Samshuijzen
- Jelmer Zondergeld

The project is supported by a grant awarded by the FAIR Research IT Program at Utrecht University and builds upon previous efforts in deploying CKAN at UU, specifically the EPOS & CD2 projects.

## License

This project is licensed under the GNU AFFERO GENERAL PUBLIC LICENSE

## Project Status

Ongoing as of 2023-03-01