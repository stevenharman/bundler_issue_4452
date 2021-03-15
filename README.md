# Bundler: Multi-source Gemfile.lock Issue

This repo contains a minimal set of code to reproduce an issue with incompatible `Gemfile.lock` files.

## The Problem

We have multiple sources in our Gemfile - rubygems and a private gem server.
When generating with Bundler 2.2.14 the Gemfile.lock has multiple GEM sections, one for each of the two source declared in the Gemfile.
This is as expected.

However, when trying to bundle install for deployment with an older Bundler (2.2.11, for example), an error is raised.
This happens in practice when deploying to Heroku, for example, because the heroku/ruby build pack uses Bundler 2.2.11.

## Bundler Issue on GitHub

I've used this code to open an [Issue on Bundler](https://github.com/rubygems/rubygems/issues/4452).
Check there for current status, updates, etc…
