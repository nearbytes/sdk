# Nearbytes SDK Fork Notes

This repository is a Nearbytes-maintained fork of the upstream MEGA SDK.

Upstream project:

- https://github.com/meganz/sdk

## Why this fork exists

Nearbytes needs the SDK to accept a native remote-to-local sync mode for restricted incoming MEGA shares.

The key Nearbytes-specific change is to expose and honor `TYPE_DOWN` for this use case while preserving the existing full-access requirement for normal two-way sync.

## Nearbytes-specific changes

This fork carries only the minimum Nearbytes-specific delta needed by the Nearbytes MEGAcmd fork:

- public `TYPE_DOWN` sync enum exposure
- direction-aware syncability validation
- restricted incoming-share roots allowed for `TYPE_DOWN` only
- existing `TYPE_TWOWAY` restrictions preserved

The corresponding consumer-facing CLI change lives in:

- https://github.com/nearbytes/MEGAcmd

## What to read first

For normal SDK build and usage instructions, keep using the existing upstream-style docs in this repository:

- [README.md](README.md)

For the Nearbytes-specific delta, read this file and the linked issue:

- https://github.com/nearbytes/sdk/issues/1

## Release policy

This fork should stay source-first and avoid duplicating upstream SDK documentation.

Preferred maintenance model:

1. Keep upstream-compatible build docs in place.
2. Keep this file short and limited to the Nearbytes delta.
3. Tag source releases that match the Nearbytes MEGAcmd consumer release.