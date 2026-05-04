# Changelog - AMAZON2023-STIG-Audit

## [v1.3.0]

### Based on DISA STIG Amazon Linux 2023 V1R3 (01 April 2026) - benchmark_v1.3.0

#### New Goss Tests (4 added)

- AZLX-23-000050: Enable FIPS mode (CAT I)
- AZLX-23-001206: SSH Client ciphers (CAT I)
- AZLX-23-001211: SSH Client MACs (CAT I)
- AZLX-23-001286: DOD-approved encryption in bind package (CAT I)

#### Removed Goss Tests (9 duplicate/redundant controls)

- AZLX-23-001085, 001200, 001260, 001265, 001275
- AZLX-23-002215, 002275, 002560, 002570

#### Severity Upgrades (moved from cat_2 to cat_1)

- AZLX-23-001195, 001205, 001210, 001270, 001285

#### Other Changes

- Updated benchmark_version to v1r3 in vars/STIG.yml
- Updated BENCHMARK_VER to 1.3.0 in run_audit.sh
- Updated vars/STIG.yml toggle variables (187 rules)
- Fixed LICENSE casing: MindPoint (capital P)

#### QA Improvements

- Updated 26 Rule_ID metadata lines to match V1R3 XCCDF revision numbers
- Fixed syslog certificate paths in vars/STIG.yml to match remediation defaults
- Updated README benchmark version v1r2 to v1r3
- Fixed run_audit.sh OS detection for containers (added /etc/os-release fallback)
- Fixed blank line after --- in 5 V1R3 audit test files
- Aligned README with standard audit repo format

---

## [v1.2.0] - 2026-02-27

(Previous changelog entries preserved below)
