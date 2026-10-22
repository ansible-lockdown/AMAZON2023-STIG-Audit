# Changelog - AMAZON2023-STIG-Audit

## [v1.4.0]

### Based on DISA STIG Amazon Linux 2023 V1R4 (01 July 2026) - benchmark_v1.4.0

Benchmark bump 187 -> 187 (1 added, 1 removed; PDF-verified). Version strings: vars/STIG.yml v1r4, run_audit.sh BENCHMARK_VER 1.4.0, README banner + branch ref v1.4.0.

#### Goss delta
- AZLX-23-001041 (SV-284944, CAT II) ADDED: rsyslog service enabled + running (split out of 001040) - new service goss test + az2023stig_001041 toggle.
- AZLX-23-001280 (FIPS-mode duplicate) REMOVED per V1R4; the FIPS requirement remains covered by AZLX-23-000050. Deleted cat_1/AZLX-23-001280.yml + toggle.
- AZLX-23-001040: dropped the service enabled/running block (now covered by 001041); keeps the rsyslog package check. Rule_ID -> r1208263.
- AZLX-23-002075: encryption driver gtls -> OpenSSL TLS (ossl); exec now greps /etc/rsyslog.conf + /etc/rsyslog.d/ for StreamDriver="ossl" or $DefaultNetstreamDriver ossl; title updated. Rule_ID -> r1210985.
- AZLX-23-002240: audit.rules/auditd.conf mode 0640 -> 0600 (find -perm /137 -> /177). Rule_ID -> r1210984.
- AZLX-23-002350: added /usr/libexec to the system-command group-owner check. Rule_ID -> r1208253.
- AZLX-23-002396: title 15 -> 10 minutes (content already TMOUT=600). Rule_ID -> r1208254.
- AZLX-23-002595: pcscd service -> pcscd.socket (converted service resource to a systemctl is-active pcscd.socket command check); added CCI-004046. Rule_ID -> r1208251.

#### New Alignment Strategy
- run_audit.sh: goss version parse awk '{print $NF}' -> awk 'NR==1{print $NF}' (krameff goss emits a 2-line banner); AUDIT_BIN_MIN_VER 0.4.4 -> 0.4.8; OS detection grep -w VERSION_ID= -> grep "^VERSION_ID="; fixed "does not met" typo.
- README: goss links repointed from goss-org/aelsabbahy to github.com/krameff/goss (availability + goss-documentation).

#### Other Changes
- run_audit.sh: runs syver (github.com/krameff/syver), the signed continuation of the krameff goss fork, which reads this content unchanged. AUDIT_BIN defaults to /usr/local/bin/syver and AUDIT_BIN_MIN_VER moves 0.4.8 -> 0.13.0, so a goss binary now fails the version pre-check. README requirements and links describe syver.
- AZLX-23-002130 (EACCES rule), AZLX-23-002490 and AZLX-23-002495: patterns lacked the closing `/`, so they matched as literal text and never passed. 002490/002495 also expected `rounds=10000` directly after `sha512`; they now accept rounds of 100000 or more anywhere on the `pam_unix.so` password line, the value the check text requires, so the stock Amazon Linux 2023 line (`sha512` after `nullok`) passes once rounds is set.
- AZLX-23-002385: the pattern used `(?#`, which RE2 rejects, so the check errored on every host. It now accepts `enforce_for_root` in pwquality.conf or a drop-in and fails when the line is commented out.
- Metadata now matches the V1R4 XCCDF: 70 meta blocks across 67 controls corrected (CCI placeholders `NA`, missing CCI and Group_Title keys, malformed SRG IDs such as `GPOS-000006`, digit typos `CCI-0001314`/`CCI-0002617`, comma-joined CCIs, and the Vul_ID on AZLX-23-000320 (V-274011) and AZLX-23-001270 (V-283452)).
- Titles: 47 check titles across 37 controls now carry the V1R4 rule title and severity; 22 had no or a malformed severity field, and AZLX-23-002105 named /etc/passwd for the /etc/security/opasswd rule.
- README and LICENSE: the Support section link to the parent company repointed from Tyto Athene at gotyto.com to Quantum Sky at www.quantumsky.com, and the LICENSE copyright line names MindPoint Group - A Quantum Sky Company, following the company rename.
- CONTRIBUTING.rst replaced by CONTRIBUTING.md, the current Ansible-Lockdown contributing guide (approved-contributor pull requests, issues open to everyone, GPG and Signed-off-by on every commit); the README gains a Contributing section pointing at it. Added .gitattributes for GitHub language detection.

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
