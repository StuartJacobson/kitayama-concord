# Working on the Kitayama Concord

The repository root is the mod root. `in_game` contains game scripts and
interface definitions; `main_menu` contains localization and graphics;
`.metadata/metadata.json` supplies the mod identity and version.

The initial snapshot is version 0.3.0-alpha.78 for EU5 1.3. Keep UTF-8 BOMs
and existing line endings in runtime text files. `.gitattributes` disables
automatic conversion so Git preserves the shipped files.

## Release status

- The author accepts the current balance as fun and suitable for release testing.
- Alpha.77 AI formation at 15 Stability was confirmed in an observer run.
- Alpha.78 adds AI Ezo colonization after formation, Manchurian colonization
  after the Hundred-Year Concord completes, and earlier availability of the
  Northern Colonial Administration. Fourteen focused static tests passed.
- These static tests are not engine tests. Northern charter execution,
  long-run AI behavior, collapse, and save transitions remain observer checks.
- The central monthly refactor and the five further prose suggestions are
  deferred. They are not included in this snapshot.

Use [OBSERVER_TESTS.md](OBSERVER_TESTS.md) for the current test procedure.
Keep backups, game saves, logs, and local build outputs outside the repository.
The initial import includes the playable mod and its documentation; the
machine-specific patch builders and historical backups are not part of it.

## Compatibility

Review shared overrides after a game update. Current overlaps include Middle
Kingdom membership, law voting and sponsorship, Japanese clan buildings,
country-rank naming, and the native colonial-charter creation and abandonment
actions. The README and Workshop description explain these restrictions.

## Preparing a release

Update the metadata version and documentation together. Package the mod files
and intended documentation, excluding `.git` and other repository-only files.
Test the exact package in a clean playset before publishing it. Keep an
immutable copy of each released package for reproducing reports.
