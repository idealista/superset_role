# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/) and [Keep a changelog](https://github.com/olivierlacan/keep-a-changelog).

## [Unreleased](https://github.com/idealista/superset_role/tree/develop)
### :hammer_and_wrench: Fixed
- *[#21] Fix sql lab error* @jmonterrubio

## [1.2.1](https://github.com/idealista/superset_role/tree/1.2.1) (2021-07-13)

[Full Changelog](https://github.com/idealista/superset_role/compare/1.2.0...1.2.1)

### :arrows_clockwise: Changed

- Update default superset install version to [1.2.0](https://github.com/apache/superset/releases/tag/1.2.0)

### :hammer_and_wrench: Fixed

- Fix wrong email configuration in molecule default scenery
- Fixed versions of `celery` and `flower` because newer versions broke superset installation
- Fix pip build problems

## [1.2.0](https://github.com/idealista/superset_role/tree/1.2.0) (2021-07-01)

[Full Changelog](https://github.com/idealista/superset_role/compare/1.1.1...1.2.0)

### :heavy_plus_sign: Added

- Option to add custom imports in superset_config.py

### :hammer_and_wrench: Fixed

- Fix typo missing quotation for mapbox token in superset_config template
- Use auth user registration when defined (no boolean evaluated)

## [1.1.1](https://github.com/idealista/superset_role/tree/1.1.1) (2021-06-24)

[Full Changelog](https://github.com/idealista/superset_role/compare/1.1.0...1.1.1)

### :hammer_and_wrench: Fixed

- Fix template path name for celery-flower service

## [1.1.0](https://github.com/idealista/superset_role/tree/1.1.0) (2021-06-21)

[Full Changelog](https://github.com/idealista/superset_role/compare/1.0.1...1.1.0)

- Many (good) changes

### :heavy_plus_sign: Added

- .gitattributes
- templates for service and  profile env set
- option to install firefox and geckodriver
- superset_config.py fully parametizable with ansible vars

### :arrows_clockwise: Changed

- tuned .gitignore
- tuned .yamllint
- bump Pipfile requirements
- Bump test-requirements
-  Realocated group_vars main.yml
- Add, remove and modificated vars main.yml
- Set needed molecule converge yml environment vars
- Updated Dockerfile to remove unnecessary exposed ports
- Updated molecule verify.yml with updated group_vars path
- Updated molecule vars for default scenario
- Updated molecule tests vars
- Update and renew config tasks (e.g: user creation)
- Install tasks reviewed and updated as we need
- Service tasks refactored
- Some task now are handlers for be more correct
- Service template refactored
- Superset_config python file template mega refactor
- Bump Changelog

### :hammer_and_wrench: Fixed

- Fix typo README.md

### :arrows_clockwise: Changed

- Install new 1.0 superset version
- superset_config.py template updated

### :heavy_plus_sign: Added

- New vars for SIP-15, emailing, chrome, etc.
- Some new tasks and checks
- Install chrome and chormedriver for reports

## [1.0.1](https://github.com/idealista/superset_role/tree/1.0.0) (2020-10-28)

[Full Changelog](https://github.com/idealista/superset_role/compare/1.0.0...1.0.1)

### :hammer_and_wrench: Fixed

- *[#3](https://github.com/idealista/superset_role/issues/3)* Fix updating config files @frantsao

## [1.0.0](https://github.com/idealista/superset_role/tree/1.0.0) (2020-10-19)

### :heavy_plus_sign: Added

- *First release* @ultraheroe
