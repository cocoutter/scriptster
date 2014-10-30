# Scriptster

[![Gem Version](https://badge.fury.io/rb/scriptster.png)](http://badge.fury.io/rb/scriptster)
[![Inline docs](http://inch-ci.org/github/pazdera/scriptster.png)](http://inch-ci.org/github/pazdera/scriptster)
[![Build Status](https://travis-ci.org/pazdera/scriptster.svg)](https://travis-ci.org/pazdera/scriptster)

A small library to make your scripts hip ;-).

Scriptster is a small library to help you writing scripts in Ruby. It
is only consists of two functions and it's especially useful for apps
that uses many external tools through the shell.

The two basic things this library focuses on are
 * Running shell commands
 * Providing nice logs/status messages about what happened

See the examples bellow.

## Usage

```ruby
require 'scriptster'
```

It is not necessary to configure scriptster before using it, in case you're
fine with the default settings. But if not, the configure method offers
many options to change. For the full list of options, please refer to
the [docs](http://www.rubydoc.info/github/pazdera/scriptster/master/frames).

```ruby
Scriptster::configure do |conf|
  conf.name = "my-script"
  conf.theme = :dark
end
```

The following snippet demonstrates exactly how would you use **scriptster**
in practice:

```ruby
Scriptster::log :info, "Starting ...", :informative

Scriptster::cmd.new "git branch",
  :show_out = true,
  :show_err = true,
```

The last argument of the `log` method is optional and the `cmd` method
has other options available. You will find more in the
[docs](http://www.rubydoc.info/github/pazdera/scriptster/master/frames).

## Installation

Add this line to your application's Gemfile:

    gem 'scriptster'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install scriptster


## Contributing

1. Fork it ( https://github.com/[my-github-username]/scriptster/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
