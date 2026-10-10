# RCO Identity Version Metadata

Public version metadata for the RCO Identity update checker.

RCO Identity is released as a single package: `rco-appearance` and `rco-creator` must use the same version.

## Current release

- RCO Identity: `2.0.4`
- Minimum supported version: `1.7.0`

## Publishing a new version

When a new release is published, update `version.json`:

1. Change `identity.latest`.
2. Change `channels.stable`.
3. Update `releasedAt`.
4. Optionally change `message`.

Only `rco-creator` performs the remote version request. It also compares the local `rco-creator` and `rco-appearance` manifest versions and warns when the installed package is mixed.

The checker is informational only. If this endpoint is unavailable, RCO Identity continues starting normally.

## RCO Vehicles

Entry `vehicles` in `version.json`, read by `rco-vehicles` (`server/version_check.lua`) at server start. On each
release of `rco-vehicles`, change `vehicles.latest` to the `version` of its `fxmanifest.lua`, update `releasedAt` and,
optionally, `message` (shown in the console when an update is available). Below `vehicles.minimum` the notice is red.
