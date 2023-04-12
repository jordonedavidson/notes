---
title: Setting up a new Development System
date: "2019-03-22"
categories:
  - Development
  - Servers
tags:
  - ubuntu
  - mysql
  - php
---

# Setting up a New Development System (Ubuntu >= 18.04)

## MySQL

[Digital Ocean Instructions](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04)

```console
sudo apt update
sudo apt install mysql-server
sudo mysql_secure_installation
```

Follow the steps in the Digital Ocean docs for setup

## PHP

```console
sudo apt-get install php7.2-CLI
sudo apt-get install php-xml
sudo apt-get install php-mysql
```

### Package Managers, Frameworks

- [Composer](https://getcomposer.org/download)
- [Symfony](https://symfony.com/download)  
  `curl -sS https://get.symfony.com/cli/installer | bash`
- [WP-CLI](https://make.wordpress.org/cli/handbook/installing/#installing-via-composer)
- [Node.js](https://nodejs.org/en/)

## Maybe Need

- curl
- OpenSSH for ssh keys

## Nice to Have

- [Fish Shell](https:/fishshell.com)

## Development Tools

- IDE/Text Editor: [VS Code](https://code.visualstudio.com) Can also be accquired via App Store (Snap Store or Pop! Shop)
- Graphics Program: [Gimp](https://gimp.org)
- Database GUI: [Emma Database Assistant](http://www.emma-assistant.org/)
- FTP Client: [FileZilla](https://filezilla-project.org/) Also easily accquired from the platform's App Store

## ToDos

- Create ssh keys: `ssh-keygen`
- Apply public key to servers and version control systems

## Helper Apps

### PHP CodeSniffer (phpcs)

- `composer global require "squizlabs/php_codesniffer=*"`
- locate and install rulesets for Symfony, Drupal8 and Wordpress
  - Symfony: Follow the [Stand Alone](https://github.com/djoos/Symfony-coding-standard#stand-alone) Instructions. Cloning the repo in `~/.composer/vendor/escapestudios` is a good place as other coding standards files end up in this vendor dir.
  - Drupal 8: `composer global require drupal/coder`
  - Wordpress: Like Symfony follow the [Stand Alone](https://github.com/WordPress/WordPress-Coding-Standards#standalone) instructions. Clone into `~/.composer/vendor/wpcs`

Add the rulesets with:

```console
phpcs --config-set installed_paths ~/.composer/vendor/escapestudios,~/.composer/vendor/drupal,~/.composer/vendor/wpcs
```

**NOTE** there are no spaces around the commas.

### VS Code Extentions

- PHP IntelliSense
- phpcs by Ioannis Kappas
- Git Lens
- Twig
- XML Tools
- ESLint
- Prettier - Code Formatter
