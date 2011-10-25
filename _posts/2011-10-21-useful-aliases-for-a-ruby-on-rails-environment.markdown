---
date: 2011-10-21 6:00 PM
title: Useful aliases for a Ruby on Rails environment
layout: post
author: Harlan Wood
---

We have set up a number of aliases that reduce keystrokes for the things we do a lot, every day.
Some of our favorites are reproduced here:

{% highlight bash %}

    # Bundler
    alias bi='bundle install'
    alias be='bundle exec'

    # Rails
    alias r='be rails'
    alias rdm='rake db:migrate'
    alias rdp='rake db:prepare'
    alias rdr='rake db:rebuild'
    alias rtp='rake db:test:prepare'
    alias rds='rake db:seed'

    # Rspec
    alias sp='be rspec --color --drb'
    alias sn='sp --format nested'
    alias sf='sp --require fuubar --format Fuubar'

{% endhighlight %}

Just pop these into your .bashrc (or similar file), and you're good to go.

