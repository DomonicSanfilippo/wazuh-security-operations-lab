# Publication and secret-safety checklist

Run this checklist before every public release.

## Do not publish

- Wazuh enrollment keys, `client.keys`, passwords, API tokens, certificates, or private keys.
- Raw Wazuh configuration copied from a live system without review.
- VM images, disk files, snapshots, or ISO files.
- Raw logs, dashboard exports, packet captures, or terminal history.
- Private network addresses, host names, user names, dashboard URLs, browser tabs, or personally identifying information in screenshots.
- Any employer, customer, household, or school data.

## Required review

1. Search the repository for `password`, `token`, `secret`, `key`, `192.168`, `10.`, `172.16`, `@`, and known user or host names.
2. Inspect every image at full size for browser address bars, IP addresses, usernames, timestamps, and tabs.
3. Confirm screenshots are cropped or redacted and label them as sanitized where applicable.
4. Confirm every capability is marked **Implemented**, **Validated**, **Planned**, or **Not demonstrated** accurately.
5. Run `git status --ignored` and verify no excluded sensitive material was force-added.
6. Obtain explicit approval before changing repository visibility or pushing to a public remote.

## Disclosure process

If sensitive content is committed, stop public sharing, remove the material from the remote history, rotate affected credentials, and review any exposed configuration.
