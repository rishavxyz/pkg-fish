# pkg-fish

A command line alias script for pacman, written in fish &gt;&lt;&gt;.

pkg is a function which is an alias for the Arch based Linux distributions. The name *"pkg"* is inspired by the FreeBSD package manager `pkg`. Which means `pkg-fish` has some similarities with the `pkg` itself.

## Installation

1. Install [fish shell](https://fishshell.com/) on your device.
2. Copy or place the `pkg.fish` file into the fish's `conf.d` folder located in `$HOME/.config/fish`.
3. Source the file `soure ~/.config/fish/config.fish` or open a new terminal.
4. Type `pkg` followed by a `space` and autocompletion will start to work.

## Usage

pkg is similar to FreeBSD's pkg command with additional shortcuts and arguments.

> **Additional arguments**
> `-y` alias for `--noconfirm` in pacman
> `-s` alias for `-yy` in pacman (force sync) 

| argument | shortcut | pacman command | additional argument | description |
| -------- | ----- | ----------------- | ------------------- | ----------- |
| install  | i, in | `pacman -S`       | `-y`, `-s`          | Install packages |
| remove   | r, rm | `pacman -Runsc`   | `-y`                | Remove packages  |
| update   | u, up | `pacman -Su`      | `-y`, `-s`          | Update packages  |
| find     | f, fd | `pacman -Si`      | `-s`                | Query a package  |
| search   | s     | `pacman -Ss`      | `-s`                | Search packages  |

## Example

Assuming you have added the `pkg.fish` file into the `conf.d` folder which makes the `pkg` function executable.

**Search a package**

```bash
pkg search vifm

# pacman command
pacman -Ss vifm
```

**Install a package with assuming *yes* to all the propmts**

```bash
pkg i vifm -y

# pacman command
sudo pacman -S --needed --noconfirm vifm
```

**Updating the system with force sync**

```bash
pkg up -s

# pacman command
sudo pacman -Su --needed -yy
```

## You don't have to enter sudo

Certain pacman commands requires `sudo` command to run such as installing or removing packages. pkg already has added `sudo` into those commands, eliminating the need of typing `sudo` with pkg.

## If you don't want to use fish as your default shell

In that case you can create an alias in you defalut shell (bash, zsh) `alias pkg='fish -c "pkg $@"'`

---

## More aliases are yet to come! 🐟

