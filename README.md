
# Why?

Clojure programmers have very [specific workflows](https://clojureverse.org/t/share-the-nitty-gritty-details-of-your-clojure-workflow/1208) that allow them to achieve maximum productivity. My personal workflow heavily involves Cursive with an integrated REPL and a specific layout that allows me to push my code to a private repo on my GitHub account without thinking too much about it. When I have an idea or am ready to experiment, this program is designed to get me into that state as quickly as possible.

# What does it do?

All it does is bootstrap a directory for Clojure development. It's a custom, paired-down `lein new app` without Leiningen.

```
$ mkclj my-super-duper-project
Generating project files
Generating pom.xml
/projects/my-super-duper-project copied to clipboard
Created my-super-duper-project at /projects/my-super-duper-project
```

Alternatively, you can pass no project name to it and it will generate one for you.

```
$ mkclj
Generating project name nappy-pipe
Generating project files
.
.
.
```

Great for when those impromptu moments of inspiration hit me.

This program is specifically tailored to my needs so reusing it exactly as-is may not work for you but if it serves as inspiration for your own version then great!

* Generates a project name if one is not specified.
* Creates a `src` directory, a package based on the project name, and a `core` namespace.
* Creates a `resources` directory because I often operate on files such as HTML, CSVs and this is where I like to put them.
* Creates a `deps.edn` file.
* Creates a `.gitignore`.
* Creates a `README.md`.
* Runs `clj -Spom`. I am most productive inside of Cursive (thanks Colin!) and use the generated pom.xml to import the project into Cursive.
* Tries copying the absolute path to the project to the clipboard. This will only work on a Mac since it relies on `pbcopy` being in your `PATH`. As I mentioned above, my next move after creating the project is to open Cursive and import the project and having the path in the clipboard allows me to do that quickly.

# Prerequisites

* Java, of course.
* `clj` tool. `brew install clojure` on a Mac but here are more detailed [installation instructions.](https://clojure.org/guides/getting_started)

# Credits

* Alex Miller for the `clj` tool and `tools.deps.alpha`
* Michiel Borkent (BorkDude) for explaining how to embed a Clojure program in a bash script