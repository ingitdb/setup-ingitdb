# setup-ingitdb

Install an exact [InGitDB CLI](https://github.com/ingitdb/ingitdb-cli) release in GitHub Actions without Go. This action only installs the CLI; workflows choose which commands to run.

`version` is required and must be an exact release tag. `expected-sha256` optionally supplies an independently obtained digest for the selected platform archive. The release checksum file detects corruption but cannot authenticate a release if both archive and checksum are replaced. The `version` output contains the installed release tag.

Linux and macOS support amd64 and arm64; Windows supports amd64 and arm64 where the requested release contains those assets.

```yaml
- uses: actions/checkout@3d3c42e5aac5ba805825da76410c181273ba90b1 # v7.0.1
- uses: ingitdb/setup-ingitdb@e473ccda7da73166ccb7cdc92e3522066bf862bd
  with:
    version: v0.70.4
- run: ingitdb --version
```
