Macbook
========

[![Build Status](https://travis-ci.org/lmmendes/macbook.svg?branch=master)](https://travis-ci.org/lmmendes/macbook)

Macbook is a script to set up an macOS laptop for web development.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

## Install ##

Download the script:

```sh
$ curl --remote-name https://raw.githubusercontent.com/lmmendes/macbook/master/macbook
```

Execute the downloaded script:

```sh
$ sh macbook 2>&1 | tee ~/macbook.log
```

Optionally, review the log:

```sh
$ less ~/macbook.log
```

## What it sets up ##

macOS tools:

* [Homebrew] for managing operating system libraries.
* [Cakebrew] Homebrew visual interface

[Homebrew]: http://brew.sh/
[Cakebrew]: https://www.cakebrew.com/

Unix tools:

* [Git] for version control
* [OpenSSL] for Transport Layer Security (TLS)
* [The Silver Searcher] for finding things in files
* [Tmux] for saving project state and switching between projects
* [Cloud Foundry] command line client

[Git]: https://git-scm.com/
[OpenSSL]: https://www.openssl.org/
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Tmux]: http://tmux.github.io/
[Cloud Foundry]: https://github.com/cloudfoundry/cli

Programming languages, package managers, and configuration:

* [ASDF] for managing programming language versions
* [Java] SE Development Kit 8
* [Node.js] and [NPM], for running apps and installing JavaScript packages
* [Yarn] for managing JavaScript packages

[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[ASDF]: https://github.com/asdf-vm/asdf
[Yarn]: https://yarnpkg.com/en/
[Java]: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

## Managing packages using `asdf` ##

Listing and installing a greater version of Java

```sh
# List all version
$ asdf list-all java
8.161
9.0.1

# Installing Java v9.0.1
$ asdf install java 9.0.1
```

Listing and installing a greater version of Java

```sh
# List all version
$ asdf list-all java
8.161
9.0.1

# Installing Java v9.0.1
$ asdf install java 9.0.1
```

## Installing a database (eg: MySQL or PostgreSQL) ##


```
# MySQL
$ brew install mysql

# PostgreSQL
$ brew install postgresql
```

## Using brew services to manage installed services

Integrates Homebrew formulae with macOS's `launchctl` manager.

Start service mysql at login

```
$ brew services start mysql
```

Run service. Don't start at login (nor boot):

```
$ brew services run mysql
```

Stop service mysql:

```
$ brew services stop mysql
```

Restart service mysql:

```
$ brew services restart mysql
```
