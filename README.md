# Planning-Poker

![CI Build Status Badge](https://api.travis-ci.org/philou/planning-poker.svg?branch=master)
[![Code Climate](https://codeclimate.com/github/philou/planning-poker/badges/gpa.svg)](https://codeclimate.com/github/philou/planning-poker)
[![Test Coverage](https://codeclimate.com/github/philou/planning-poker/badges/coverage.svg)](https://codeclimate.com/github/philou/planning-poker/coverage)
[![Issue Count](https://codeclimate.com/github/philou/planning-poker/badges/issue_count.svg)](https://codeclimate.com/github/philou/planning-poker)

An app to do enable agile teams to do planning poker estimations remotely

An instance is continuously deployed to heroku : https://philous-planning-poker.herokuapp.com/

## How to hack it

#### Sources

First, clone the repo :
```
git clone https://github.com/philou/planning-poker.git
cd planning-poker
```

#### Dependencies

They are managed with bundler. Just run the following :
```
bundle install
```
bundle might complain that some dependencies are missing on your OS, in this case follow its advices and install them.

#### Database

There is a docker compose configuration to start services dependencies. You can either use docker, or start the db yourself. Here is the docker way.

You'll need to have docker and docker compose installed :

* https://docs.docker.com/engine/installation/
* https://docs.docker.com/compose/install/

Then, run the following to create the database :

```
docker-compose up
bundle exec rake db:create
bundle exec rake db:migrate
```

#### Local run

The db should be started from previous step. Start the rails server the typical way

```
bundle exec bin/rails server
```

Check that it's running at http://localhost:3000


======== ray =============
deploy to heroku:

x) $ heroku create planning-poker-03-15-17
Creating ⬢ planning-poker-03-15-17... done
https://planning-poker-03-15-17.herokuapp.com/ | https://git.heroku.com/planning-poker-03-15-17.git

--------------------------------------------------------------------------------
x)
  $ git remote add origin https://github.com/RayNovarina/planning-poker-03-15-17.git
  $ git remote -v
      heroku  https://git.heroku.com/planning-poker-03-15-17.git (fetch)
      heroku  https://git.heroku.com/planning-poker-03-15-17.git (push)
      origin  https://github.com/RayNovarina/planning-poker-03-15-17.git (fetch)
      origin  https://github.com/RayNovarina/planning-poker-03-15-17.git (push)

--------------------------------------------------------------------------------
x)
      $ git push origin master
      Counting objects: 1010, done.
      Delta compression using up to 8 threads.
      Compressing objects: 100% (383/383), done.
      Writing objects: 100% (1010/1010), 207.20 KiB | 0 bytes/s, done.
      Total 1010 (delta 558), reused 998 (delta 551)
      remote: Resolving deltas: 100% (558/558), done.
      To https://github.com/RayNovarina/planning-poker-03-15-17.git
       * [new branch]      master -> master

--------------------------------------------------------------------------------
x)
       $ git push heroku master
       Counting objects: 1010, done.
       Delta compression using up to 8 threads.
       Compressing objects: 100% (383/383), done.
       Writing objects: 100% (1010/1010), 207.20 KiB | 0 bytes/s, done.
       Total 1010 (delta 558), reused 998 (delta 551)
       remote: Compressing source files... done.
       remote: Building source:
       remote:
       remote: -----> Ruby app detected
       remote: -----> Compiling Ruby/Rails

       remote: -----> Using Ruby version: ruby-2.4.0
       remote: -----> Installing dependencies using bundler 1.13.7
       remote:        Running: bundle install --without development:test --path vendor/bundle --binstubs vendor/bundle/bin -j4 --deployment
       remote:        Warning: the running version of Bundler (1.13.7) is older than the version that created the lockfile (1.14.6). We suggest you upg
       rade to the latest version of Bundler by running `gem install bundler`.
       remote:        Fetching gem metadata from https://rails-assets.org/..
       remote:        Fetching gem metadata from https://rubygems.org/.........
       remote:        Fetching version metadata from https://rails-assets.org/..
       remote:        Fetching version metadata from https://rubygems.org/..
       remote:        Fetching dependency metadata from https://rails-assets.org/..
       remote:        Fetching dependency metadata from https://rubygems.org/.
       remote:        Fetching gem metadata from https://rails-assets.org/..
       remote:        Fetching version metadata from https://rails-assets.org/..
       remote:        Installing rake 12.0.0
       remote:        Installing i18n 0.8.0
       remote:        Installing concurrent-ruby 1.0.4
       remote:        Installing minitest 5.10.1
       remote:        Installing thread_safe 0.3.5
       remote:        Installing builder 3.2.3
       remote:        Installing mini_portile2 2.1.0
       remote:        Installing erubis 2.7.0
       remote:        Installing nio4r 1.2.1 with native extensions
       remote:        Installing rack 2.0.1
       remote:        Installing websocket-extensions 0.1.2
       remote:        Installing mime-types-data 3.2016.0521
       remote:        Installing arel 7.1.4
       remote:        Installing execjs 2.7.0
       remote:        Installing sass 3.4.23
       remote:        Installing coffee-script-source 1.12.2
       remote:        Installing method_source 0.8.2
       remote:        Installing thor 0.19.4
       remote:        Installing multi_json 1.12.1

       remote:        Installing pg 0.19.0 with native extensions
       remote:        Installing libv8 3.16.14.17
       remote:        Installing puma 3.8.1 with native extensions
       remote:        Using bundler 1.13.7
       remote:        Installing rails-assets-jquery 3.1.1
       remote:        Installing rails-assets-moment 2.17.1
       remote:        Installing redis 3.3.3
       remote:        Installing ref 2.0.0
       remote:        Installing tilt 2.0.6
       remote:        Installing turbolinks-source 5.0.0
       remote:        Installing tzinfo 1.2.2
       remote:        Installing nokogiri 1.7.0.1 with native extensions
       remote:        Installing rack-test 0.6.3
       remote:        Installing sprockets 3.7.1
       remote:        Installing websocket-driver 0.6.5 with native extensions
       remote:        Installing mime-types 3.1
       remote:        Installing autoprefixer-rails 6.7.2
       remote:        Installing uglifier 3.0.4
       remote:        Installing coffee-script 2.4.1
       remote:        Installing rails-assets-jquery.countdown 2.2.0
       remote:        Installing rails-assets-moment-timezone 0.5.11
       remote:        Installing therubyracer 0.12.3 with native extensions
       remote:        Installing turbolinks 5.0.1
       remote:        Installing tzinfo 1.2.2
       remote:        Installing nokogiri 1.7.0.1 with native extensions
       remote:        Installing rack-test 0.6.3
       remote:        Installing sprockets 3.7.1
       remote:        Installing websocket-driver 0.6.5 with native extensions
       remote:        Installing mime-types 3.1
       remote:        Installing autoprefixer-rails 6.7.2
       remote:        Installing uglifier 3.0.4
       remote:        Installing coffee-script 2.4.1

       remote:        Installing rails-assets-jquery.countdown 2.2.0
       remote:        Installing rails-assets-moment-timezone 0.5.11
       remote:        Installing therubyracer 0.12.3 with native extensions
       remote:        Installing turbolinks 5.0.1
       remote:        Installing activesupport 5.0.1
       remote:        Installing mail 2.6.4
       remote:        Installing bootstrap-sass 3.3.7
       remote:        Installing loofah 2.0.3
       remote:        Installing rails-dom-testing 2.0.2
       remote:        Installing globalid 0.3.7
       remote:        Installing jbuilder 2.6.1
       remote:        Installing activemodel 5.0.1
       remote:        Installing rails-html-sanitizer 1.0.3
       remote:        Installing activejob 5.0.1
       remote:        Installing actionview 5.0.1
       remote:        Installing activerecord 5.0.1
       remote:        Installing actionpack 5.0.1
       remote:        Installing actionmailer 5.0.1
       remote:        Installing actioncable 5.0.1
       remote:        Installing railties 5.0.1
       remote:        Installing sprockets-rails 3.2.0
       remote:        Installing coffee-rails 4.2.1
       remote:        Installing rails 5.0.1
       remote:        Installing jquery-rails 4.2.2
       remote:        Installing sass-rails 5.0.6
       remote:        Bundle complete! 36 Gemfile dependencies, 63 gems now installed.
       remote:        Gems in the groups development and test were not installed.
       remote:        Bundled gems are installed into ./vendor/bundle.
       remote:        Bundle completed (39.79s)
       remote:        Cleaning up the bundler cache.
       remote:        Warning: the running version of Bundler (1.13.7) is older than the version that created the lockfile (1.14.6). We suggest you upg
       rade to the latest version of Bundler by running `gem install bundler`.

       remote: -----> Installing node-v6.10.0-linux-x64
       remote: -----> Detecting rake tasks
       remote: -----> Preparing app for Rails asset pipeline
       remote:        Running: rake assets:precompile
       remote:        /tmp/build_66e2a082ed4c27e0429f71e059a75567/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/xml_mini.rb:51:
       warning: constant ::Fixnum is deprecated
       remote:        /tmp/build_66e2a082ed4c27e0429f71e059a75567/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/xml_mini.rb:52:
       warning: constant ::Bignum is deprecated
       remote:        /tmp/build_66e2a082ed4c27e0429f71e059a75567/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/core_ext/numeric
       /conversions.rb:138: warning: constant ::Fixnum is deprecated
       remote:        I, [2017-03-20T01:10:20.409052 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/cards-32b7265a
       0dafa0c9e8645b2ff58a934e0c5216f0aeda1eccd3f8768eb4596d24.png
       remote:        I, [2017-03-20T01:10:20.411742 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/androi
       d-chrome-96x96-cd390d19f46d54ea0c49aa3ce6309e75fdd0227e13dd7733eea13d692ac77409.png
       remote:        I, [2017-03-20T01:10:20.413943 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/apple-
       touch-icon-a414418c1168c91d784123fb38153146db225d4eed00022377dff75f7e31b52a.png
       remote:        I, [2017-03-20T01:10:20.418741 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/browse
       rconfig-307372cf3e6493cbff74c3996951b64a98defa120220f5812557c9aadd5e3dcb.xml
       remote:        I, [2017-03-20T01:10:20.418903 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/browse
       rconfig-307372cf3e6493cbff74c3996951b64a98defa120220f5812557c9aadd5e3dcb.xml.gz
       remote:        I, [2017-03-20T01:10:20.419359 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/mstile
       -150x150-f23707681fbfd4808e4c593f6a73651dd2be38a35dc54d5616a71a07b5e43978.png
       remote:        I, [2017-03-20T01:10:20.422504 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/favico
       n-16x16-706cadf8919b83640c3f6c6383dc2da08e2f61d1e5344cfb87533369f5c47dd0.png
       remote:        I, [2017-03-20T01:10:20.424564 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/favico
       n-32x32-d38e9ae1603a00f9b075f53026fc64997c2592497cb98c1d92813e624ae27048.png
       remote:        I, [2017-03-20T01:10:20.426423 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/favico
       n-b12fad534a1a1ba55a495512a28a7622712fdf19069e3dec760d2530b9148a35.ico
       remote:        I, [2017-03-20T01:10:20.426862 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/favico
       n-b12fad534a1a1ba55a495512a28a7622712fdf19069e3dec760d2530b9148a35.ico.gz
       remote:        I, [2017-03-20T01:10:20.430390 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/manife
       st-fade4aa6408730e97be49e834bdea26adf368457116286ab0aa8ebbf99d84045.json

       remote:        I, [2017-03-20T01:10:20.430524 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/manife
       st-fade4aa6408730e97be49e834bdea26adf368457116286ab0aa8ebbf99d84045.json.gz
       remote:        I, [2017-03-20T01:10:20.433187 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/safari
       -pinned-tab-aaebc1d211a58561547162a088f3c4d20d7ae770cb24c497824cdcc75958a3e6.svg
       remote:        I, [2017-03-20T01:10:20.433335 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/favicon/safari
       -pinned-tab-aaebc1d211a58561547162a088f3c4d20d7ae770cb24c497824cdcc75958a3e6.svg.gz
       remote:        I, [2017-03-20T01:10:25.068872 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/application-7d
       40e84856a3c064074f61065b8ab0fcbc5b3b20682d88388039197b39c61823.js
       remote:        I, [2017-03-20T01:10:25.069059 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/application-7d
       40e84856a3c064074f61065b8ab0fcbc5b3b20682d88388039197b39c61823.js.gz
       remote:        I, [2017-03-20T01:10:31.102530 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/application-63
       9c48ce147da71d4bc018d4fa12c1fa70bdc45f2ba5610ccc37d640ec0874d8.css
       remote:        I, [2017-03-20T01:10:31.102710 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/application-63
       9c48ce147da71d4bc018d4fa12c1fa70bdc45f2ba5610ccc37d640ec0874d8.css.gz
       remote:        I, [2017-03-20T01:10:31.103223 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-13634da87d9e23f8c3ed9108ce1724d183a39ad072e73e1b3d8cbf646d2d0407.eot
       remote:        I, [2017-03-20T01:10:31.103726 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-13634da87d9e23f8c3ed9108ce1724d183a39ad072e73e1b3d8cbf646d2d0407.eot.gz
       remote:        I, [2017-03-20T01:10:31.104309 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-fe185d11a49676890d47bb783312a0cda5a44c4039214094e7957b4c040ef11c.woff2
       remote:        I, [2017-03-20T01:10:31.104916 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-a26394f7ede100ca118eff2eda08596275a9839b959c226e15439557a5a80742.woff
       remote:        I, [2017-03-20T01:10:31.105974 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-e395044093757d82afcb138957d06a1ea9361bdcf0b442d06a18a8051af57456.ttf
       remote:        I, [2017-03-20T01:10:31.107961 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-e395044093757d82afcb138957d06a1ea9361bdcf0b442d06a18a8051af57456.ttf.gz
       remote:        I, [2017-03-20T01:10:31.109052 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-42f60659d265c1a3c30f9fa42abcbb56bd4a53af4d83d316d6dd7a36903c43e5.svg
       remote:        I, [2017-03-20T01:10:31.110407 #1410]  INFO -- : Writing /tmp/build_66e2a082ed4c27e0429f71e059a75567/public/assets/bootstrap/glyp
       hicons-halflings-regular-42f60659d265c1a3c30f9fa42abcbb56bd4a53af4d83d316d6dd7a36903c43e5.svg.gz

       remote:        Asset precompilation completed (12.19s)
       remote:        Cleaning assets
       remote:        Running: rake assets:clean
       remote:        /tmp/build_66e2a082ed4c27e0429f71e059a75567/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/xml_mini.rb:51:
       warning: constant ::Fixnum is deprecated
       remote:        /tmp/build_66e2a082ed4c27e0429f71e059a75567/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/xml_mini.rb:52:
       warning: constant ::Bignum is deprecated
       remote:        /tmp/build_66e2a082ed4c27e0429f71e059a75567/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/core_ext/numeric
       /conversions.rb:138: warning: constant ::Fixnum is deprecated
       remote:
       remote: -----> Discovering process types
       remote:        Procfile declares types     -> web
       remote:        Default types for buildpack -> console, rake, worker
       remote:
       remote: -----> Compressing...
       remote:        Done: 46.9M
       remote: -----> Launching...
       remote:        Released v5
       remote:        https://planning-poker-03-15-17.herokuapp.com/ deployed to Heroku
       remote:
       remote: Verifying deploy.... done.
       To https://git.heroku.com/planning-poker-03-15-17.git
        * [new branch]      master -> master

--------------------------------------------------------------------------------
x) Look at the heroku logs at this point:

  $ heroku logs --app planning-poker-03-15-17
2017-03-20T01:04:56.580250+00:00 app[api]: Initial release by user rnova94037@gmail.com
2017-03-20T01:04:56.725774+00:00 app[api]: Release v2 created by user rnova94037@gmail.com
2017-03-20T01:04:56.725774+00:00 app[api]: Enable Logplex by user rnova94037@gmail.com
2017-03-20T01:04:56.580250+00:00 app[api]: Release v1 created by user rnova94037@gmail.com
2017-03-20T01:04:57.018625+00:00 app[api]: Release v2 created by user rnova94037@gmail.com
2017-03-20T01:09:32.000000+00:00 app[api]: Build started by user rnova94037@gmail.com
2017-03-20T01:10:41.092908+00:00 app[api]: Set LANG, RACK_ENV, RAILS_ENV, RAILS_LOG_TO_STDOUT, RAILS_SERVE_STATIC_FILES, SECRET_KEY_BASE config

vars by user rnova94037@gmail.com
2017-03-20T01:10:41.092908+00:00 app[api]: Release v3 created by user rnova94037@gmail.com
2017-03-20T01:10:41.307921+00:00 app[api]: Release v3 created by user rnova94037@gmail.com
2017-03-20T01:10:41.821430+00:00 app[api]: Release v4 created by user rnova94037@gmail.com
2017-03-20T01:10:41.821430+00:00 app[api]: Attach DATABASE (@ref:postgresql-slippery-36442) by user rnova94037@gmail.com
2017-03-20T01:10:42.049074+00:00 app[api]: Release v4 created by user rnova94037@gmail.com
2017-03-20T01:10:42.161022+00:00 app[api]: Release v5 created by user rnova94037@gmail.com
2017-03-20T01:10:42.161022+00:00 app[api]: Deploy 1480d84 by user rnova94037@gmail.com
2017-03-20T01:10:42.173359+00:00 app[api]: Scaled to console@0:Free rake@0:Free web@1:Free worker@0:Free by user rnova94037@gmail.com
2017-03-20T01:10:42.357683+00:00 app[api]: Release v5 created by user rnova94037@gmail.com
2017-03-20T01:09:32.000000+00:00 app[api]: Build succeeded
2017-03-20T01:10:45.675203+00:00 heroku[web.1]: Starting process with command `bundle exec puma -C config/puma.rb`
2017-03-20T01:10:48.405965+00:00 app[web.1]: * Version 3.8.1 (ruby 2.4.0-p0), codename: Sassy Salamander
2017-03-20T01:10:48.405952+00:00 app[web.1]: Puma starting in single mode...
2017-03-20T01:10:48.405966+00:00 app[web.1]: * Min threads: 5, max threads: 5
2017-03-20T01:10:48.405971+00:00 app[web.1]: * Environment: production
2017-03-20T01:10:48.688290+00:00 app[web.1]: /app/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/xml_mini.rb:51: warning:
constant ::Fixnum is deprecated
2017-03-20T01:10:48.688304+00:00 app[web.1]: /app/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/xml_mini.rb:52: warning:
constant ::Bignum is deprecated
2017-03-20T01:10:49.992622+00:00 app[web.1]: /app/vendor/bundle/ruby/2.4.0/gems/activesupport-5.0.1/lib/active_support/core_ext/numeric/conversi
ons.rb:138: warning: constant ::Fixnum is deprecated
2017-03-20T01:10:50.514057+00:00 app[web.1]: /app/vendor/bundle/ruby/2.4.0/gems/activejob-5.0.1/lib/active_job/arguments.rb:38: warning: constan
t ::Fixnum is deprecated
2017-03-20T01:10:50.514073+00:00 app[web.1]: /app/vendor/bundle/ruby/2.4.0/gems/activejob-5.0.1/lib/active_job/arguments.rb:38: warning: constan
t ::Bignum is deprecated
2017-03-20T01:10:51.109687+00:00 app[web.1]: * Listening on tcp://0.0.0.0:15460
2017-03-20T01:10:51.110268+00:00 app[web.1]: Use Ctrl-C to stop
2017-03-20T01:10:51.155367+00:00 heroku[web.1]: State changed from starting to up


--------------------------------------------------------------------------------
x) Provision heroku app planning-poker-03-15-17 with postgresql and redis:

Activity Feed
rnova94037@gmail.com: Deployed 1480d84

    12 minutes ago v5

rnova94037@gmail.com: Attach DATABASE (@ref:postgresql-slippery-36442)

    12 minutes ago v4

rnova94037@gmail.com: Set LANG, RACK_ENV, RAILS_ENV, RAILS_LOG_TO_STDOUT, RAILS_SERVE_STATIC_FILES, SECRET_KEY_BASE config vars

    12 minutes ago v3

rnova94037@gmail.com: Build succeeded

    13 minutes ago View build log

rnova94037@gmail.com: Enable Logplex

    17 minutes ago v2

rnova94037@gmail.com: Initial release

    17 minutes ago v1


Postgresql already provisioned:
postgresql-slippery-36442
Attach DATABASE (@ref:postgresql-slippery-36442)

I added heroku-redis:
 heroku-redis: @ref:redis-encircled-41258 completed provisioning, setting REDIS_URL.


 --------------------------------------------------------------------------------
 x) Open app via heroku dashboard:

      https://planning-poker-03-15-17.herokuapp.com/

  displays ok as:

  Philou's Planning Poker

Soon an app to enable agile teams to do planning poker estimations remotely

--------------------------------------------------------------------------------
