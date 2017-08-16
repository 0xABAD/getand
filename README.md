Overview
========

Getand/install is a redistrutable installation script for go packages
that have dependencies.  You list dependent packages directly in
the script and what branch/tag/commit need to be checked out before
installation.  Then your users need to just get your package and run
the script for an easy install.

Usage
-----

* Clone this repo directly in the folder of you project.

* Modify install.go to list your specific dependencies and remove any
files you don't want to redistibute.

* Now all your users have to do is `go get -d yourpackage` and then `go
  run getand/install.go` from the package directory.

Motivation
----------

`go get` works for many cases when you don't care about working out
the master branch.  Also, there is also an automatic checkout function
that gets a commit with a tag that lists a specific go version.
However, this isn't necessarily flexible when people are using
different different go versions and your dependencies need to have
that specific tag.

I do know of [go dep](https://github.com/golang/dep) but that's not
official and while package managers can be extremely useful they do
have their drawbacks.  So the other option is a custom install tool.
This gives you full control at the expense of having to maintain it.
In practice, I don't find this problematic as long as you can keep it
simple.

License
-------

This software is released under the public domain and dual licensed
under the MIT license for entities that don't recognize works under
the public domain.
