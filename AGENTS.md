# Agent operating rules — ESPSomfy-RTS
Effective: 2026-11-08

## Git-first workflow and release completion
- Inspect upstream/vendor status, current code, repository history, local checkout and deployment before making changes. Preserve upstream attribution and do not assume this fork is the production firmware.
- Work on topic branches with reviewed PRs and tests. A merged PR is not a deployed firmware release.
- Record target commit SHA, board/device identity, build version, affected paths, backups, rollback and configuration/flash safeguards. Compare live or local changes against target blobs before updating; do not blindly pull, reset --hard, clean, force push or auto-stash/pop.
- After firmware deployment verify local checkout HEAD and build source match the approved commit, firmware build identity and device version are confirmed, and RF control/awning safety tests pass. If no device was flashed, mark DEPLOYED and VERIFIED as NOT APPLICABLE.
- Never disrupt wind protection or motor limits to test a Git workflow. Protect keys, device secrets, RF capture payloads and local configuration.
- Keep diagnostics in an approved persistent directory, not /tmp. Stop on any failed command; record distinct COMMITTED, MERGED, DEPLOYED, RECONCILED and RUNTIME_VERIFIED states.
- This rule prevents the 2026-11-08 HomeAssistant failure in which targeted live file copies left the local checkout six commits behind GitHub.
