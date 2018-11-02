---
title: Using reveal-md
theme: night
revealOptions:
    transition: 'fade'
---
# reveal-md

Using [reveal-md][1] to create [reveal.js][2] presentations with [markdown][3] while maintaining a separation of [content][6] and [presentation][7] a la [csszengarden][8]

.
.

----------------------------------
created by [csteel](https://github.com/csteel) | 2018-10-01 | [src][4] | [pdf][5]


[1]: https://github.com/webpro/reveal-md
[2]: http://lab.hakim.se/reveal-js/
[3]: https://daringfireball.net/projects/markdown/
[4]: https://github.com/cjsteel/presentation-reveal-md-demo
[5]: https://github.com/cjsteel/presentation-reveal-md-demo/blob/master/reveal-md-demo.pdf
[6]: https://alistapart.com/article/separationdilemma
[7]: https://en.wikipedia.org/wiki/Separation_of_content_and_presentation
[8]: http://www.csszengarden.com


Note:  reveal.js is great, reveal-md allows you to create beautiful reveal.js presentations from your markdown files.

----

## reveal.js

The reveal.js framework has been around a awhile  has many handy features including:

* Nested slides
* PDF export
* Speaker notes and timer.
* A JavaScript API

Note: You can create Markdown content using reveal.js but it is intermingled wi$

----

## reveal-md

reveal-md allows you to leverage many of the features of reveal.js while maintaining a separation of content, code and style.

* Focus on content.
* Maintain consistent styles.
* Separation is voluntary.

Note: Maintaining separate code, style and content can be annoying for coders.

----

## Requirements

* npm
* reveal-md

Notes: Here I will outline how to do this in your home directory without root or sudo access but you can do this in whatever way you like.

----

## Installing npm in your home directory

To download v8.12.0 of nodejs run the following commands:

```shell
mkdir -p ~/bin
cd ~/bin
wget https://nodejs.org/dist/v8.12.0/node-v8.12.0-linux-x64.tar.xz
wget https://nodejs.org/dist/v8.12.0/SHASUMS256.txt.asc
grep node-v8.12.0-linux-x64.tar.xz SHASUMS256.txt.asc | sha256sum -c -
```

Confirm our checksum:

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

Confirm that the installed version is first on your path

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

Good to go.

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

## Creating a new presentation

You can clone my repository and customize it the way you like to create your own base presentation.

My demo has includes three files

```shell
css/overide.css  # Used to overide css elements in the default theme.
reveal-md.json   # Used to configure presentation options
slides.md        # Where you create your slides using markdown
```

See [reveal-md documentation site][1] for detailed informations.

[1]: http://webpro.github.io/reveal-md/

----

## Clone your base presentation

```shell
mkdir ~/projects/presentations/
cd ~/projects/presentations
git clone git@github.com:cjsteel/presentation-reveal-md-demo.git my-presentation
```

----

## Start the build in server

In a terminal session start up reveal-md

```shell
cd my-presentation
reveal-md -w slides.md --css css/overide.css
```

## Customize

In a second terminal session, or using your favortie GUI editor open slides.md for editing

```shell
nano slides.md
```

----
