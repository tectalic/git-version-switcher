# Git Version Switcher

> Simple bash script to switch specific branch|commit|tag on target repositories.

## Installation

### Stand-alone

Download the `bin/gvs` file and make it executable (`chmod +x gvs`).

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

Alternatively, you can use it as a global dependency.

```bash
composer global require om4/git-version-switcher
```

## Usage

With `-h` or `--help`, you can get usage information:

```
git version switcher: Checkout specific branch|commit|tag on targets

Usage: gvs [-h|-r|-v] <TARGET1> [TARGET2…]
   -h | --help          Display this help message
   -r | --report-only   Discard version switching, only report
   -v | --verbose       Verbose output
   TARGET               Path and branch|commit|tag separated by a colon (:)
```

For 'target', pass one or more path and branch|commit|tag separated by a colon (:) to specify a target. The first part should be a path to a git repository; the second part is the target branch|commit|tag.

Example: `path/to/repo:1.2.3-beta.1`

**Notes:**
- You can use relative absolute and home (~) paths.
- If you were using a global variable for path, wrap it in curly braces ({}) to avoid interpreting the colon by the shell. Example: `${MY_PATH}:0.1.0`

## Note

This script reinstalls composer dependencies upon version switch if a target is [WooCommerce](https://github.com/woocommerce/woocommerce).
