# Contributing

## Maintainer Instructions

A `.github/release.yaml` configuration file is provided to help
[automatically create release notes][auto]. Add labels to pull requests
to place new features and bugfixes into different sections of the next
version's release notes:

| Label | Description | Semver |
|-------|-------------|--------|
| `breaking-change` | API breaking change | Major |
| `enhancement` | New feature or improvement | Minor |
| `ignore-for-release` | Exclude from release notes | |
| `semver-major` | | Major |
| `semver-minor` | | Minor |

### Release Process

1. Review, add labels to, and merge PRs into the default branch
2. Draft a new release on GitHub, creating a new tag for the version
3. Auto-generate release notes
4. Review and publish

#### Automatic major version tag updates

When a new release is published the `.github/release.yaml` workflow will
publish the major semantic version component as a tag. Ex. publishing version
`v2.0.5` will also result in the `v2` tag being updated.

[auto]: https://docs.github.com/en/repositories/releasing-projects-on-github/automatically-generated-release-notes
