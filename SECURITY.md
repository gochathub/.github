# Security policy

## Reporting a vulnerability

Please report security issues **privately**. Do not open a public issue, pull
request or discussion.

1. Open the affected repository's **Security** tab.
2. Choose **Report a vulnerability**.
3. Describe the issue.

Please include:

- the repository and version or commit
- steps to reproduce, or a proof of concept
- the impact you expect (data exposure, account takeover, denial of service, ...)
- any suggested fix

Do not include real user data, credentials or tokens. Redact them.

If a repository has no **Report a vulnerability** button, open a public issue
that says only "security contact requested" with no details, and a maintainer
will arrange a private channel.

## Scope

All repositories in this organization, with the most attention on
`gochathub-server` (authentication, sessions and tokens, attachments, push,
webhooks, the optional Rocket.Chat bridge) and the clients that talk to it.

## Supported versions

Only the latest release and `main` receive security fixes.

## What to expect

Reports are acknowledged on a best-effort basis. Fixes are developed privately
and disclosed through a GitHub security advisory once a patched release is
available. Please give us reasonable time to fix an issue before disclosing it.

Good-faith research that avoids privacy violations, data destruction and
service disruption is welcome.
