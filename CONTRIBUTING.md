# Contributing to goChatHub

Thanks for helping. This guide applies to every repository in the organization.

- **Bugs and ideas:** open an issue using the templates.
- **Security problems:** do not open an issue. See [SECURITY.md](SECURITY.md).
- **Larger changes:** open an issue first so we can agree on the approach.

## Pull requests

1. Branch from `main`.
2. Keep each change small and focused; touch only what the change needs.
3. Add or update tests for any behavior change, and don't disable failing tests.
4. Run the repository's checks (table below) and make sure they pass.
5. Write concise commit messages in bullet form that say what changed and why.
6. Fill in the pull request template.

## The API contract

`gochathub-server/api/openapi.yaml` is the normative contract. The web and
Android clients pin a snapshot of it. A feature that needs a contract change
lands in the server first, then the client snapshot is refreshed in the same
pull request as the client change.

## Checks per repository

| Repository | Run before opening a PR |
| --- | --- |
| `gochathub-server` | `go test ./... -p 1` (needs `TEST_DATABASE_URL`), `python3 scripts/contract-check.py` |
| `gochathub-webui` | `bun run typecheck`, `bun run lint`, `bun test tests/` |
| `gochathub-android-client` | `./gradlew assembleDebug`, `./gradlew checkContract`, `./gradlew :chatuikit-core:testDebugUnitTest` |
| `gochatinstaller` | shell-check `install.sh` and describe how you tested the install |
| `gochathub-rocketchat-migrate` | documentation and backup tooling only; the importer lives in `gochathub-server` (`rcmigrate`) |

## Conduct and license

By taking part you agree to the [code of conduct](CODE_OF_CONDUCT.md). By
contributing you agree your work is licensed under the repository's MIT license.
