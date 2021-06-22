# Triopsi Coding Standards for PHP_CodeSniffer

* [Introduction](#introduction)
* [Installation](#installation)
    + [Requirements](#requirements)
    + [Standalone](#standalone)
* [How to use](#how-to-use)
    + [Command line](#command-line)

## Introduction

This project is a collection of [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) rules (sniffs) to validate code developed for Triopsi Hosting Package. It ensures code quality and adherence to coding conventions, especially the official Triopsi Hosting Coding Standards.

## Installation

### Requirements

The Triopsi Hosting Coding Standards require PHP 5.4 or higher and [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) version **3.3.1** or higher.

### Standalone

1. Install PHP_CodeSniffer by following its [installation instructions](https://github.com/squizlabs/PHP_CodeSniffer#installation) (via Composer, Phar file, PEAR, or Git checkout).

   Do ensure that PHP_CodeSniffer's version matches our [requirements](#requirements), if, for example, you're using [VVV](https://github.com/Varying-Vagrant-Vagrants/VVV).

2. Clone the Triopsi Hosting standards repository:

        git clone -b master https://github.com/Triopsi-Hosting/code-standard.git thcs

3. Add its path to the PHP_CodeSniffer configuration:

        phpcs --config-set installed_paths /path/to/thcs

   **Pro-tip:** Alternatively, you can tell PHP_CodeSniffer the path to the WordPress standards by adding the following snippet to your custom ruleset:
   ```xml
   <config name="installed_paths" value="/path/to/thcs" />
   ```

To summarize:

```bash
cd ~/projects
git clone https://github.com/Triopsi-Hosting/code-standard.git thcs
git clone -b master https://github.com/Triopsi-Hosting/code-standard.git thcs
cd phpcs
./bin/phpcs --config-set installed_paths ../thcs
```

And then add the `~/projects/phpcs/bin` directory to your `PATH` environment variable via your `.bashrc`.

You should then see `Triopsi` et al listed when you run `phpcs -i`.

## How to use

### Command line

Run the `phpcs` command line tool on a given file or directory, for example:

    phpcs --standard=Triopsi index.php
