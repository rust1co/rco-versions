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

## Rules for every entry

- `latest` is the version customers can download now. Change it only when that package is on CFX, never on a
  development commit.
- `message` is the note of that one version, one or two sentences. Replace it on each release; never add the new note
  in front of the old ones. The checker prints the whole field in the server console.

## RCO Vehicles

Entry `vehicles` in `version.json`, read by `rco-vehicles` (`server/version_check.lua`) at server start. On each
release of `rco-vehicles`, change `vehicles.latest` to the `version` of its `fxmanifest.lua`, update `releasedAt` and,
optionally, `message` (shown in the console when an update is available). Below `vehicles.minimum` the notice is red.

## RCO Gym

Entry `gym` in `version.json`, read by `rco-gym` (`server/version_check.lua`) at server start. On each release of
`rco-gym`, change `gym.latest` to the `version` of its `fxmanifest.lua`, update `releasedAt` and, optionally,
`message` (shown in the console when an update is available). Below `gym.minimum` the notice is red.
