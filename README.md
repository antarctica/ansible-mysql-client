# MySQL Client (`mysql-client`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs MySQL database client and configures password files for users

## Overview

* Installs MySQL client package with python bindings required by ansible.
* Configures `.my.cnf` files for *app* and *controller* users to prevent password prompting.

## Author

[British Antarctic Survey](http://www.antarctica.ac.uk) - Web & Applications Team

Contact: [basweb@bas.ac.uk](mailto:basweb@bas.ac.uk).

## Availability

This role is designed for internal use but if useful can be shared publicly.

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### BAS Ansible Role Collection (BARC)

* `core`

## Variables

* `mysql_server_controller_user_password`
* `mysql_client_controller_user_username`
    * The username of the controller user, used for management tasks, if enabled
    * This variable **must** be a valid unix username
    * Default: "controller"
* `mysql_client_app_user_username`
    * The username of the app user, used for day to day tasks, if enabled
    * This variable **must** be a valid unix username
    * Default: "app"
    * Default password for controller user.
    * Default: "cacophony-234/877"
* `mysql_server_app_user_password`
    * Default password for app user.
    * Default: "infamous-&34529"
* `mysql_client_user_password`
    * Passwords for users for use in `.my.cnf` files to provide default mysql login credentials.
    * Structured as an array of users and passwords (key, value) respectively
    * Default (array)
        * controller: "{{ mysql_server_controller_user_password }}"
        * app: "{{ mysql_server_app_user_password }}"

## Changelog

### 0.2.1 - October 2014

* Including in BARC
* Updating dependencies
* App and controller user usernames now configurable using variables

### 0.2.0 - August 2014

* Adding user connection files for streamlining database access from the command line

### 0.1.1 - August 2014

* Migrating role into BARC - this version should be a drop in replacement for any previous versions of this role

### 0.1.0 - August 2014

* Initial version
