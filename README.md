# Home Assistant Family Routines

Animated Morning Missions and Nighttime Routine dashboards for a landscape wall display.

## Status

Private source archive in preparation. Dashboard source was recovered from the November 5, 2026 configuration snapshot. Morning backend is included; the original nighttime backend and screenshots are pending retrieval. **This is not yet a complete installable release.**

Names and entity IDs are anonymized as `child_one`, `child_two`, and `child_three`. Replace these consistently with your own identifiers before installing on an existing system. No Home Assistant hostnames, credentials, webhook URLs, device data, or unrelated dashboard sections are included.

## Features

- Morning checklist: brush teeth, breakfast, get dressed, socks/shoes, brush hair, and go potty.
- Per-child daily animation choice: a fixed favorite or Surprise.
- Animated task progression, including a hatching dragon that flies when complete.
- Weekly stars and daily task reset logic.
- Morning countdown with “Finish up!” and “Time to go!” stages.
- Settings shortcut to the hidden Animation Preview view.
- Nighttime checklist: bath, pajamas, brush teeth, go potty, and bedtime bravery.
- Five-point star progress and nighttime completion animation.

## Files

- `dashboard.yaml`: the three routine views only. Extracted from the existing dashboard snapshot; unrelated Home, weather, laundry and note cards are excluded.
- `morning_missions_package.yaml`: recovered morning helper, automation and script package.

## Dependencies and installation notes

Home Assistant and the community `custom:button-card` frontend resource are required. This is a YAML dashboard/package project, not a custom integration or HACS-installable repository.

Back up the target dashboard and packages first. For an existing installation, do not add a second copy of helpers or automation IDs. Merge deliberately. The dashboard navigation paths currently use `/wall-tab/...`; change these if your dashboard URL differs. Its Home button assumes a Home view in that dashboard, which is not included here.

The morning package is intended for Home Assistant's packages configuration. Review your existing `homeassistant: packages:` include before placing a package file under `/config/packages/`. Run Home Assistant's configuration validation and reload/restart only as required by the changed helper types. Use the dashboard raw editor to merge these views rather than replacing unrelated views.

The animation preview depends on `input_number.morning_preview_*_step` helpers. The recovered morning package includes the dragon helper, but the earlier preview helper definitions must also be recovered before a fresh installation is complete. The original nighttime helper/automation package is likewise required.

## Validation limits

Recovered YAML parses successfully. This archive has not been installed into a fresh Home Assistant instance. Existing behavior and history are not a substitute for fresh-install testing. Review entity references and navigation paths before use.
