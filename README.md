# postgresql-vagrant

A Vagrant file to create an environment with postgresql and memcached, to avoid installing them in the system.
It creates a fedora Image, updates it, configures it, and installs and configures memcached and postgresql with users.


# Instructions
- You should have Vagrant and Virtualbox installed
- Clone the repo into a directory
- And also change your users and passwords in the ansible playbook. It will create as many as you need.

Once is configured, go to the directory and execute:

    $ vagrant up

Please configure your application so that it connects to localhost for postgres (i.e development environment in config/database.yml or similar)

    host: localhost

Connect to it in localhost and normal port
