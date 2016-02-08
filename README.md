# Onotole

New Rails project wizard. Onotole will help!

![Onotole](http://sobesednik.ru/sites/default/files/styles/420x315/public/complex_images/images/vasserman-anatoliy1-rl_2.jpg?itok=c43MW8vK)

Read more [ENG](https://en.wikipedia.org/wiki/Anatoly_Wasserman) | 
[RUS](https://ru.wikipedia.org/wiki/%D0%92%D0%B0%D1%81%D1%81%D0%B5%D1%80%D0%BC%D0%B0%D0%BD,_%D0%90%D0%BD%D0%B0%D1%82%D0%BE%D0%BB%D0%B8%D0%B9_%D0%90%D0%BB%D0%B5%D0%BA%D1%81%D0%B0%D0%BD%D0%B4%D1%80%D0%BE%D0%B2%D0%B8%D1%87) | [RUS lurk](http://lurkmore.to/%D0%92%D0%B0%D1%81%D1%81%D0%B5%D1%80%D0%BC%D0%B0%D0%BD)

## About

Fork from thoughtbot/suspenders(https://github.com/thoughtbot/suspenders)
Implemented function of user choice gems installation with all their settings,
so you can use fully working application with all needed installed and
configured from the box. Cut `Bitters` as default choice.

As default uses the latest Ruby version and Rails '~> 4.2.0' 

This user gem pack are available for custom installation (you will choose only
what you need) all of this will be available in customization menu with `-c` 
flag usage (no default selected gems will be installed). Gems with `*` mark 
will be installed as addition like default, if start `onotole` with out `-c`
flag. 

 * [Airbrake](https://github.com/airbrake/airbrake) for exception notification
 * [bootstrap3](https://github.com/seyhunak/twitter-bootstrap-rails) Bootstrap
 with asset pipeline support
 * [bootstrap3_sass](https://github.com/twbs/bootstrap-sass) Bootstrap sass
 * [bundler_audit](https://github.com/rubysec/bundler-audit) Patch-level
 verification for Bundler
 * `*`[faker](https://github.com/stympy/faker) A library for generating fake data
 such as names, addresses, and phone numbers.
 * `*`[guard](https://github.com/guard/guard) Guard is a command line tool to
 easily handle events on file system modifications. http://guardgem.org
 * [guard_rubocop](https://github.com/yujinakayama/guard-rubocop) Guard plugin
 for RuboCop
 * `*`[slim](https://github.com/slim-template/slim) Slim is a template language
 whose goal is reduce the syntax to the essential parts without becoming
 cryptic. http://slim-lang.com
 * [html2slim](https://github.com/slim-template/html2slim) HTML2SLIM utility,
  installs with slim
 * [haml](https://github.com/haml/haml) HTML Abstraction Markup Language - A
 Markup Haiku http://haml.info
 * `*`[meta_request](https://github.com/dejan/rails_panel/tree/master/meta_request)
 Supporting gem for Rails Panel (Google Chrome extension for Rails development).
 * [rails_db](https://github.com/igorkasyanchuk/rails_db) Rails Database Viewer
 and SQL Query Runner https://youtu.be/TYsRxXRFp1g
 * `*`[rubocop](https://github.com/bbatsov/rubocop) A Ruby static code analyzer,
 based on the community Ruby style guide.
 * [devise](https://github.com/plataformatec/devise) Flexible authentication
 solution for Rails with Warden. http://blog.plataformatec.com.br/tag/devise/
 * [devise-bootstrap-views](https://github.com/hisea/devise-bootstrap-views)
 * [will_paginate](https://github.com/mislav/will_paginate) Pagination library
 for Rails, Sinatra, Merb, DataMapper
 * [will_paginate-bootstrap](https://github.com/bootstrap-ruby/will_paginate-bootstrap)
 Integrates the Twitter Bootstrap pagination component with will_paginate
 * `*`[responders](https://github.com/plataformatec/responders) A set of responders
 modules to dry up your Rails 4.2+ app.
 * [hirb-unicode](https://github.com/miaout17/hirb-unicode) Unicode support
 for hirb
 * [dotenv-heroku](https://github.com/sideshowcoder/dotenv-heroku) Addition for
 quick variables export to heroku
 * [tinymce-rails](https://github.com/spohlenz/tinymce-rails) Integration of 
 TinyMCE with the Rails asset pipeline
 * `*`[annotate](https://github.com/ctran/annotate_models) Annotate Rails classes 
 with schema and routes info
 * `*`[overcommit](https://github.com/brigade/overcommit) A fully configurable 
 and extendable Git hook manager

Mandatory installation gem list you will find in `Gemfile` section

## Installation

First install the onotole gem add this in `Gemfile` and `bundle`

```
    group :development do
      gem 'onotole', require: false
    end
```

or

```
gem install onotole
```

Create gemset if you need it. 

Then run:

    `onotole projectname [ -c ] [ * rails_genetator_flags ]`

This will create a Rails app in `projectname` using the latest version of Rails.

    `onotole projectname -c`

And command like this will add some magic

    `onotole app  * github organization/project * heroku true`

This will provide a dialog, where you can select needed gems, also you can add
it with gemname flag, after app_name, like `onotole projectname --slim`.
List of gems you always can get with `onotole --gems` command. Also, 
`onotole --help` can be useful.

!!! Note, that databases with names `projectname`_development and `projectname`_test
will be dropped. For example, if your project calls `awesome`, databases
`awesome_development` and `awesome_test` will be dropped.

*NB: if you install custom gems, default user gem pack will not be installed.

## Gemfile

To see the latest and greatest gems, look at Onotole'
[Gemfile](templates/Gemfile.erb), which will be appended to the default
generated projectname/Gemfile. This gem will be installed anyway.

It includes application gems like:

* [Autoprefixer Rails](https://github.com/ai/autoprefixer-rails) for CSS vendor prefixes
* [Delayed Job](https://github.com/collectiveidea/delayed_job) for background
  processing
* [Flutie](https://github.com/thoughtbot/flutie) for `page_title` and `body_class` view
  helpers
* [High Voltage](https://github.com/thoughtbot/high_voltage) for static pages
* [jQuery Rails](https://github.com/rails/jquery-rails) for jQuery
* [New Relic RPM](https://github.com/newrelic/rpm) for monitoring performance
* [Normalize](https://necolas.github.io/normalize.css/) for resetting browser styles
* [Postgres](https://github.com/ged/ruby-pg) for access to the Postgres database
* [Rack Canonical Host](https://github.com/tylerhunt/rack-canonical-host) to
  ensure all requests are served from the same domain
* [Rack Timeout](https://github.com/heroku/rack-timeout) to abort requests that are
  taking too long
* [Recipient Interceptor](https://github.com/croaky/recipient_interceptor) to
  avoid accidentally sending emails to real people from staging
* [Simple Form](https://github.com/plataformatec/simple_form) for form markup
  and style
* [Title](https://github.com/calebthompson/title) for storing titles in
  translations
* [Puma](https://github.com/puma/puma) to serve HTTP requests

And development gems like:

* [Dotenv](https://github.com/bkeepers/dotenv) for loading environment variables
* [Pry Rails](https://github.com/rweng/pry-rails) for interactively exploring
  objects
* [Hirb](https://github.com/cldwalker/hirb) for pretty tables view in the console
* [Awesome_print](https://github.com/michaeldv/awesome_print) Pretty print your
  Ruby objects with style -- in full color and with proper indentation
* [ByeBug](https://github.com/deivid-rodriguez/byebug) for interactively
  debugging behavior
* [Bullet](https://github.com/flyerhzm/bullet) for help to kill N+1 queries and
  unused eager loading
* [Spring](https://github.com/rails/spring) for fast Rails actions via
  pre-loading
* [Web Console](https://github.com/rails/web-console) for better debugging via
  in-browser IRB consoles.
* [Quiet Assets](https://github.com/evrone/quiet_assets) for muting assets
  pipeline log messages

And testing gems like:

* [Capybara](https://github.com/jnicklas/capybara) and
  [Capybara Webkit](https://github.com/thoughtbot/capybara-webkit) for
  integration testing
* [Factory Girl](https://github.com/thoughtbot/factory_girl) for test data
* [Formulaic](https://github.com/thoughtbot/formulaic) for integration testing
  HTML forms
* [RSpec](https://github.com/rspec/rspec) for unit testing
* [RSpec Mocks](https://github.com/rspec/rspec-mocks) for stubbing and spying
* [Shoulda Matchers](https://github.com/thoughtbot/shoulda-matchers) for common
  RSpec matchers
* [Timecop](https://github.com/ferndopolis/timecop-console) for testing time

## Other goodies

Onotole also comes with:

* The [`./bin/setup`][setup] convention for new developer setup
* Rails' flashes set up and in application layout
* A few nice time formats set up for localization
* `Rack::Deflater` to [compress responses with Gzip][compress]
* A [low database connection pool limit][pool]
* [Safe binstubs][binstub]
* [t() and l() in specs without prefixing with I18n][i18n]
* An automatically-created `SECRET_KEY_BASE` environment variable in all
  environments
* The analytics adapter [Segment][segment] (and therefore config for Google
  Analytics, Intercom, Facebook Ads, Twitter Ads, etc.)

## Heroku

You can optionally create Heroku staging and production apps:

    onotole app  * heroku true

This:

* Creates a staging and production Heroku app
* Sets them as `staging` and `production` Git remotes
* Configures staging with `RACK_ENV` and `RAILS_ENV` environment variables set
  to `staging`
* Adds the [Rails Stdout Logging][logging-gem] gem
  to configure the app to log to standard out,
  which is how [Heroku's logging][heroku-logging] works.
* Creates a [Heroku Pipeline] for review apps

[logging-gem]: https://github.com/heroku/rails_stdout_logging
[heroku-logging]: https://devcenter.heroku.com/articles/logging#writing-to-your-log
[Heroku Pipeline]: https://devcenter.heroku.com/articles/pipelines

You can optionally specify alternate Heroku flags:

    onotole app \
       * heroku true \
       * heroku-flags " * region eu  * addons newrelic,sendgrid,ssl"

See all possible Heroku flags:

    heroku help create

## Git

This will initialize a new git repository for your Rails app. You can
bypass this with the ` * skip-git` option:

    onotole app  * skip-git true

## GitHub auto repository create

You can optionally create a GitHub repository for the suspended Rails app. It
requires that you have [Hub](https://github.com/github/hub) on your system:

    curl http://hub.github.com/standalone -sLo ~/bin/hub && chmod +x ~/bin/hub
    onotole app  * github organization/project

This has the same effect as running:

    hub create organization/project

## Spring

Onotole uses [spring](https://github.com/rails/spring) by default.
It makes Rails applications load faster, but it might introduce confusing issues
around stale code not being refreshed.
If you think your application is running old code, run `spring stop`.
And if you'd rather not use spring, add `DISABLE_SPRING=1` to your login file.

## Dependencies

Onotole requires the latest version of Ruby.

Some gems included in Onotole have native extensions. You should have GCC
installed on your machine before generating an app with Onotole.

Use [OS X GCC Installer](https://github.com/kennethreitz/osx-gcc-installer/) for
Snow Leopard (OS X 10.6).

Use [Command Line Tools for XCode](https://developer.apple.com/downloads/index.action)
for Lion (OS X 10.7) or Mountain Lion (OS X 10.8).

We use [Capybara Webkit](https://github.com/thoughtbot/capybara-webkit) for
full-stack JavaScript integration testing. It requires QT. Instructions for
installing QT are
[here](https://github.com/thoughtbot/capybara-webkit/wiki/Installing-Qt-and-compiling-capybara-webkit).

PostgreSQL needs to be installed and running for the `db:create` rake task.

## Contributing

If you want to get your gem in Onotole follow this steps

1. Clone this repository
2. If you need to add new question in menu add it in UserGemsMenu
3. Add your gem with description in `EditMenuQuestions`.
4. Add per `bundler` hooks in `BeforeBundlePatch`. Use function name with this 
template `add_awesome_gem` where `awesome` is a gem name. Usually minimum is to 
add gem into `Gemfile`.
5. Add after install hooks in `AfterInstallPatch`. Name your function 
`after_install_awesome`. Also, add it in query at `#post_init`. Other way it 
will not run
6. Update README.MD
7. Make PR

Please, do not change version or gems for default install.
Appname `tmp` is preferred for develop. It already added to gitignore.

If you find some misprints fell free to fix them.

Thank you!

## Direct GitHub gem installation

Gems, which have been installed from github, with 'github:' option in 
`Gemfile.erb` will be automatically installed with `gem install` command. It made
for making available support fresh fixes. If you do not need it, use 'git:' 
option with full gem trace.   

## License

MIT Licence