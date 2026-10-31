# setup-datatug

[![Watch the DataTug product video](assets/product-video-play.svg)](https://youtu.be/tjOzdzB_PGA)

[Watch the DataTug product video](https://youtu.be/tjOzdzB_PGA)

Install an exact [DataTug CLI](https://github.com/datatug/datatug-cli) release in GitHub Actions without Go. This action installs the CLI only; workflows choose which commands to run. The action downloads the published DataTug release; the CLI's own terms apply separately. Release-provided license files and notices are kept beside the installed binary; their presence does not make draft terms effective.

`version` is required and must be an exact release tag. `expected-sha256` optionally supplies an independently obtained digest for the selected platform archive. The release checksum file detects corruption but cannot authenticate a release if both archive and checksum are replaced. The `version` output contains the installed release tag.

Linux and macOS support amd64 and arm64; Windows supports amd64 where the release contains those assets.

```yaml
- uses: actions/checkout@3d3c42e5aac5ba805825da76410c181273ba90b1 # v7.0.1
- uses: datatug/setup-datatug@f2133005854495a293d90cb684e01b27a91c2c5c
  with:
    version: v0.131.0
- run: datatug --version
```

Self-hosted runners need PowerShell (`pwsh`); Unix runners also need `tar` and `chmod`.
