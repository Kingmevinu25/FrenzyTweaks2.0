# Frenzy Tweaks v2.0 — Premium Centers (development build)

## Included
- Original v1.7 application, cleanup tools, and loader preserved.
- New standalone **Cleanup Center** sidebar page linking to existing Discord/Steam/Epic and Windows cache pickers.
- New **Restore Center** sidebar page linking to Windows System Restore and the existing service/task restoration dialogs.
- Purple accent on the home/debloat pages, refreshed bold home subtitle, 5-second telemetry interval.
- Post-operation summary with real successful, failed, and skipped counts.
- The existing activity log, GPU display, controls, Discord contact, and other tabs remain.

## Limitations (important)
This is a source-level incremental UI update, **not** a complete implementation of every feature discussed. It does not add a standalone NVIDIA Profile Inspector importer, automatic gaming profiles, hardware-validated FPS benchmarking, search across every page, favorites, full universal rollback, asynchronous execution of all Windows commands, or a comprehensive notification/animation system. Existing service/task and network operations can still block the UI. The loader is retained from v1.7 and still requires Windows validation. Do not distribute this build as fully tested.

## Run locally
Keep FrenzyTweaks.ps1 and FrenzyApp.ps1 together, open Windows PowerShell in the extracted folder and run:

    powershell.exe -NoProfile -STA -ExecutionPolicy Bypass -File ".\FrenzyTweaks.ps1"

The loader uses the adjacent local FrenzyApp.ps1 when launched from disk. Test UI/navigation before applying any system changes.

## Update GitHub (main branch)
1. Back up the existing FrenzyTweaks.ps1 and FrenzyApp.ps1 files in your repository.
2. On GitHub, open Kingmevinu25/Frenzy-Extreme-Panel and select main.
3. Replace **FrenzyTweaks.ps1** and **FrenzyApp.ps1** at the repository root with the files in this ZIP. Commit both changes.
4. The existing irm .../FrenzyTweaks.ps1 | iex command will download the updated loader. The loader fetches FrenzyApp.ps1 from the same repository.
5. For a reliable test, close existing app instances and inspect %ProgramData%\FrenzyTweaks\loader.log if startup fails.

## Testing
Static source changes and file packaging only. PowerShell 5.1/WinForms runtime, elevation, loader handoff, and system changes have NOT been tested on Windows. Some older UI handlers still use synchronous work.

## Rollback
Restore the two backed-up scripts from GitHub history, or revert the commit. Windows System Restore is available from Restore Center for supported restore points. Individual service/task changes can be restored using their dialogs if previous states were recorded. Do not assume all other tweaks have automatic rollback.
