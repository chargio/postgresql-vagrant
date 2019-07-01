# postgresql-vagrant

A Vagrant file to create a database environment with Postgresql in a virtual machine, to avoid installing anything in the system you are running the database. Works in any OS and configures the VM properly.
It creates a CentOS Image, install necessary packages and updates the system to the latest version, and installs and configures postgresql. It also creates databases and users defined in var files.


# Instructions
- You should have Vagrant and Virtualbox installed in your machine (you can use other virtualization engines if you prefer)
- You could use ansible_local if you don't want to install ansible but automatic rebooting does not work.
- Clone the repo into a directory

# Configuration
- Make sure that the ansible playbooks install the proper version of Postgresql and that the config files are those needed by the version you are installing
- Go to scripts/ and update database_users.yaml and databases.yaml with the proper databases and users to create. You can create as many as you need. Django needs the database to be created before using it, while Rails will create the database the first time you execute it.

Once is configured, go to the directory and execute:

    $ vagrant up

Please configure your application so that it connects to localhost for postgres (i.e development environment in config/database.yml or similar)

    host: localhost
    port: 5432

Connect to it in localhost and normal port (5432)


If you change the databases or the user names, or you just want to update the packages, just do:

    $ vagrant up --provision
     
And if you want to destroy the database and start anew, just do

    $ vagrant destroy
    $ vagrant up

