# Security Policy

Sentrya Fuseline is a security project, so we take vulnerability reports
seriously and handle them privately until a fix or mitigation is available.

## Project status

Fuseline is currently in the **design phase**. There are no released
versions yet, and therefore no supported versions.

| Version | Supported |
|---|---|
| No releases yet | — |

This table will be updated with the first release.

## What to report

Please report:

- Flaws in Fuseline's hardened profiles that leave a protection disabled,
  weakened or misconfigured when the documentation says otherwise.
- False results from the audit tool (a protection reported as enabled when
  it is not, or vice versa).
- Errors in the provisioning guide that could expose keys or leave a device
  in an insecure or unrecoverable state.
- Errors or omissions in the threat model.
- Any vulnerability in Fuseline's own code or tooling.

Out of scope for this policy:

- Hardware vulnerabilities in ESP32-family chips and vulnerabilities in
  ESP-IDF itself. Please report these to Espressif through its official
  product security channel. If you are unsure whether an issue belongs to
  Fuseline or upstream, report it to us and we will help route it.
- Vulnerabilities in application code built by users on top of Fuseline.

## How to report a vulnerability

**Do not open a public issue, discussion or pull request for a suspected
vulnerability.**

Preferred channel — **GitHub private vulnerability reporting**:

1. Go to the **Security** tab of this repository.
2. Select **Advisories**, then **Report a vulnerability**.

Alternative channel — email: **[SECURITY_EMAIL]**

Please include, where possible:

- The affected component, file or document, and the commit or version.
- The chip, chip revision and ESP-IDF version involved.
- A description of the impact.
- Steps to reproduce, or a proof of concept.
- Any suggested mitigation.

Do not include credentials, private keys or personal data in your report.

## What to expect

Fuseline is maintained by a small team. We commit to the following targets:

| Step | Target |
|---|---|
| Acknowledgement of your report | Within 5 business days |
| Initial assessment | Within 14 days |
| Coordinated public disclosure | Within 90 days of the report, or earlier once a fix is available |

If we cannot meet a target, we will tell you and explain why.

When a vulnerability is confirmed, we will:

1. Work on a fix privately, inviting you to collaborate if you wish.
2. Coordinate with Espressif when the issue also involves ESP-IDF or
   Espressif hardware.
3. Publish a security advisory on this repository, requesting a CVE
   identifier where appropriate.
4. Credit you in the advisory, unless you prefer to remain anonymous.

## Safe harbor

We will not pursue or support legal action against researchers who act in
good faith, follow this policy, avoid harming users or their data, and give
us reasonable time to respond before any public disclosure.

<!-- Review note: the safe harbor wording above should be reviewed by
qualified legal counsel before publication. -->
