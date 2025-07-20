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

Swayenv comes with some handy default environment variables (see [default environment file](environment)). You can edit them or add your own in `/etc/sway/environment`.
For user-level varables, Swayenv will automatically source the `environment` file in your sway config directory (usually `~/.config/sway/`).
To add user-level variables, simply add them to the `environment` file. E.g.:

```
# /etc/sway/environment
export FUN_VARIABLE=COOL
```

Because Swayenv sources these files, they are valid bash scripts, and can be used to run anything before Sway starts.

### Sway arguments

Swayenv can pass custom arguments to Sway for you. A helpful example is `--unsupported-gpu`, which allows Sway to use proprietary drivers (NVIDIA).

To use this, add the following to your `environment` file:

```
export SWAY_ARGS="--unsupported-gpu"
```

Any arguments you add to `SWAY_ARGS` will be passed to Sway on startup.

## License

MIT
