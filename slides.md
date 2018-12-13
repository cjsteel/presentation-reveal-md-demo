---
title: Using reveal-md
theme: night
revealOptions:
    transition: 'fade'
---
# reveal-md

How to use [reveal-md][1] to create [reveal.js][2] presentations with [markdown][3] while maintaining a separation of [content][6] and [presentation][7] a la [csszengarden][8]

.
.

----------------------------------
created by [csteel](https://github.com/csteel) | 2018-10-01 | [src][4] | [pdf][5]


[1]: https://github.com/webpro/reveal-md
[2]: http://lab.hakim.se/reveal-js/
[3]: https://daringfireball.net/projects/markdown/
[4]: https://github.com/cjsteel/presentation-reveal-md-demo
[5]: https://github.com/cjsteel/presentation-reveal-md-demo/blob/master/resources/reveal-md-demo.pdf
[6]: https://alistapart.com/article/separationdilemma
[7]: https://en.wikipedia.org/wiki/Separation_of_content_and_presentation
[8]: http://www.csszengarden.com


Note:  reveal.js is great, reveal-md allows you to create beautiful reveal.js presentations from your markdown files.

----

## reveal.js

The *reveal.js* framework has been around a while and includes many features:

* Nested slides
* PDF export
* Speaker notes and timer.
* A JavaScript API

Note: You can create Markdown content using reveal.js but it is intermingled wi$

----

## reveal-md

*reveal-md* allows you to leverage reveal.js while maintaining a better separation of content, code and style.

* Focus on content.
* Maintain consistent styles.
* Separation is voluntary, nothing prevents you from mixing in code when required.

Note: Maintaining separate code, style and content is considered to be a best practice but sometimes....

----

## Requirements

* git
* npm
* reveal-md

Instructions to follow

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

### Make our `npm` the default `npm`

Add the following `export` command to the end of your ~/.bashrc file.

```shell
export PATH=~/bin/node-v8.12.0-linux-x64/bin:$PATH
```

Now source your `~/.bashrc` to apply the new `export` to your current terminal session.:

```shell
source ~/.bashrc
```

Note: Adding our binaries directory to the beginning of the path ensures that this version of *npm* will be executed.

----

### Testing your npm installalation

Confirm that the `npm` version we installed is the first `npm` version on your path so that it gets executed whenever  you run the `npm` command.

```shell
which npm
```

Output example:

```shell
/home/csteel/bin/node-v8.12.0-linux-x64/bin/npm
```

----

### Testing the `npm` executable
Confirm that `npm` is working as expected:

```shell
npm --version
```

Output example:

```shell
6.4.1
```

----

## installing reveal-md

```shell
npm install -g reveal-md
```

### Test reveal-md

Confirm that the reveal-md executable is working as expected.

```shell
reveal-md --version
```

Output expected (when this was last edited):

```shell
2.4.0
```

Note: I stopped editing here! 

---

## Creating a new presentation

You can clone my repository and customize it the way you like to create your own base presentation.

My demo has includes three files

```shell
css/overide.css  # Used to overide css elements in the default theme.
reveal-md.json   # Used to configure presentation options
slides.md        # Where you create your slides using markdown
```

See [reveal-md documentation site][1] for detailed information.

[1]: http://webpro.github.io/reveal-md/

----

## Clone your base presentation

```shell
mkdir ~/projects/presentations/
cd ~/projects/presentations
git clone git@github.com:cjsteel/presentation-reveal-md-demo.git my-presentation
```

----

## Start the included server

In a terminal session start up reveal-md

```shell
cd my-presentation
reveal-md -w slides.md --css css/overide.css
```

---

## Customize your presentation

In a second terminal session, or using your favortie GUI editor open slides.md for editing

```shell
nano slides.md
```

----

## More to come

This demo is a *work in progress*... more to come.

----

## Create a PDF

Create or update a PDF version of your presentation

```shell
reveal-md slides.md --css css/overide.css --print resources/reveal-md-demo-pdf
```

----

## Create a static demo

Creating a local static copy of your demo might be a good idea as a backup.

```shell
reveal-md slides.md --css css/overide.css --static
```

----
