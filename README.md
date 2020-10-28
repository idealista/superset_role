# Superset Ansible role

![Logo](https://raw.githubusercontent.com/idealista/superset_role/main/logo.gif)

[![Build Status](https://travis-ci.org/idealista/superset_role.png)](https://travis-ci.org/idealista/superset_role)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-idealista.superset_role-B62682.svg)](https://galaxy.ansible.com/idealista/superset_role)

This ansible role installs [Superset](https://superset.apache.org/) in a Debian environment. It has been tested for Debian buster.

This role has been generated using the [cookiecutter](https://github.com/cookiecutter/cookiecutter) tool, you can generate a similar role that fits your needs using the this [cookiecutter template](https://github.com/idealista/cookiecutter-ansible-role).

- [Getting Started](#getting-started)
  - [Prerequisities](#prerequisities)
  - [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started

These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will install Superset in a Debian system.

### Prerequisities

Ansible 2.9.x.x version installed.

Molecule 3.x.x version installed.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver and  [Goss] (<https://github.com/aelsabbahy/goss>) as verifier.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

```yml
- src: idealista.superset_role
  version: 1.0.1
  name: superset_role
```

Install the role with ansible-galaxy command:

```sh
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```yml
---
- hosts: someserver
  roles:
    - role: superset_role
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties, it is very likely that you will not need to override any variables.

Don't forget to override `superset_admin_user` with more secure values and the `superset_flask_app_secret_key` (superset_config.py `SECRET_KEY`) to follow the [superset configuration](https://superset.apache.org/docs/installation/configuring-superset)

In addition, superset requires additional drivers to connect to different databases [Supported Databases and Dependecies](https://superset.apache.org/docs/databases/installing-database-drivers). We left activated the most common drivers for us (MySQL, Oracle, PostgreSQL and Clickhouse). Choose yours editing the `superset_db_drivers` variable

## Testing

### Install dependencies

```sh
pipenv sync
```

For more information read the [pipenv docs](ipenv-fork.readthedocs.io/en/latest/).

### Run test

```sh
pipenv run molecule test
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.9.9-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.0.4-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.9-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/superset_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

- **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/superset_role/contributors) who participated in this project.

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
