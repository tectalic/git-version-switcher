# Git Version Switcher

> Simple bash script to switch specific branch/commit/tag on target repositories.

## Installation

### Stand-alone

Download the `bin/version-switcher` file, make it executable (`chmod +x version-switcher`).

### Via Composer

Add this repository to your composer.json file.

```json
    "repositories": [
        {
            "type": "git",
            "url": "git@github.com:OM4/git-version-switcher.git"
        }
    ]
```

Require this package as a development dependency with [Composer](https://getcomposer.org).

```bash
composer require --dev om4/git-version-switcher
```

Alternatively you can use it as global dependency.

```bash
composer global require om4/git-version-switcher
```

## Usage

With `-h` or `--help` yo can get usage information:

```
Usage: version-switcher [-v] <target1> [target2…]
Checkout specific branch/commit/tag on targets:
   -v | --verbose   Verbose output
   target           Colon (:) separated path and branch/commit/tag
```

For 'target', pass one or more colon (:) separated string to specify a target. The first part should be a path to a git repository; the second part is the target branch/commit/tag.

Example: `~/path/to/repo:1.2.3-beta.1`

**Notes:**
- You can use relative and absolute paths.
- If you were using a global variable for path, wrap it in curly braces ({}) to avoid interpreting the colon by the shell. Example: `${MY_PATH}:0.1.0`
