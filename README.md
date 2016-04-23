# robert-w.github.io

#### Notes about project structure
I am no Ruby expert or Jekyll Expert, so I am still learning and these are just my observations.  The folders have the following meaning. All files must use front matter to be processed, except for Sass files that are imported, the root Sass file is the only one that needs it.

|Folder|Meaning|
|------|-------|
|_includes|HTML partial files that are included via `{% include head.html %}`|
|_layouts|Layout files that are linked in front matter via: `layout: default`|
|_posts|Static markdown files to be generated, must have format `xxxx-xx-xx-name.md`.  Typically the x's represent year-date-month, but any numbers can be used.
|_sass|Sass files go here, `@import` in `.scss` files will look here|
|_site|Where site generated content goes|

Configurations go in `_config.yml` and you should have your homepage defined as index.html in the root.


#### Setting up Local Environment
I like to use [Brew](http://brew.sh/) to manage packages on OSX. Since I can not install Ruby Gems on OSX without Sudo, I installed [rbenv](https://github.com/rbenv/rbenv). Below are instructions on how to set those up, install a specific version of ruby and set that as your local version.

1. Install Brew
2. `brew install rbenv`
3. `rbenv install 2.0.0-p247`
4. `rbenv local 2.0.0-p247`
5. `gem install bundler`
  * if you get permission errors, try running `gem env home` and see if it points to something in an rbenv folder.
6. Copy this Gemfile, run  `bundle install`
7. Run `bundle exec jekyll serve` to begin local development.


#### Developing Locally
Make sure your environment is set up.  If you don't have ruby, bundler, and jekyll installed.  See above.
1. Initialize rbenv with `eval "$(rbenv init -)"`
2. Start Jekyll with `jekyll serve`
