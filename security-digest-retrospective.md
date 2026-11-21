# Modern Classics — Quarterly Security Digest

Retrospective on the four supply-chain and coding bugs every developer should know by name.

## Apache Log4j "Log4Shell"

- **CVE:** CVE-2021-44228
- **Database:** [GHSA-jfh8-c2jp-5v3q](https://github.com/advisories/GHSA-jfh8-c2jp-5v3q)
- **Severity:** Critical — CVSS 10.0 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H)
- **First fixed version:** 2.15.0
- **Disclosed:** 2021 (Dec 10, 2021)
- **Authoritative link:** [GitHub Advisory GHSA-jfh8-c2jp-5v3q](https://github.com/advisories/GHSA-jfh8-c2jp-5v3q) · [NVD CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228)
- **Logo:** [Apache Log4j](https://commons.wikimedia.org/wiki/File:Apache_Log4j_Logo.png)

**What to tell your team:** Treat all 2.13.x log4j-core as vulnerable — the fix landed in 2.15.0. Enable autocompleting JDK updates and pin versions explicitly; old log4j versions are still reachable in many dependency trees.

## OpenSSL Heartbleed

- **CVE:** CVE-2014-0160
- **Database:** [GHSA-w8r8-w5w4-4w4v](https://github.com/advisories/GHSA-w8r8-w5w4-4w4v)
- **Severity:** High — CVSS 7.5 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N)
- **First fixed version:** 1.0.1g
- **Disclosed:** 2014
- **Authoritative link:** [GitHub Advisory GHSA-w8r8-w5w4-4w4v](https://github.com/advisories/GHSA-w8r8-w5w4-4w4v) · [NVD CVE-2014-0160](https://nvd.nist.gov/vuln/detail/CVE-2014-0160)
- **Logo:** [OpenSSL](https://upload.wikimedia.org/wikipedia/commons/a/a1/OpenSSL_logo.png)

**What to tell your team:** Upgrade OpenSSL to 1.0.1g or later — the 0.9.8 line is extinct. Replace old 0.9.8 with 1.0.1 or 1.1.1. Block the heartbeat-related TLS support that caused the leak.

## GNU Bash Shellshock

- **CVE:** CVE-2014-6271
- **Database:** [GHSA-6hfc-grwp-2p9c](https://github.com/advisories/GHSA-6hfc-grwp-2p9c)
- **Severity:** Critical — CVSS 9.8 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H)
- **First fixed version:** 4.3
- **Disclosed:** 2014
- **Authoritative link:** [GitHub Advisory GHSA-6hfc-grwp-2p9c](https://github.com/advisories/GHSA-6hfc-grwp-2p9c) · [NVD CVE-2014-6271](https://nvd.nist.gov/vuln/detail/CVE-2014-6271)
- **Logo:** [GNU Bash](https://commons.wikimedia.org/wiki/File:Gnu-bash-logo.svg)

**What to tell your team:** Bash 4.2 and below pass env vars with post-function strings. Call `shopt -s expand_aliases` and use bash 4.3+ for anything installed before 2014; retest any splunk/ssh/cgi configs.

## xz Utils Backdoor

- **CVE:** CVE-2024-3094
- **Database:** [GHSA-rxwq-x6h5-x525](https://github.com/advisories/GHSA-rxwq-x6h5-x525)
- **Severity:** Critical — CVSS 10.0 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H/CHE:E:H)
- **First fixed version:** 5.6.1
- **Disclosed:** 2024
- **Authoritative link:** [GitHub Advisory GHSA-rxwq-x6h5-x525](https://github.com/advisories/GHSA-rxwq-x6h5-x525) · [NVD CVE-2024-3094](https://nvd.nist.gov/vuln/detail/CVE-2024-3094) · [CISA alert](https://www.cisa.gov/news-events/alerts/2024/03/29/reported-supply-chain-compromise-affecting-xz-utils-data-compression-library-cve-2024-3094)
- **Logo:** [XZ](https://upload.wikimedia.org/wikipedia/commons/6/67/XZ_logo_contributed_by_Jia_Tan.png)

**What to tell your team:** Remove the malicious .m4/automake files from build archives and always verify provenance of xz tarballs before use in CI.
