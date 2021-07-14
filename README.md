# Apache Superset Ansible role

![GitHub release (latest by date)](https://img.shields.io/github/v/release/idealista/superset_role?color=%23B62682)
[![Build Status](https://travis-ci.org/idealista/superset_role.png)](https://travis-ci.org/idealista/superset_role) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-idealista.superset_role-B62682.svg)](https://galaxy.ansible.com/idealista/superset_role)

![Logo](https://raw.githubusercontent.com/idealista/superset_role/main/logo.gif)

This ansible role installs [Superset](https://superset.apache.org/) in a Debian environment. It has been tested for Debian buster.

This role has been generated using the [cookiecutter](https://github.com/cookiecutter/cookiecutter) tool, you can generate a similar role that fits your needs using the this [cookiecutter template](https://github.com/idealista/cookiecutter-ansible-role).

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites-ballot_box_with_check)
  - [Installing](#Installing-inbox_tray )
- [Usage](#usage-runner)
- [Testing](#testing-test_tube)
- [Built With](#built-with-building_construction)
- [Versioning](#versioning-card_file_box)
- [Authors](#authors-superhero)
- [License](#license-spiral_notepad)
- [Contributing](#contributing-construction_worker)

## Getting Started

These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will install [Apache Superset](https://superset.apache.org/) in a Debian system.

### Prerequisites :ballot_box_with_check:

Ansible 2.9.x.x version installed.
Inventory destination should be a Debian (preferable Debian 10 Buster ) or Ubuntu environment.

ℹ️ By default this role use the predefined installation of Python that comes with the distro.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver and [Goss](<https://github.com/aelsabbahy/goss>) as verifier.

### Installing :inbox_tray:

Create or add to your roles dependency file (e.g requirements.yml):

```yml
- src: idealista.superset_role
  scm: git
  version: 1.1.0
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

## Usage :runner:

Look to the defaults properties files to see the possible configuration properties, take a look for them:

- [`main.yml`](./defaults/main/main.yml) for superset general purpose vars.
- [`superset_config.yml`](./defaults/main/superset_config.yml) for all the related superset_config.py config parameters.

👉 Don't forget :

- 🦸 To set your Admin user.
- 🔑 To set Secret key.
- 🔑 To set webserver secret key.
- 📝 To set your SUPERSET_HOME and SUPERSET_CONFIG_PATH at your own discretion.
- 📝 To set your installation and config skelton paths at your own discretion.
  - 👉 See `superset_skeleton_paths` in [`main.yml`](./defaults/main/main.yml)
- ⚙️ To customize your app service and superset running config.
- ⚙️ To customize your feature flags.
- ⚙️ To choose your preferred webdriver version in case of use [alerts & reports](https://superset.apache.org/docs/installation/alerts-reports) for example.
- 🐍 Python and pip version, and install before if necessary.
- 🚙 [Custom db drivers](#blue_car-Custom-db-drivers) In addition, superset requires additional drivers to connect to different databases [Supported Databases and Dependecies](https://superset.apache.org/docs/databases/installing-database-drivers).
- 📦 [Additional Python packages](#package-Additional-Python-packages) with version specific like like python-ldap for example to use LDAP login

### :blue_car: Custom db drivers

Choose yours editing the [`superset_db_drivers`](./defaults/main/main.yml) variable, you can see all the default db drivers ready to use (uncomment) in [`main-yml`](./defaults/main/main.yml). It should be a list like this:

```yml
superset_db_drivers:
  - name: ClickHouse
    package:
      - name: clickhouse-driver
        version: 0.2.0
      - name: clickhouse-sqlalchemy
        version: 0.1.6
  - name: MySQL
    package:
        - name: mysqlclient
    required_libs:
      - default-libmysqlclient-dev
      - python-mysqldb
  - name: PostgreSQL
    package:
      - name: psycopg2-binary
```

### :package: Additional Python packages

[`superset_additional_python_packages`](./defaults/main/main.yml) should be a list following this format:

```yml
superset_additional_python_packages:
  # [ LDAP ]
  - name: python-ldap
```

## Testing :test_tube:

### Install dependencies

```sh
pipenv install -r test-requirements.txt
```

For more information read the [pipenv docs](ipenv-fork.readthedocs.io/en/latest/).

### Run test

```sh
pipenv run molecule test
```

## Built With :building_construction:

![Ansible](https://img.shields.io/badge/ansible-2.9.21-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.0.6-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.9-green.svg)

## Versioning :card_file_box:

For the versions available, see the [tags on this repository](https://github.com/idealista/superset_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors :superhero:

- **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/superset_role/contributors) who participated in this project.

## License :spiral_notepad:

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.


## Contributing :construction_worker:

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
