---
title: Terminus Guide
subtitle: Install
description: Learn how to install Terminus to your local computer.
terminusexample: true
terminuspage: true
categories: [develop]
tags: [cli, local, terminus, workflow]
type: terminuspage
layout: terminuspage
showtoc: true
permalink: docs/terminus/install
anchorid: install
reviewed: "2022-03-25"
---

This section provides information on how to install and authenticate Terminus.

Terminus is available for macOS and Linux. Windows 10 users can install the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10), then install Terminus in the Linux shell.

Some Terminus commands use SSH authentication. You may want to consider [generating and adding SSH keys](/ssh-keys/) to your account before you continue.

## Requirements

### Package Manager

- [apt](https://ubuntu.com/server/docs/package-management) for Ubuntu/WinWSL-Ubuntu
- [Homebrew](https://brew.sh/) for Mac

### Required Packages

- PHP Version 7.4 or later (must include the [php-xml extension](https://secure.php.net/manual/en/dom.setup.php)). You can check your PHP version by running `php -v` from a terminal application.
- [PHP-CLI](http://www.php-cli.com/)
- [PHP-CURL](https://secure.php.net/manual/en/curl.setup.php)
- [Composer](https://getcomposer.org/download/)
- [Git](https://help.github.com/articles/set-up-git/) (May be needed for the plugin manager component)

### Recommended Packages

- [Drush](http://docs.drush.org/en/master/install/) (Useful to run incompatible-with-Terminus Drush commands)
- [WP-CLI](http://wp-cli.org/) (Useful to run incompatible-with-Terminus WP-CLI commands)

## Install Terminus

There are several ways to install Terminus, depending on your use case:

- For a self-contained Terminus executable, [install terminus.phar](#standalone-terminus-phar).
- If you are using a Mac, you can [install using homebrew](#homebrew-installation).
- If you want to contribute to the Terminus project, [download and install](https://github.com/pantheon-systems/terminus#installing-with-git) from the Git repository.

### Standalone Terminus PHAR

The following commands will:

- Create a `terminus` folder in your home directory (`~/`)
- Get the latest release tag of Terminus
- Download and save the release as `~/terminus/terminus`
- Make the file executable
- Add a symlink to your local `bin` directory for the Terminus executable

    ```bash{promptUser: user}
  mkdir -p ~/terminus && cd ~/terminus
  curl -L https://github.com/pantheon-systems/terminus/releases/download/3.1.0/terminus.phar --output terminus
  chmod +x terminus
  ./terminus self:update
  sudo ln -s ~/terminus/terminus /usr/local/bin/terminus
  ```

### Homebrew Installation

The Terminus application is published to [Homebrew](https://brew.sh/). 

Run the command below to install:

```bash
brew install pantheon-systems/external/terminus
```

## Authenticate

### Machine Token

You must log in with a machine token after the installation completes. A machine token is used to securely authenticate your machine. Machine tokens provide the same access as your username and password, and do not expire. Refer to [Machine Tokens](/machine-tokens/) for more information.

1. Navigate to the **User Dashboard**, select **Account**, and then select  **Machine Tokens** to [create your machine token](https://dashboard.pantheon.io/login?destination=%2Fuser#account/tokens/create/terminus/).

1. Use your machine token to authenticate into Terminus, replacing <email@example.com> and <machine_token>:

  ```bash{promptUser: user}
  terminus auth:login --email=<email@example.com> --machine-token=<machine_token>
  ```

    - Machine tokens are keyed to the email address associated with your Pantheon user account. After a token has been used to authenticate Terminus, future sessions are authenticated with your email address:

  ```bash{promptUser: user}
  terminus auth:login --email <email@example.com>
  ```

### SSH Authentication

Commands that execute remote instructions to tools like Drush or WP-CLI require SSH authentication. Refer to [Generate and Add SSH Keys](/ssh-keys/) to prevent password requests when executing these commands.

## More Resources

- [Developing on Pantheon Directly with SFTP Mode](/sftp)
- [PHP on Pantheon](/guides/php)