[![Travis Build Status](http://img.shields.io/travis/abrom/rocketchat-ruby.svg?style=flat)](https://travis-ci.org/abrom/rocketchat-ruby)
[![Code Climate Score](http://img.shields.io/codeclimate/github/abrom/rocketchat-ruby.svg?style=flat)](https://codeclimate.com/github/abrom/rocketchat-ruby)
[![Gem Version](http://img.shields.io/gem/v/rocketchat.svg?style=flat)](#)

# Rocket.Chat REST API for Ruby

This is a gem wrapping the v1 REST API for [Rocket.Chat](https://rocket.chat/).

The gem is based on a fork of http://github.com/int2xx9/ruby-rocketchat however that gem implemented v0.1
of the Rocket.Chat API and it was not forward compatible. Thanks to [@int2xx9](http://github.com/int2xx9) for the
framework on which this gem was based 

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'rocketchat'
```

And then execute:

    $ bundle


## Supported API calls

This gem supports the following Rocket.Chat APIs (Tested against Rocket.Chat v0.54)

#### Miscellaneous information
* [/api/v1/info](#info)

#### Authentication
* [/api/v1/login](#authentication)
* [/api/v1/logout](#authentication)
* /api/v1/me

#### Users
* [/api/v1/users.create](docs/users.md#userscreate)
* [/api/v1/users.delete](docs/users.md#usersdelete)
* [/api/v1/users.getPresence](docs/users.md#usersgetpresence)
* [/api/v1/users.info](docs/users.md#usersinfo)
* [/api/v1/users.list](docs/users.md#userslist)
* [/api/v1/users.setAvatar](docs/users.md#userssetavatar)
* [/api/v1/users.update](docs/users.md#usersupdate)

#### Settings
* [/api/v1/settings/:_id](docs/settings.md#settingsget)


## Usage

#### info
To get Rocket.Chat version

```ruby
require 'rocketchat'

rocket_server = RocketChat::Server.new('http://your.server.address/')
info = rocket_server.info
puts "Rocket.Chat version: #{info.version}"
```

#### authentication
To logout from a server:

```ruby
require 'rocketchat'

rocket_server = RocketChat::Server.new('http://your.server.address/')
session = rocket_server.login('username', 'password')
# ... use the API ...
session.logout
```


For details of specific APIs:

* [Users](docs/users.md)
* [Settings](docs/settings.md)


## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/abrom/rocketchat-ruby.

Note that spec tests are appreciated to minimise regressions. Before submitting a PR, please ensure that:
 
```bash
$ rspec
```
and

```bash
$ rubocop
```
both succeed 

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
