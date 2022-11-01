---
title: Terminus Guide
subtitle: Terminus 3
description: Learn what's new with the latest Terminus major version upgrade.
layout: guide
showtoc: true
contributors: [greg-1-anderson]
categories: [develop]
tags: [reference, cli, local, terminus, workflow]
permalink: docs/guides/terminus/terminus-3-0
anchorid: terminus-3-0
---

This section provides information about Terminus 3.0.

<Alert title="Note" type="info" >

If you're not already familiar with Terminus, we suggest you read the [Terminus Manual](/terminus) instead. This doc is specifically geared at existing Terminus users who need to update existing implementations.
If you're not already familiar with Terminus, we suggest you read the [Terminus Guide](/terminus) instead. This section is specifically geared at existing Terminus users who need to update existing implementations.

</Alert>

These commands or their output have changed in a significant way that may affect your existing scripting of Terminus.

## Deprecated Commands
No commands were deprecated in the Terminus 3.0 release.

## New Commands
The following commands are new to Terminus as of version 3.0:
- `self:plugin:install`: Install Terminus plugins.
- `self:plugin:list`: List installed Terminus plugins.
- `self:plugin:search` Find Terminus plugins on Packagist.
- `self:plugin:uninstall` Uninstall Terminus plugins.
- `self:plugin:update` Update already-installed Terminus plugins.

## Additional Changes
- Support for EOL versions of PHP have been removed from Terminus 3. PHP 7.4 or later is required.

## More Resources

- [The Terminus Manual](/terminus)
- [Terminus on GitHub](https://github.com/pantheon-systems/terminus)
- [Terminus Guide](/terminus)
- [Terminus PHP Compatibility](/terminus/supported-terminus#php-version-compatibility-matrix)
- [Terminus on GitHub](https://github.com/pantheon-systems/terminus)