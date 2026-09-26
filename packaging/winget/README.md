# winget — first submission

The `update-winget.yml` workflow uses [`vedantmgoyal9/winget-releaser`][wr] to
open update PRs against `microsoft/winget-pkgs`. That action only works for
**existing** manifests. The first version must be submitted manually.

[wr]: https://github.com/vedantmgoyal9/winget-releaser

## One-time: submit the initial manifest

1. Install [`wingetcreate`][wc] on a Windows machine.
2. Run:
   ```powershell
   wingetcreate new `
     --urls "https://github.com/MelekCreed/Hydra-Agent-Orchestrator/releases/download/v0.2.32/hydra-0.2.32-x64.exe" `
     --version 0.2.32
   ```
3. Fill in the prompts — use `MelekCreed.Hydra` as the PackageIdentifier.
4. Submit the PR. Once merged, every subsequent release will be auto-PRed by
   `update-winget.yml`.

[wc]: https://github.com/microsoft/winget-create

## Required metadata

| Field | Value |
|---|---|
| PackageIdentifier | `MelekCreed.Hydra` |
| Publisher | `MelekCreed` |
| PackageName | `Hydra` |
| License | `MIT` |
| ShortDescription | Orchestrate Claude Code and OpenAI Codex CLI agents in parallel |
| Homepage | https://github.com/MelekCreed/Hydra-Agent-Orchestrator |
| InstallerType | `nullsoft` |
| Architecture | `x64` |
