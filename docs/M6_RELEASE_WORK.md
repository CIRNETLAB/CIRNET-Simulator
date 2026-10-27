# M6 product version work

Date: 2026-10-27. This is current work-unit evidence, separate from historical migration reports.

Python metadata, Contracts dependency, installed-wheel checker, selected-wheel metadata prefix, installer filenames, consumer tests, CI and current documentation target product 0.1.1 and Contracts 0.1.1. DEV remains 1.0.0a1. Backend adapter/plan identity, schema and simulation semantics are unchanged. Historical pre-facade Simulator artifacts that also used 0.1.1 remain distinct by SHA256; rollback must identify the exact payload and matching consumer implementation.

Changed Python/JSON/TOML syntax checks PASS. Installed-artifact/runtime/spawn acceptance is NOT_RUN in this work unit until committed Contracts and Simulator artifacts are rebuilt. No package installations or historical report changes were performed.

Use README bootstrap/locked closure commands, then `python -m build --no-isolation --outdir ABSOLUTE_SESSION/dist`; force-install `netcircuit_simulator-0.1.1-py3-none-any.whl`, run `pip check`, `scripts/check_installed.py --wheel ABSOLUTE_WHEEL`, and external-CWD `python -I -B -m pytest ABSOLUTE_TESTS --basetemp ABSOLUTE_SESSION/pytest`. Preserve exact manifest/digest provenance; no sibling runtime source is needed.

All generated regression fixtures/archives used the shared external allocator session with all six Git roots. Shared-session cleanup remains with the migration owner. No stage/commit/merge/push was performed by this work unit.
