# Changelog

All notable changes to Page Password will be documented in this file.

## [1.0.2] - 2026-04-05

### Added
- Parent inheritance: protecting a page now protects all its descendants
- Unlocking a parent page unlocks the entire branch for that session

### Changed
- Visitors accessing a protected subpage are redirected to the protected ancestor after entering the password

## [1.0.1] - 2026-04-05

### Fixed
- Token service access on frontend PageController (was throwing "Undefined property: $token")
- Removed strict return types causing PHP 8 type errors on install

## [1.0.0] - 2026-04-05

### Added
- Page password attribute for protecting any page
- Session-persistent unlock (one password entry per session)
- Dashboard panel for viewing and managing protected pages
- Dark, minimal password entry UI
- Support for both plain text and bcrypt-hashed passwords
- Middleware-based interception (clean architecture)
