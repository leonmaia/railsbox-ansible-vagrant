# railsbox

Configures a development environment for Ruby on Rails development. It will have the following main components:

- RVM (user_installs) with Ruby 2.1.5
- MySQL
- PostgreSQL
- Node.js
- Bower

You can change the ruby version, just open the playbook.yml and change the
variable {ruby}.

## Vagrant Installation
Install Ansible: http://docs.ansible.com/intro_installation.html

Set this environment variable to your projects folder:
```
export VAGRANT_SYNCED_FOLDER=~/Projects
```
You are good to go, just run:
```
vagrant up --provision
```

## License and Authors
Author:: Leon Maia (hi@leonmaia.com)
