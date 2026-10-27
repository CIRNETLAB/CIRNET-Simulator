# Simulator verification

Use the exact Contracts 1.0.1 and DEV 1.0.0a1 wheel artifacts selected by SHA256. scripts/bootstrap_contract_tools.py, artifact_download.py, contracts_artifact.py and allocator adapters originate from Remote revision 25d2e6784035f6a8165142f8a8e03c4534512bcc. The canonical allocator implementation belongs exclusively to the installed DEV artifact; these adapters validate and delegate to it.

Set NETCIRCUIT_ARTIFACTS_CONTEXT before bootstrap when several repositories participate. The JSON object contains an owner and every participating absolute Git root. Standalone verification defaults to this repository only. Keep the identical context for children and cleanup.

Bootstrap writes the ownership/session to GITHUB_ENV immediately after allocation so CI can clean even after installation failure. Capture all local command output under that owned session. Do not run pytest with cacheprovider or default source-local temporary output. Build caches are compiler output; diagnostics are always external.

Run tests against the built wheel from an external working directory using `python -I -m pytest --import-mode=importlib ABSOLUTE_TESTS --basetemp OWNED_SESSION/pytest`. `scripts/check_installed.py --wheel ABSOLUTE_NEWLY_BUILT_WHEEL` binds verification to the selected archive SHA256, payload and original RECORD entries. Always force reinstall when rebuilding the same package version. The checker also rejects editable installs, source shadowing and modified RECORD-owned payloads. It verifies the installed Contracts resource owner as well. Runtime source must not enter PYTHONPATH.

Check the wheel inventory (exactly nine runtime modules, including the unchanged eight legacy modules plus distribution metadata), sdist fixture/tooling presence, dependency closure with `pip check`, and fresh installation without source/editable dependencies. Worker lifecycle, REST preview and Hardware virtual integration stay in Remote.

After inspecting diagnostics and verifying owned child processes exited, clean only this session using `node scripts/artifact-paths.mjs --cleanup ABSOLUTE_SESSION`. Never remove an arbitrary parent or another session. Preserve shared integration sessions for their owner to clean. No full browser result or physical hardware availability follows from these package tests.


Backend verification additionally covers legacy compile/run/preview parity, permissive unsupported previews, truthful ngspice unavailability without native launch, trusted provider delegation, immutable identity/directions/registry snapshots, source-independent pickle/spawn execution, and rejection of missing/mismatched providers without fallback. The current Hardware composition permits built-ins only; custom extension tests compose a trusted registry explicitly in the child. Preserve the reviewed0.1.1 baseline artifacts while validating0.2.0; no native integration or analog capability is established by these tests.
