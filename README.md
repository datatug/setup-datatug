# setup-datatug

Install an exact [DataTug CLI](https://github.com/datatug/datatug-cli) release in GitHub Actions without Go. This action installs the CLI only; workflows choose which commands to run. The action downloads the published DataTug release; the CLI's own terms apply separately.

`version` is required and must be an exact release tag. `expected-sha256` optionally supplies an independently obtained digest for the selected platform archive. The release checksum file detects corruption but cannot authenticate a release if both archive and checksum are replaced. The `version` output contains the installed release tag.

Linux and macOS support amd64 and arm64; Windows supports amd64 where the release contains those assets.
