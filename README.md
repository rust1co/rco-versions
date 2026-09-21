# RCO Identity Version Metadata

Public version metadata for the RCO Identity update checker.

## Current release

- RCO Identity: `1.7.0`
- rco-appearance: `1.7.0`
- rco-creator: `1.7.0`

## Publishing a new version

When a new release is published, update `version.json`:

1. Change `identity.latest`.
2. Change the versions under `resources`.
3. Change `channels.stable`.
4. Update `releasedAt`.
5. Optionally change `message`.

The in-game checker should be informational only. If this endpoint is unavailable, RCO Identity should continue starting normally.
