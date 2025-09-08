
<p align="center">
  <img src="images/icon-with-bg.png" alt="pacguard-icon" />
</p>

<a href="https://www.star-history.com/#blackXploit-404/pacguard&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=blackXploit-404/pacguard&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=blackXploit-404/pacguard&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=blackXploit-404/pacguard&type=Date" />
 </picture>
</a>

# pacguard

Meet **pacguard** — yes, it's pacman with a guard.  
Think of it as your package bodyguard, checking if anything in your Arch Linux system has known vulnerabilities.  

This tool is inspired by the idea behind `arch-audit`, but written simply in Python. I built it to learn, to share, and hopefully to help others keep their systems a little more secure.  

---

## Why?

Arch Linux is fast, rolling, and bleeding edge. But with speed comes the chance of pulling in packages with security issues before you've heard about them.  
**pacguard** fetches the official Arch Security Tracker feed, compares it with your installed packages, and tells you if something looks shady.  

---

## Features

- Reads your installed package list directly from pacman’s database.  
- Talks to the [Arch Security Tracker](https://security.archlinux.org/) in JSON format.  
- Flags packages that match known advisories.  
- Shows affected versions, fixed versions, severity, and CVE identifiers.  
- Suggests a quick `pacman -Syu` fix if one exists.  
- Otherwise, tells you to keep an eye on it (because sometimes there’s no fix yet).  

---

## Installation

Just type : 

```bash 
yay -S pacguard
```` 

or 

Clone the repo:

```bash
git clone https://github.com/blackXploit-404/pacguard.git
cd pacguard
````

Install dependencies:

```bash
pip install requests
sudo pacman -S pyalpm
```

Make the script executable:

```bash
chmod +x pacguard
```

(Optional) move it into your `$PATH`:

```bash
sudo cp pacguard /usr/local/bin/
```

---

## Usage

Run it like this:

```bash
./pacguard
```

or, if installed system-wide:

```bash
pacguard
```

---

## Example

When something bad shows up:

```
Vulnerable packages found:

- openssl (installed 3.0.11-1)
  Advisory: ASA-2024-0001
  Affected: 3.0.0 - 3.0.11
  Fixed: 3.0.12
  Severity: Critical
  CVEs: CVE-2024-12345, CVE-2024-67890
  Suggested fix: sudo pacman -Syu openssl
```

When everything is clean:

```
No vulnerable packages detected.
```

---

## Limitations

* Arch Linux only (uses pacman’s local database + Arch Security Tracker).
* Needs internet access to pull JSON feed.
* Won’t magically fix anything — it just tells you what’s wrong.

---

## License

MIT License. See the `LICENSE` file.

---

## Notes from the me :)

This is a small project, nothing fancy — just a Python script that scratches an itch.
I know it’s simple, but I wanted to package it up for the community. If it helps even one other Arch user, I’ll call that a win.

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="http://surajitsen.live"><img src="https://avatars.githubusercontent.com/u/143313960?v=4?s=100" width="100px;" alt="Surajit Sen"/><br /><sub><b>Surajit Sen</b></sub></a><br /><a href="https://github.com/blackXploit-404/pacguard/commits?author=blackXploit-404" title="Code">💻</a> <a href="https://github.com/blackXploit-404/pacguard/commits?author=blackXploit-404" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://debasisbiswas.me"><img src="https://avatars.githubusercontent.com/u/185465407?v=4?s=100" width="100px;" alt="DEBASIS BISWAS"/><br /><sub><b>DEBASIS BISWAS</b></sub></a><br /><a href="https://github.com/blackXploit-404/pacguard/commits?author=DebaA17" title="Code">💻</a> <a href="#ideas-DebaA17" title="Ideas, Planning, & Feedback">🤔</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![All Contributors](https://img.shields.io/github/all-contributors/projectOwner/projectName?color=ee8449&style=flat-square)](#contributors)