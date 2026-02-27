# Changelog - AMAZON2023-STIG-Audit

## [v1.2.0] - 2026-02-27

#### Rule ID Updates (V1R1 -> V1R2)

- AZLX-23-000130: SV-273999r1119985_rule -> SV-273999r1155171_rule
- AZLX-23-001040: SV-274020r1120048_rule -> SV-274020r1155173_rule
- AZLX-23-001240: SV-274049r1120135_rule -> SV-274049r1120747_rule
- AZLX-23-002290: SV-274121r1120351_rule -> SV-274121r1155161_rule
- AZLX-23-002295: SV-274122r1120354_rule -> SV-274122r1155164_rule
- AZLX-23-002300: SV-274123r1120357_rule -> SV-274123r1155167_rule
- AZLX-23-002500: SV-274164r1120480_rule -> SV-274164r1137695_rule
- AZLX-23-002505: SV-274165r1120483_rule -> SV-274165r1137695_rule
- AZLX-23-002510: SV-274166r1120486_rule -> SV-274166r1155170_rule

#### Content Changes

- AZLX-23-001040: Added service check (enabled + running) in addition to package installed check per V1R2 check-content update.
- AZLX-23-002290: Updated find command to target `*.so*` files specifically. Removed `-L` symlink follow flag. Fixed CCI from CCI-0001499 to CCI-001499.
- AZLX-23-002295: Updated find command to target `*.so*` files specifically. Fixed CCI from CCI-0001499 to CCI-001499.
- AZLX-23-002300: Updated find command to target `*.so*` files specifically.
- AZLX-23-002510: Changed from file content regex (1-900 range) to command check with `grep -i ^StopIdleSessionSec` expecting exactly `600` per V1R2 requirement.

#### New Audit Files

- AZLX-23-001295: Added audit check for PKI-based identity mapping
- AZLX-23-002310: Added audit check for library directories group ownership
- AZLX-23-002625: Added audit check for pam_faillock.so in /etc/pam.d/password-auth
- AZLX-23-002630: Added audit check for pam_faillock.so in /etc/security/faillock.conf

#### Bug Fixes

- Deleted duplicate audit file `cat_2/AZLX-23-002xxx/AZLX-23-002450.yml` (was a copy of AZLX-23-002445 content; correct 002450 file exists in cat_1)
- Added missing toggles to `vars/STIG.yml`: az2023stig_001295, az2023stig_002310, az2023stig_002625, az2023stig_002630
- Added `cat_2/AZLX-23-005000.yml` to `goss.yml` include list
- Fixed README typo `AMAZON20203` -> `AMAZON2023`

#### Metadata

- Updated `benchmark_version` from `v1r1` to `v1r2` in vars/STIG.yml
- Updated `BENCHMARK_VER` from `1.0.0` to `1.2.0` in run_audit.sh
- Updated README benchmark reference to v1r2 - January 2026

### Based on DISA STIG Amazon Linux 2023 V1R2 - 05 January 2026

## [v1.0.0] - 2025-07-14

### Initial Release - Based on DISA STIG Amazon Linux 2023 V1R1
