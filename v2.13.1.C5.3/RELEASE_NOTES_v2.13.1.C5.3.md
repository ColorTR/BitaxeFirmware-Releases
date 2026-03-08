# Release Notes - v2.13.1.C5.3

Date:
- 2026-03-08 Europe/Bucharest

Scope:
- Follow-up UI/runtime release on top of `v2.13.1.C5.2`
- Focused on AutoTune session persistence, BestVF state clarity, and safer overclock defaults

Highlights:
- Settings now defaults to overclock disabled on page load
  - even if NVS previously reported overclock enabled
  - user must explicitly enable it again from the UI
- AutoTune `Best VF Active` display now reflects actual Auto BestVF maintenance mode
  - tuning-in-progress no longer shows a misleading active BestVF state
- AutoTune recent-session persistence now runs from an app-level background monitor
  - completed terminal sessions are recorded even if the user leaves the AutoTune page
- Stopping BestVF maintenance after a completed run no longer overwrites the already-captured `done` session
- Previous UI polish from the same branch remains intact:
  - equalized Home `AutoTune Live Status` spacing
  - opaque dark dropdown surfaces for locked `MHz` / `mV` controls

Validation:
- Angular unit tests passed (`49/49`)
- production build passed
- local UI verification passed on:
  - Home
  - Settings
  - AutoTune-related routes

Deploy:
- Built and OTA deployed through VPS path using the canonical runbook
- Device verified after deploy:
  - `version`: `v2.13.1.C5.3`
  - `axeOSVersion`: `v2.13.1.C5.3`
  - `overclockEnabled`: `0`
  - device returned to active mining after reboot

Related deploy report:
- `/Users/colortr/Downloads/aaa_fork/BitaxeFirmware_HIGHRISK_C5_2_20260308_022745/project_meta/reports/DEPLOY_REPORT_20260308_031037.md`
