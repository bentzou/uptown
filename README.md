# Uptown

## Summary
Uptown allows you to use arrows keys to navigate up and down your current path hierarchy.

### Example (using the default config): 

You log in to your terminal and are placed in the home directory:

```/Users/johnsmith $>```

Press "Alt+Up" to cd into the parent dir

```/Users $>```

Press "Alt+Down" to cd into the child dir:

```/Users/johnsmith $>```

## Install:
Add a line to your .bash_profile or .bashrc to source this script. Here's an example:

```source ~/foo/bar/uptown```

## How it works:
Uptown remembers your current path hierarchy with the environment variable "$UPTOWN_PATH." This path is used to find the parent and child directories relative to your current path. This path is updated when you "cd" out of the current hierarchy. No other environment variables are used.

Uptown also adds two readline key bindings to trigger "cd"-ing into the relative parent and child directories.

## Supported Bash versions
3.2-4.0
