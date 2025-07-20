# Swayenv

Easily define environment variables for Sway on session startup.

## Installation

This package is available for Arch users. It is a simple wrapper script for Sway that allows you to define environment variables for your session.

Install Swayenv with the following commands:

```bash
git clone https://github.com/trevin-j/swayenv.git
cd swayenv
makepkg -si
```

Note that Swayenv is not currently available in the AUR. If others start using this package, I will add it to the AUR.

## Usage

Swayenv adds a new desktop entry to the Wayland sessions menu, meaning if your display manager (e.g. SDDM) detects Sway, it should also detect a new entry, `Sway (Swayenv)`.

Upon installing, Swayenv should automatically be available on your login screen. Use it to launch Sway from now on.

Swayenv comes with some handy default environment variables. You can edit them or add your own in `/etc/sway/environment`.
For user-level varables, Swayenv will automatically source the `environment` file in your sway config directory (usually `~/.config/sway/`).
To add user-level variables, simply add them to the `environment` file. E.g.:

```
# /etc/sway/environment
export FUN_VARIABLE=COOL
```

Because Swayenv sources these files, they are valid bash scripts, and can be used to run anything before Sway starts.

## License

MIT
