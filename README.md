# Ansible Playbook for Temple University Libraries Oral Histories Hydra Application

## Requirements
* Ansible 2.0 or greater

### For local development, you also need:
* VirtualBox
* Vagrant


### Running locally

Clone this repository locally

`git clone https://github.com/tulibraries/tul_ohist_playbook`

`cd tul_ohist_playbook`

Next, prepare the ansible playbook by installing required roles.

`ansible-galaxy install -r required-roles.yml`

Set up the the ansible-vault password file. This is used to encrypt/decrypt sensitive data in the playbook.

`echo [VAULT PASSWORD SUPPLIED ELSEWHERE] > ~/.vault`

Then run the vagrant command to build your local dev machine and deploy the software.

`vagrant up`

This will download the vagrant base box, and run the ansible playbook. When it completes after about 10 minutes you should have a working tul_cdm app, available at [http://localhost:8180/oralhistories](localhost:8180/oralhistories). However, it will still be empty until you harvest some collections.

You can log into the server with `vagrant ssh` when yuo are in the project's root directory on your host machine. 

On the vagrant box, the application is installed at `/var/www/tul_ohist`.