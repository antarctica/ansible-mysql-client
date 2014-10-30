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

## Branches

This project uses three permanent branches with the *Git Flow* branching model managing the interaction between branches.

* **Develop:** unstable, potentially non-working but most current version of roles. Bug fixes and features interact with this branch only.
* **Master:** stable, tested, working version of role with full documentation. Releases and hot fixes mainly interact with this branch. This branch should when consuming roles internally.
* **Public:** equivalent to the *master* branch, but available externally. Some configuration details may be altered or features removed to make available for public release.

## Testing

Manual testing is performed for all roles to ensure roles achieve their aims and this forms a prerequisite task for merging changes into the *master* and *public* branches.
Wherever possible testing is as complete as possible meaning tasks such as downloading dependencies are performed as part of each test.

## Issues

Please log issues to the [BAS Web and Applications Team](https://jira.ceh.ac.uk/browse/BASWEB) project in Jira, within the *Project - Ansible Roles* component.

If outside of NERC please get in touch to report any issues.

## Contributions

We have no formal contribution policy, if you spot any bugs or potential improvements please submit a pull request or get in touch.

These roles are used for internal projects which may dictate whether any contributions can be included.

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### BAS Ansible Role Collection (BARC)

* `core`

## Variables

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

## Changelog

### 0.2.1 - October 2014

* Including in BARC
* Updating dependencies
* App and controller user usernames now configurable using variables
* Fixing variable documentation
* Preparing for public release

### 0.2.0 - August 2014

* Adding user connection files for streamlining database access from the command line

### 0.1.1 - August 2014

* Migrating role into BARC - this version should be a drop in replacement for any previous versions of this role

### 0.1.0 - August 2014

* Initial version
