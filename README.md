# Amazon Linux 2023 STIG Syver config

## Overview

### Based on STIG Amazon Linux 2023 Benchmark v1r5 - September 2026

Ability to audit a system using a lightweight binary to check the current state.

This is:

- very small < 14MB
- lightweight
- self contained

It works using a set of configuration files and directories to audit STIG of Amazon Linux 2023 servers. These files/directories correlate to the STIG Level and STIG_ID.

Feedback on any differences between OSs please raise an issue.

## Requirements

You must have [syver](https://github.com/krameff/syver) >= 0.13.0 available to the host you would like to test. The audit content uses the goss file format, which syver reads unchanged.

You must have sudo/root access to the system as some commands require privilege information.

Assuming you have already cloned this repository you can run syver from where you wish.

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

- e.g. v1.5.0 will pull in branch benchmark_v1.5.0

Devel is normally the latest benchmark version, so maybe different from the version of benchmark you wish to test.
Details will show in the README as part of the remediation as to the benchmark for the version it is written for.

## Join us

On our [Discord Server](https://www.lockdownenterprise.com/discord) to ask questions, discuss features, or just chat with other Ansible-Lockdown users

## Extra settings

Ability to add your own requirements is available in several sections.

## Support

- [Discord Community Discussions](https://www.lockdownenterprise.com/discord)
- [Enterprise Support](https://lockdownenterprise.com#GH_LockdownReadMe)
- [Quantum Sky](https://www.quantumsky.com)

## Contributing

Bug reports and feature requests are welcome from everyone, please raise an issue.

Pull requests are accepted from approved contributors only. To be onboarded, join the [Discord Server](https://www.lockdownenterprise.com/discord) and request contributor access. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full process.

## Further information

- [Syver documentation](https://github.com/krameff/syver/blob/main/docs/index.md)
- [goss vs Syver](https://github.com/krameff/syver/blob/main/docs/goss-vs-syver.md)
- [STIG standards](https://public.cyber.mil/stigs/)
