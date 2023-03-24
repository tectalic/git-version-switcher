# Git Version Switcher

> Simple bash script to switch specific branch|commit|tag on target repositories.

## Usage

With `-h` or `--help`, you can get usage information:

```
git version switcher: Checkout specific branch|commit|tag on targets

Usage: gvs [-h] [-u] [-r] [-v] <TARGET1> [TARGET2…]
   -h | --help          Display this help message
   -u | --update        Update default remote (fetch)
   -r | --report-only   Discard version switching, only report
   -v | --verbose       Verbose output
   -V | --version       Display version
   TARGET               A path and a branch|commit|tag separated by a colon (:)
```

For 'target', pass one or more path and branch|commit|tag separated by a colon (:) to specify a target. The first part should be a path to a git repository; the second part is the target branch|commit|tag.

Example: `path/to/repo:1.2.3-beta.1`

**Notes:**
- You can use relative, absolute and home (~) paths.
- If you were using a global variable for path, wrap it in curly braces ({}) to avoid interpreting the colon by the shell. Example: `${MY_PATH}:0.1.0`
- This script reinstalls composer dependencies upon version switch if a target repository is [WooCommerce](https://github.com/woocommerce/woocommerce).

## Installation

### Stand-alone

Download the `bin/gvs` file and make it executable (`chmod +x gvs`).

### Via Composer

Add this repository to your `composer.json` file.

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

Alternatively, you can install it globally.

```bash
composer global require om4/git-version-switcher
```

### Via npm

Install this package as a development dependency with [npm](https://npmjs.com).

```bash
npm install --D git+ssh://git@github.com/OM4/git-version-switcher.git
```

Alternatively, you can install it globally.

```bash
npm install --g git+ssh://git@github.com/OM4/git-version-switcher.git
```

## Requirements

- `git`
- `composer` when used for installation or WooCommerce amongst the targets
- `npm` when used for installation
