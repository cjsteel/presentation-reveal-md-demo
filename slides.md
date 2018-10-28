---
title: Using reveal-md
theme: night
revealOptions:
    transition: 'fade'
---
# reveal-md

a faster way to create reveal.js presentations using *Markdown* the markup language.

Note:  reveal.js a a great projects that can be used to create professional presentations. reveal-md

---

## Overview

We are going do the following:

* Install reveal-md and it's requirements.
* Learn how to create a presentation.
* How to make our presentation a stand alone package.
* How to export our presentation to PDF.
* How to share a presentation.

----

## reveal.js

reveal.js is a framework for creating presentations using HTML. It has many advanced features including:

* Nested slides
* PDF export
* Speaker notes and timer.
* A JavaScript API

Note: You can create Markdown content using reveal.js but it is intermingled with code. reveal-md allows for an almost complete separation of code and content.

---

## Requirements

Creating new reveal-md presentation requires a little bit of preparation including:

* installing npm
* installing git
* installing reveal-md

Notes: Here I will outline how to do this in your home directory without root or sudo access but you can do this in whatever way you like.

----

## Installing npm

Most Linux systems will have a version available via a package manager. Here we explain how to install it to your home directory. This has some advantages including:

* root or sudo access is *not* required.
* Allows for the support of *multiple versions*.
* The presentations requirements can be saved to a git respository.

Notes: If you are running multiple npm, git or reveal-md versions you can switch between them by editing the export command we will see later.

----

### Download node.js code

Here we download the code and confirm it's integrity.

```shell
mkdir -p ~/bin
cd ~/bin
wget https://nodejs.org/dist/v8.12.0/node-v8.12.0-linux-x64.tar.xz
wget https://nodejs.org/dist/v8.12.0/SHASUMS256.txt.asc
grep node-v8.12.0-linux-x64.tar.xz SHASUMS256.txt.asc | sha256sum -c -
```

Confirm that the checksum for our tar.xz file has not been corrupted or tampered with.

```shell
node-v8.12.0-linux-x64.tar.xz: OK
```

----

### Unarchive node.js

Next we extract the contents of our tar file to our ~/bin directory.

```shell
tar -xf node-v8.12.0-linux-x64.tar.xz
```

This will create a new directory:

```shell
~/bin/node-v8.12.0-linux-x64/bin`
```

which contains the *npm* executable.

----

### Make our newest `npm` the default version.

Edit ~/.bashrc and add the followoing export command to the end of the file"

```shell
export PATH=~/bin/node-v8.12.0-linux-x64/bin:$PATH
```

Source your edited *~/.bashrc* in order apply the new `export` to your current terminal session.

```shell
source ~/.bashrc
```

Note: Adding our binaries directory to the beginning of the path ensures that this version of *npm* will be executed.

----

### Test npm

Confirm that installed version  is first in your PATH

```shell
which npm
```

Confirm that `npm` is working as expected:

```shell
npm --version
```

Output example

```shell
6.4.1
```

OK, npm iw working.
----

## installing reveal-md

### Installation

```shell
npm install -g reveal-md
```

### Testing reveal-md

Confirm that the reveal-md executable is working as expected.

```shell
reveal-md --version
```

Output expected:

```shell
2.3.0
```

---

## Creating a new reveal-md project

Next we will:

* Create a basic presentation.
* Customize some reveal-md presentation options.
* Customize our theme.
* View our presentation.

----

### Creating our content

All of our slide content will go into a slides.md file. You can call it anything you like, we will stick with *slides.md* for this how to.

```shell
mkdir -p ~/presentations/my-presentation
cd ~/presentations/my-presentation
touch slides.md

