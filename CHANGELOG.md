# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2026-07-04 (Moses-Ling fork)

### Added
- `compile_project` now reads build results back from the CODESYS message store
  (compile message category `{97F48D64-A2A3-4856-B640-75C046E37EA9}`) via
  `system.get_message_objects()` and returns them in the tool result:
  - `BUILD_ERROR:` / `BUILD_WARNING:` lines with the full compiler message text
  - `BUILD_RESULT: N error(s), M warning(s)` summary
  - Tool result is flagged `isError` and reports "Build FAILED" when errors exist
- Message store is cleared before each build so only messages from the current
  build are reported
- Falls back to the previous fire-and-forget behavior if the message store API
  is unavailable

## [1.1.16] - 2025-05-06

### Fixed
- Reverted to v1.1.3 code base which has working POU creation functionality
- Fixed path handling by using simpler approach from v1.1.3
- Restored original Application object finding logic that worked in v1.1.3

## [1.0.0] - 2025-04-23

### Added
- Initial release of the MCP server for CODESYS
- Command-line interface with configuration options
- Project management functionality:
  - Opening existing CODESYS projects
  - Creating new CODESYS projects
  - Saving projects
- POU (Program Organization Unit) management:
  - Creating POUs (Programs, Function Blocks, Functions)
  - Setting POU code (declaration and implementation)
  - Creating properties and methods for Function Blocks
- Project compilation support
- Resources for querying:
  - Project status
  - Project structure
  - POU code
- Documentation for installation and usage
