<!--
Copyright (c) 2026 ADBC Drivers Contributors

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Contributing

Issues and PRs are welcome. If you want to ask questions before opening an issue or PR, feel free to start a [Discussion](https://github.com/orgs/adbc-drivers/discussions) here on GitHub or join the [Columnar Community Slack](https://join.slack.com/t/columnar-community/shared_invite/zt-3gt5cb69i-KRjJj~mjUZv5doVmpcVa4w).

## When to Update

Update `system-to-driver.yaml` when:

- A new [dbc](https://docs.columnar.tech/dbc/)-installable driver is added (add a self-mapping, e.g., `postgresql: postgresql`)
- A new system has been tested and verified to work with an existing driver
- There is a change to the preferred driver to use with a system

## Releases

### GitHub Actions Workflow

When a release is created through the GitHub UI, the release workflow automatically attaches `alias-to-driver.yaml` and `system-to-driver.yaml` as release assets. This allows consumers to download specific versions of the mapping files directly from the release page.

### Tagging Conventions

- **Tag**: `X.Y.Z` (e.g., `0.1.0`)
- **Release title**: `X.Y.Z (YYYY-MM-DD)` (e.g., `0.1.0 (2026-02-05)`)
- **Release description**: Bulleted list of changes, one per line

Example release description:

```md
- Add foo: bar to alias-to-driver
- Fix baz typo in system-to-driver
```

### Versioning

This project follows [Semantic Versioning](https://semver.org/):

- **Patch version** (X.Y.**Z**): Fixes to existing mappings (e.g., correcting a typo in a driver name)
- **Minor version** (X.**Y**.0): Additions of new mappings
- **Major version** (**X**.0.0): Breaking changes or format changes to the YAML structure

All mapping files share the same version number and are released together. When making a release, update the `version` field in every mapping file's metadata, even if only one file has changes. This ensures consumers can rely on a single version number for the entire set of mappings.

Only update a file's `updated` field when its mappings actually change. Do not change `updated` just because the `version` was incremented.

### Adding a New Mapping File

Adding a new mapping file is a minor version increment. When adding a new file:

1. Increment the minor version in all existing mapping files to match the new file's version
2. Add the new file to `.github/workflows/release.yaml` so it gets attached to releases
