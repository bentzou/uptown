# Uptown

Navigate your directory hierarchy with Alt+Arrow keys.

```
/Users/johnsmith/Code/myproject $>   # press Alt+Up
/Users/johnsmith/Code $>             # press Alt+Up
/Users/johnsmith $>                  # press Alt+Down
/Users/johnsmith/Code $>             # press Alt+Down
/Users/johnsmith/Code/myproject $>
```

Uptown remembers where you've been. When you go up, it knows how to come back down.

## Install

Source the script from your `.bashrc` or `.bash_profile`:

```bash
source ~/path/to/uptown
```

## How it works

Uptown tracks your position in the directory tree using a single environment variable, `$UPTOWN_PATH`. When you navigate up with Alt+Up, your place is saved. When you navigate down with Alt+Down, Uptown follows the saved path back. If no saved path exists but the current directory has exactly one subdirectory, Uptown descends into it automatically.

Under the hood, two readline bindings map Alt+Arrow to the shell functions `cdu` (up) and `cdd` (down).

## Configuration

**Terminal escape sequences** are detected automatically. iTerm uses modifier 9; most other terminals (Ghostty, kitty, Terminal.app) use the standard xterm modifier 3. If your terminal sends something different, override the variables before sourcing:

```bash
CD_UP_KEY_SEQUENCE='\e[1;3A'
CD_DOWN_KEY_SEQUENCE='\e[1;3B'
source ~/path/to/uptown
```

**Default paths** let Uptown automatically pick up context when you `cd` into a known tree. By default, `$HOME` is included. Add your own:

```bash
UPTOWN_DEFAULT_PATHS=(
   "$HOME"
   "/opt/projects"
)
```

## Supported Bash versions

3.2+
