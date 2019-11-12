# Ruby / rbenv / Bundler

rbenv = Ruby version manager  
Ma version de ruby est gérée par rbenv \(paquet Homebrew\)

> [rbenv](https://github.com/rbenv/rbenv) is a tool that lets you install and run multiple versions of Ruby side-by-side. It’s a simple, lightweight alternative to [RVM](http://beginrescueend.com/) that focuses solely on _managing_ multiple Ruby environments.

```text
// Are you using rbenv? Just run rbenv version
$ rbenv version
2.4.0 (set by /Users/robin/.rbenv/version)
```

Bundler provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed.

Bundler is an exit from dependency hell, and ensures that the gems you need are present in development, staging, and production. Starting work on a project is as simple as `bundle install`.

```text
$ bundler -v
Bundler version 1.16.0
```

