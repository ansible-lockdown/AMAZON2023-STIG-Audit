# AMAZON2023 STIG Goss config

## Overview

### Based on STIG Benchmark for AMAZON20203 Benchmark v1r1 - July 2025

[DISA STIG]

This repository is set of configuration files and directories to run the audit of the relevant benchmark of AMAZON 2023 servers

This is configured in a directory structure level.

## variables

file: vars/{benchmark_type}.yml

Please refer to the file for all options and their meanings

The listed variable for every control/benchmark can be turned on/off or section

- Other controls
  - enable_selinux
  - run_heavy_tasks

- Bespoke options

  If a site has specific options e.g. password complexity these can also be set.

## Requirements

- goss >= 0.4.9
- root privileges

## Branches

If running as part of the ansible playbook, this will pull in the relevant branch for the version of benchmark you are remediating.

- e.g. v1.0.0 will pull in branch benchmark-v1.0.0

Devel is normally the latest benchmark version, so maybe different from the version of benchmark you wish to test.
Details will show in the README as part of the remediation as to the benchmark for the version it is written for.

## Usage

Fot the latest information on audit and how it can be used please visit

[Read the Docs - Audit]

## Extra settings

Ability to add your own requirements is available in several sections

## Support

[Discord Community Discussions]

[Enterprise Support]

[Tyto Athene]

## Links and Further information

- [Goss]
  - [Goss documentation]
- [Centre For Internet Security]

<!----
README Links
---->

[Centre For Internet Security]: (https://www.cisecurity.org)
[Read the Docs - Audit]: https://ansible-lockdown.readthedocs.io/en/latest/audit/getting-started-audit.html

[goss documentation]: (https://goss.readthedocs.io/en/stable/)

[Goss]: (https://goss.rocks)
[DISA STIG]: (https://public.cyber.mil/stigs)

[Tyto Athene]: (https://gotyto.com)
[Discord Community Discussions]: https://www.lockdownenterprise.com/discord
[Enterprise Support]: https://lockdownenterprise.com#GH_LockdownReadMe
