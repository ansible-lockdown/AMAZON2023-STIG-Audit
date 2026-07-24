# Amazon Linux 2023 STIG Goss config

## Overview

### Based on STIG Amazon Linux 2023 Benchmark v1r4 - July 2026

Ability to audit a system using a lightweight binary to check the current state.

This is:

- very small < 14MB
- lightweight
- self contained

It works using a set of configuration files and directories to audit STIG of Amazon Linux 2023 servers. These files/directories correlate to the STIG Level and STIG_ID.

Feedback on any differences between OSs please raise an issue.

## Requirements

You must have [goss](https://github.com/krameff/goss) available to your host you would like to test.

You must have sudo/root access to the system as some commands require privilege information.

Assuming you have already cloned this repository you can run goss from where you wish.

Please refer to the audit documentation for usage.

- [readthedocs](https://ansible-lockdown.readthedocs.io/en/latest/)

This also works alongside the [Ansible Lockdown AMZN2023-STIG role](https://github.com/ansible-lockdown/AMZN2023-STIG)

Which will:

- install
- audit
- remediate
- audit

## Variables

file: vars/STIG.yml

Please refer to the file for all options and their meanings.

The listed variable for every control/benchmark can be turned on/off or section.

- Other controls
  - run_heavy_tasks

- Bespoke options

  If a site has specific options e.g. password complexity these can also be set.

## Branches

If running as part of the ansible playbook, this will pull in the relevant branch for the version of benchmark you are remediating.

- e.g. v1.4.0 will pull in branch benchmark-v1.4.0

Devel is normally the latest benchmark version, so maybe different from the version of benchmark you wish to test.
Details will show in the README as part of the remediation as to the benchmark for the version it is written for.

## Join us

On our [Discord Server](https://www.lockdownenterprise.com/discord) to ask questions, discuss features, or just chat with other Ansible-Lockdown users

## Extra settings

Ability to add your own requirements is available in several sections.

## Support

- [Discord Community Discussions](https://www.lockdownenterprise.com/discord)
- [Enterprise Support](https://lockdownenterprise.com#GH_LockdownReadMe)
- [Tyto Athene](https://gotyto.com)

## Further information

- [goss documentation](https://github.com/krameff/goss/blob/devel/docs/index.md)
- [STIG standards](https://public.cyber.mil/stigs/)
