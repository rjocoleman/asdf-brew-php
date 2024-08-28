<div align="center">

# asdf-brew-php [![Build](https://github.com/yogurt1/asdf-brew-php/actions/workflows/build.yml/badge.svg)](https://github.com/yogurt1/asdf-brew-php/actions/workflows/build.yml) [![Lint](https://github.com/yogurt1/asdf-brew-php/actions/workflows/lint.yml/badge.svg)](https://github.com/yogurt1/asdf-brew-php/actions/workflows/lint.yml)

[php](asdf-brew-php) plugin for the [asdf version manager](https://asdf-vm.com).
</div>

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Version Format](#version-format)
- [Available Versions](#available-versions)
- [Installing Extensions](#installing-extensions)
- [Contributing](#contributing)
- [License](#license)

# Dependencies

- `brew` homebrew app
- `jq` for querying PHP versions from homebrew

# Install

Plugin:

```shell
asdf plugin add php
# or
asdf plugin add php https://github.com/yogurt1/asdf-brew-php.git
```

brew-php:

```shell
# Show all installable versions
asdf list-all php

# Install specific version
asdf install php latest

# Set a version globally (on your ~/.tool-versions file)
asdf global php latest

# Now php commands are available
php --version
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to
install & manage versions.

# Version Format

This plugin uses the major.minor version format (e.g., 8.2) when installing PHP and extensions. When specifying versions, use this format for compatibility with the underlying Homebrew formulas.

# Available Versions

The plugin supports various PHP versions and special builds. Here are some examples:

- Standard versions: 5.6, 7.0, 7.1, 7.2, 7.3, 7.4, 8.0, 8.1, 8.2, 8.4
- Debug builds: Add "-debug" suffix (e.g., 8.2-debug)
- Thread-safe builds: Add "-zts" suffix (e.g., 8.2-zts)
- Debug and thread-safe builds: Add "-debug-zts" suffix (e.g., 8.2-debug-zts)

Use `asdf list-all php` to see all available versions.

# Installing Extensions

## Manual Installation

To install PHP extensions manually, use the following command:

```shell
brew install shivammathur/extensions/<extension_name>@<php_version>
```

For example, to install Xdebug for PHP 8.2:

```shell
brew install shivammathur/extensions/xdebug@8.2
```

## Automatic Installation with Default Extensions

You can specify default extensions to be installed automatically with each PHP version. Create a file named `.default-php-extensions` in your home directory or set the `ASDF_PHP_DEFAULT_EXTENSIONS_FILE` environment variable to point to your extensions file.

Example `.default-php-extensions` file:

```
xdebug
redis
imagick
```

These extensions will be automatically installed when you install a new PHP version using asdf.

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/yogurt1/asdf-brew-php/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [Paruyr](https://github.com/yogurt1/)
