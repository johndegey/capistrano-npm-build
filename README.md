# Capistrano::npm::Build [![Gem Version](https://badge.fury.io/rb/capistrano-npm-build.svg)](https://badge.fury.io/rb/capistrano-npm-build)

npm support for Capistrano 3.x


## Installation

Add this line to your application's Gemfile:

```ruby
gem 'capistrano', '~> 3.1.0'
gem 'capistrano-nvm', '~> 0.0.7'
gem 'capistrano-npm-build'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install capistrano-npm-build

## Usage

Require in `Capfile` to use the default task:

```ruby
require 'capistrano/npm_build'
```

The task will run before `deploy:updated` as part of Capistrano's default deploy,
or can be run in isolation with `cap production npm:install`

Configurable options:

```ruby
set :npm_flags, '--silent --no-progress'                 # default  (adding --production will failed to run build command)
set :npm_build_flags, '--modern'                         # default
set :npm_roles, :all                                     # default
set :npm_env_variables, {}                               # default
```

### Dependencies

npm allows for normal `dependencies` and `devDependencies`. By default this gem uses `'--silent --no-progress'` as the install flags which will install `dependencies` and `devDependencies` too. If you don't want your `devDependencies` installed, then add `--production`.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
