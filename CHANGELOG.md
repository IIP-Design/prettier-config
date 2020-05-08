# Change Log

##### All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased](https://github.com/IIP-Design/prettier-config/compare/v1.0.0...HEAD)

_This sections lists changes committed to master since most recent release_

## [v1.1.0](https://github.com/IIP-Design/prettier-config/compare/v1.0.0...v1.1.0) - 2020.05.08

### Added:

- Justification in the docs for why we maintain the arrow function parentheses rule set to `avoid` when Prettier switched their default to `always` in v2.0.0

### Changed:

- Switched the value for trailing commas from `none` to `es5`. This makes for cleaner git diffs and matches Prettier's own change in the default value for this property in their v2 release
- Updated to the latest version of Prettier (v2.0.5)
- Removed the justification for the end of line rule since Prettier altered the default to match our selection in v2.0.0

## [v1.0.0](https://github.com/IIP-Design/prettier-config/releases/tag/v1.0.0) - 2020.03.17 (Initial Release)

### Added:

- The base Prettier rule set
- Initial documentation
