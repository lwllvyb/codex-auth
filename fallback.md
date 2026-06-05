# Fallbacks

- `src/cli/login.zig`: Windows `codex-auth login` checks `codex.ps1` only after exhausting `codex.exe` and `codex.cmd`.
  Reason: real npm installs provide `codex.ps1`, and manual testing confirmed `powershell.exe -File codex.ps1 login --help` works.
  Protected callers/data: Windows users whose Codex CLI install exposes only the PowerShell wrapper.
  Remove when: supported Windows Codex installs are guaranteed to provide `codex.exe` or `codex.cmd`.
