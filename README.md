# Page Password

![Concrete CMS](https://img.shields.io/badge/Concrete_CMS-9.x-00A4E4)
![PHP](https://img.shields.io/badge/PHP-8.1+-777BB4?logo=php&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

> Password-protect any page in Concrete CMS. One attribute, session-persistent unlock, clean architecture.

![Password entry screen](password-screen.png)

---

## Features

- **Page attribute protection** — Set a password on any page via the Compose or Properties panel
- **Session persistence** — Visitors authenticate once per session, not on every page load
- **Parent inheritance** — Protect a page and all its descendants inherit that protection
- **Branch unlocking** — Unlocking a parent unlocks the entire subtree for that session
- **Dashboard panel** — View all protected pages, remove protection with one click
- **Bcrypt support** — Store passwords as plain text or hashed (your choice)
- **Middleware architecture** — Intercepts requests cleanly before page render

## Installation

1. Download or clone this repository
2. Place the `page_password` folder in your Concrete CMS `packages/` directory
3. Go to **Dashboard → Extend Concrete** and click **Install**

## Usage

### Protecting a page

1. Edit any page
2. Open **Compose** or **Properties**
3. Find the **Page Password** attribute
4. Enter a password and save

All child pages inherit protection automatically.

### Unlocking behavior

When a visitor hits a protected page, they're redirected to a password entry screen. After entering the correct password:

- The page (and all its descendants) unlocks for the remainder of their session
- If they accessed a child page, they're redirected to the protected ancestor first, then can navigate freely

### Managing protected pages

**Dashboard → Page Password** shows all currently protected pages. You can remove protection from any page directly from this panel.

### Using hashed passwords

For production use, you can store bcrypt hashes instead of plain text:

```php
// Generate a hash
$hash = password_hash('your-password', PASSWORD_DEFAULT);
```

Paste the resulting hash as the page password. The addon accepts both formats.

## Requirements

- Concrete CMS 9.0.0 or higher
- PHP 8.1 or higher

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for version history.

## License

MIT License. See [LICENSE](LICENSE) for details.

## Author

[Marc Stress](https://okmarc.com) — OK Marc
