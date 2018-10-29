# Template for VisLies web pages

This repository contains the template for the VisLies web pages. This is
the starting point for each year.

## Installing Jekyll

These pages use Jekyll for building the html, so the first thing you need
to do is have Jekyll installed on your machine. As of now, VisLies is being
hosted on GitHub pages, so Jekyll is run for you there, but you will surely
wish to also run Jekyll locally to preview pages.

Jekyll uses ruby, so first you need ruby installed on your system. Ruby
might already be installed on your system, but you might need a newer
version in order to be able to download the necessary packages. Generally,
you can use a package manager do the dirty work. For example, using
macports ruby can be installed with

``` sh
sudo port install ruby24
port select --set ruby ruby24
```

Next, you need to install bundler, which is done through the `gem`
installer part of ruby.

``` sh
sudo gem install bundler
```

Once bundler is installed you can finally (finally!) install Jekyll.

``` sh
sudo gem install jekyll
```

## Running Jekyll

Typically, the first thing you need to do when you want to build a specific
repository is to make sure that you have all the packages and plugins
necessary. To update jupyter on local machine, be in this repositories root
directory and run:

``` sh
bundle install
```

You probably need to run this with root perissions (i.e. `sudo`).

Once you have done this, you should be able to run the Jekyll server, which
will build the html pages and start a simple web server.

``` sh
bundle exec jekyll serve
```

## Updating the configuration

Get started by updating the `_config.yaml` configuration file. The biggest
need is to update the configuration to the current year. Typically, the
items needed to be updated are `title`, `email`, and `this-year`.

## Creating content

Content is created by editing the `.md` files in this repository. Every
`.md` file in the `_pages` directory will be converted to an html page. The
most likely pages to change are `index.md` and `gallery/index.md`. There
are templates for each of these pages. Take particular attention to the
configuration at the top of each one.

## Link to gallery

When you first create the site, you won't have a gallery (because the even
has not happened yet). When you are ready to add the gallery, edit the
`_config.yaml` file and change the `gallery-ready` item from `false` to
`true`.

## Moving to archive

At some point, the page will have to move to an archive to make room for
the next year. You can do this by creating a new GitHub pages repository of
the appropriate name and pushing there.

**Also**, you need to change the `baseurl` entry in `_config.yaml` to the
subdirectory where these pages will be posted.

When moving to a sub-archive, you need to make sure that you push as the
gh-pages branch.
