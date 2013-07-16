Oneboxer
----------

  - [![Gem Version](https://badge.fury.io/rb/architect.png)](https://rubygems.org/gems/architect)
  - [![Code Climate](https://codeclimate.com/github/krainboltgreene/architect.png)](https://codeclimate.com/github/krainboltgreene/architect)
  - [![Build Status](https://travis-ci.org/krainboltgreene/architect.png)](https://travis-ci.org/krainboltgreene/architect)
  - [![Dependency Status](https://gemnasium.com/krainboltgreene/architect.png)](https://gemnasium.com/krainboltgreene/architect)
  - [![Coverage Status](https://coveralls.io/repos/krainboltgreene/architect/badge.png?branch=master)](https://coveralls.io/r/krainboltgreene/architect)


Oneboxer is a library for turning media URLs into previews.

Oneboxer currently has support for page, image, and video URLs from these sites:
> + Amazon
+ Android App Store
+ Apple Store
+ BlipTV
+ Clikthrough
+ College Humor
+ Dailymotion
+ Dotsub
+ Flickr
+ Funny or Die
+ Gist
+ Github
++ Blob
++ Commit
++ Pull Request
+ Hulu
+ Imgur
+ Kinomap
+ NFB
+ Open Graph
+ Qik
+ Revision
+ Rotten Tomatoes
+ Slideshare
+ Smugmug
+ Soundcloud
+ Stack Exchange
+ TED
+ Twitter
+ Wikipedia
+ yFrog


Using Oneboxer
===============

You can include architect modules into a class like so:

``` ruby
require "discourse-oneboxer"

class MakeProjectCommand
  include Architect::Core

  def build(name)
    create_directory name do
      copy_file "Gemfile", version: Rails::VERSION
      create_directory "app" do
        create_directory "models"
        create_directory "controllers"
        create_directory "views"
      end
    end
  end
end
```

or you can simply have them accessible in `main` (sinatra style):

``` ruby
require "architect"

puts "What is your project name?"
name = gets.chomp

create_directory name do
  copy_file "Gemfile", version: Rails::VERSION
  create_directory "app" do
    create_directory "models"
    create_directory "controllers"
    create_directory "views"
  end
end
```

The `Gemfile` file would look like this:

``` ruby
# source/Gemfile
source "https://rubygems.org"

gem "rails", "~> <%= version %>"
```


Installing Oneboxer
==================

Add this line to your application's Gemfile:

    gem 'discourse-oneboxer'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install discourse-oneboxer


Contributing
============

  1. Fork it
  2. Create your feature branch (`git checkout -b my-new-feature`)
  3. Commit your changes (`git commit -am 'Add some feature'`)
  4. Push to the branch (`git push origin my-new-feature`)
  5. Create new Pull Request