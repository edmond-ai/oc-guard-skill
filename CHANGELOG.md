# Changelog

All notable changes to this project are documented here.

## [1.0.1] - 2026-03-05

### Changed
- Updated README with bilingual (Chinese + English) content
- Added release announcement section at README top for public sharing

## [1.0.0] - 2026-03-05

### Added
- Initial `oc-guard-skill` release with `plan` and `apply` workflow
- High-risk gating with `--confirm`
- Validation for channels, bindings, agents, and models references
- Auto backup before apply and rollback on failure
- Unified bilingual execution receipt with 12-char signature

### Security
- Path allowlist for guarded mutations
- Secret masking in receipt details
- Public package boundary guidance
