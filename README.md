# action-nfpm

A helper for building linux packages with [nFPM][] using version information
from git tags. **Using this action allows you to specify `${VERSION}` in your
nfpm.yaml and have the last valid git version used.**

## Example

**action-nfpm** creates Debian (*.deb) packages by default. Artifacts are
placed in `dist/*` unless configured otherwise with the `target:` input.

### Debian

Assuming you have a repository with a **nfpm.yaml** file in its root:

```yaml
jobs:
  build:
    using: [self-hosted, linux]
    steps:
      - uses: secondlife/action-nfpm@v1
      - uses: actions/upload-artifact@v2
        with:
          name: dist
          path: dist/
```

### RPM

Alternative distribution archives can be built by specifying a valid nFPM
`packager:`:

```yaml
jobs:
  build:
    using: [self-hosted, linux]
    steps:
      - uses: secondlife/action-nfpm@v1
        with:
          packager: rpm
      - uses: actions/upload-artifact@v2
        with:
          name: dist
          path: dist/
```

For a full list of available inputs see [action.yaml](action.yaml).

[nFPM]: https://nfpm.goreleaser.com/
[sal]: https://lindenlab.atlassian.net/wiki/spaces/PIE/pages/2579464303/Standard+Action+Library
