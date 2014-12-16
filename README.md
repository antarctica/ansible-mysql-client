# MySQL Client (`mysql-client`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs MySQL database client and configures password files for users

## Overview

* Installs MySQL client package with python bindings required by ansible.
* Configures `.my.cnf` files for *app* and *controller* users to prevent password prompting.

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Usage

### Requirements

#### BAS Ansible Role Collection (BARC)

* `core`

### Variables

* `mysql_client_controller_user_username`
    * The username of the controller user, used for management tasks, if enabled
    * This variable **must** be a valid unix username
    * Default: "controller"
* `mysql_client_app_user_username`
    * The username of the app user, used for day to day tasks, if enabled
    * This variable **must** be a valid unix username
    * Default: "app"
* `mysql_client_controller_user_password`
    * Default password for controller user.
    * Default: "cacophony-234/877"
* `mysql_client_app_user_password`
    * Default password for app user.
    * Default: "infamous-&34529"
* `mysql_client_user_password`
    * Passwords for users for use in `.my.cnf` files to provide default mysql login credentials.
    * Structured as an array of users and passwords (key, value) respectively
    * Default (array)
        * controller: "{{ mysql_server_controller_user_password }}"
        * app: "{{ mysql_server_app_user_password }}"

## Contributing

This project welcomes contributions, see `CONTRIBUTING` for our general policy.

## Developing

### Committing changes

The [Git flow](https://github.com/fzaninotto/Faker#formatters) workflow is used to manage development of this package.

Discrete changes should be made within *feature* branches, created from and merged back into *develop* (where small one-line changes may be made directly).

When ready to release a set of features/changes create a *release* branch from *develop*, update documentation as required and merge into *master* with a tagged, [semantic version](http://semver.org/) (e.g. `v1.2.3`).

After releases the *master* branch should be merged with *develop* to restart the process. High impact bugs can be addressed in *hotfix* branches, created from and merged into *master* directly (and then into *develop*).

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the BAS Web & Applications Team Jira project ([BASWEB](https://jira.ceh.ac.uk/browse/BASWEB)).

## License

Copyright 2014 NERC BAS. Licensed under the MIT license, see `LICENSE` for details.