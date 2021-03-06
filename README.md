# Overview

Shell scripts for applying default settings to UNIX-based operating systems. By default,
these are set to my preferences (namely for OSX) but you can change them to your liking by editing
any of the *.txt files in the home_files directory. Read on to learn more.

# Features

* Configures the Bash shell .bashrc file.
* Configures the Bash shell .bash_profile file.
* Configures the [Git](http://git-scm.com) .gitconfig file.
* Configures the [Git](http://git-scm.com) .gitignore file.
* Configures the [Ruby Gems](http://docs.rubygems.org/read/chapter/11) .gemrc file.
* Configures the Ruby IRB .irbrc file.
* Configures the [Pry](http://pry.github.com) .pryrc file.
* Configures the [Ruby Debugger](http://bashdb.sourceforge.net/ruby-debug.html) .rdebugrc file.
* Configures the [Awesome Print](https://github.com/michaeldv/awesome_print) .aprc file.
* Configures the [Guard](https://github.com/guard/guard) .guardrc file.
* Configures the [Xray](https://github.com/brentd/xray-rails) .xrayconfig file.
* Configures the [Pow](http://pow.cx) .powconfig file.
* Configures [Sublime Text](http://www.sublimetext.com) as the default editor.
* Adds [Bash Completion](http://bash-completion.alioth.debian.org).
* Adds [Z](https://github.com/rupa/z) support to Bash.
* Adds [rbenv](https://github.com/sstephenson/rbenv) support to Bash.

# Requirements

* [Apple OSX](https://www.apple.com/osx).
* [OSX Install](https://github.com/bkuhlmann/osx).
* [Ruby Gem Setup](http://github.com/bkuhlmann/ruby_gem_setup).

# Setup

Open a terminal window and execute the following commands:

Current Version (stable)

    git clone git://github.com/bkuhlmann/dotfiles.git
    cd dotfiles
    git checkout v6.0.0

Master Version (unstable)

    git clone git://github.com/bkuhlmann/dotfiles.git
    cd dotfiles

Edit any of the home_files/*.txt files as you see fit. Then open a terminal window and execute the following command
to install:

    cd dotfiles
    ./run.sh

Executing the run.sh script will present the following options:

    s: Show dotfiles available for install.
    i: Install dotfiles (existing files are skipped).
    l: Link dotfiles to this project (interactive - asks by file).
    c: Check for changes since last install/update.
    d: Delete dotfiles (interactive - asks by file).
    q: Quit/Exit.

The options prompt can be skipped by passing the desired option directly to the run.sh script.
For example, executing "./run.sh s" will show all dotfiles avaiable for install.

After install, the following files will require manual updating:

* .bashrc - If installed on a OS other than a Mac, adjust the path to point to the correct bin directory for the rbenv binary.
* .gemrc - Uncomment the "gemcutter_key" line and add your own RubyGems key for publishing gems.
* .gitconfig - Uncomment the name/email/token lines within the [user] and [github] sections to replace with your own details.

# Usage

From the command line, the following are a few of the commands available to use (please see all home_files/*.txt files
for additional details):

    # General
    .. = "cd .."
    ... = "cd ../.."
    c = "clear"
    h = "history"
    l = "ls -alh"
    l1 = "ls -A1"
    p='pwd | tr -d "\r\n" | pbcopy && echo "`pbpaste` (copied to clipboard)"'
    o = "open"
    home = "cd $HOME"
    bashs = "exec $SHELL"

    # Network
    ipa = 'curl -s checkip.dyndns.org | grep -Eo "[0-9\.]+" | pbcopy && echo "`pbpaste` (copied to clipboard)"'
    sniff = "sudo ngrep -W byline -d 'en0' -t '^(GET|POST) ' 'tcp and port 80'"

    # tmux (http://tmux.sourceforge.net)
    tsl = "tmux list-sessions"
    tsa = "tmux attach-session -t"
    tsk = "tmux kill-session -t"
    tsr = "tmux rename-session -t"

    # Git (http://git-scm.com)
    gi = "git init"
    gce = "git config -e"
    gail = "git config --global user.email"
    gst = "git status --short --branch"
    gl = "git log --oneline --decorate --no-abbrev-commit"
    glh='git log --pretty=format:%H -1 | pbcopy && echo "`pbpaste` (copied to clipboard)"'
    gld = "git log --graph --pretty=format:'%C(yellow)%H%Creset %an: %s -%C(cyan)%d%Creset %Cgreen(%cr)%Creset' --abbrev-commit --date=relative"
    gln = "git log --name-status"
    glf = "git log ..FETCH_HEAD"
    gg = "git grep"
    gls = "gl -S"
    glast = "git show --stat"
    guthors = "git shortlog --summary --numbered --email"
    gd = "git diff"
    gdw = "git diff --word-diff"
    gdc = "git diff --cached"
    gwc = "git whatchanged -p --pretty=medium"
    glame = "git blame"
    gb = "git branch --verbose"
    gba = "git branch --all"
    gm = "git merge"
    gms = "git merge --squash"
    gcl = "git clone"
    gch = "git checkout"
    ga = "git add"
    gap = "git add --patch"
    gall = "git add --all ."
    gco = "git commit"
    gca = "git commit --all"
    gcm = "git commit --message"
    gcam = "git commit --all --message"
    gamend = "git commit --amend --message"
    gcp = "git cherry-pick"
    gash = "git stash save"
    gashl = "git stash list --pretty=format:'%C(yellow)%gd%Creset %s'"
    gashs = "git stash show"
    gashp = "git stash pop"
    gashd = "git stash drop"
    gashc = "git stash clear"
    gf = "git fetch"
    gpu = "git pull"
    gpur = "git pull --rebase" # Rebase the current branch on top of the upstream branch after fetching
    geady = "git rebase -i @{u}" # Interactive rebase.
    gp = "git push"
    gpo = "git push origin"
    gpp = "git push production master"
    gps = "git push stage stage:master"
    gtag = "git tag"
    gtags = "git push --tags"
    gus = "git reset HEAD"
    gres = "git reset --hard HEAD"
    gdis = "git reset --hard"
    grev = "git revert"
    glatest = "git for-each-ref --sort=-committerdate refs/heads --format='%(committerdate:short) %(refname:short)'"
    ggc = "git fsck && git gc"

    # rbenv (https://github.com/sstephenson/rbenv)
    rb = "rbenv"
    rbg = "rbenv global"
    rbl = "rbenv local"
    rbs = "rbenv shell"
    rbh = "rbenv rehash"
    rbp = "rbenv which"
    rbw = "rbenv whence"
    rbv = "rbenv versions"
    rbi = "rbenv install"
    rbu = "rbenv uninstall"
    rbvars = "rbenv vars"

    # Ruby (http://www.ruby-lang.org)
    rd = "rdoc -a -o _doc"
    rdo = "open _doc/index.html"
    rdd = "rm -rf _doc"

    # Ruby Gems (http://rubygems.org)
    geml = "gem list"
    gemi = "gem install"
    gemup = "gem update"
    gemu = "gem uninstall"
    gemc = "gem cleanup"
    gems = "gem server"
    gemuc = "gem update --system && gem update && gem cleanup"

    # Ruby Gems Whois (https://github.com/jnunemaker/gemwhois)
    gemw = "gem whois"

    # Bundler (http://gembundler.com)
    b = "bundle"
    bi = "bundle install"
    bu = "bundle update"
    bo = "bundle outdated"
    bcon = "bundle console"
    be = "bundle exec"
    ber = "bundle exec rake"
    bes = "bundle exec rspec"
    bess = "bundle exec rspec spec"
    bert = "bundle exec rake test"
    berts = "bundle exec rake test | grep _test.rb"
    bertv = "TESTOPTS=-v bundle exec rake test"
    beg = "bundle exec guard"
    bch = "rm -f Gemfile.lock; bundle check"
    rebundle = "bch; bundle package"

    # Gemsmith (https://github.com/bkuhlmann/gemsmith)
    g = "gemsmith"
    go = "gemsmith open"

    # PostgreSQL (http://www.postgresql.org)
    pgs = "pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start"
    pgq = "pg_ctl -D /usr/local/var/postgres stop -s -m fast"

    # Ruby on Rails (http://rubyonrails.org)
    scs = "sc --sandbox"
    sgc = "sg controller"
    sgm = "sg model"
    sgh = "sg helper"
    sgs = "sg scaffold"
    rdbd = "rake db:drop"
    rdbc = "rake db:create"
    rdbm = "rake db:migrate"
    rassp = "rake assets:precompile"
    rassc = "rake assets:clean"
    rfixes = "rake notes:custom ANNOTATION=FIX"
    taild = "tail -f log/development.log"
    tailt = "tail -f log/test.log"
    res = "touch tmp/restart.txt"
    rprofile = "ruby-prof --printer=graph_html ./script/rails runner > profile.html"
    rpaths = "rake routes | sed -e "1d" -e "s,^[^/]*,,g" | awk '{print $1}' | sort | uniq"
    erd = "mkdir -p doc/design && rake erd attributes=primary_keys,foreign_keys,timestamps,inheritance,content inheritance=true orientation=vertical filename=doc/design/models"
    dmodels = "mkdir -p doc/design && railroady --label --inheritance --specify --all-columns --join --transitive --output doc/design/models.dot --models"
    dcontrollers = "mkdir -p doc/design && railroady --label --inheritance --output doc/design/controllers.dot --controllers"
    dstate = "mkdir -p doc/design && railroady --label --inheritance --output doc/design/state.dot --aasm"

    # Capistrano (https://github.com/capistrano/capistrano)
    bec = "bundle exec cap"
    caps = "bundle exec cap stage deploy"
    capp = "bundle exec cap production deploy"

    # Sitemap Generator (https://github.com/kjvarga/sitemap_generator)
    rsite = "rake sitemap:refresh:no_ping"
    rsitep = "rake sitemap:refresh"

    # Heroku+ (https://github.com/bkuhlmann/heroku_plus)
    hpas = "hp account --switch"

    # Z (https://github.com/rupa/z)
    ez = "$EDITOR $HOME/.z"

    # Path Finder (http://www.cocoatech.com/pathfinder)
    opf = 'open -a "Path Finder.app" "$PWD"'

    # Sublime Text (http://www.sublimetext.com)
    e = "sublime"

    # Marked (http://markedapp.com)
    md = "open -a Marked"

From IRB, Pry, and Rails consoles, the following commands are possible:

    RA.copy - Copies data to the MacOS clipboard.
    RA.paste - Pastes data from the MacOS clipboard.
    ap - Prints collections in an easy to read format.

From Pry, the following aliases are available:

    'w' = "whereami"
    'c' = "continue"
    's' = "step"
    'n' = "next"
    'f' = "finish"
    "bp" = "break"
    "bpe" = "break --enable"
    "bpd" = "break --disable"
    "bpD" = "break --delete"
    "bpc" = "break --disable-all"
    "bpC" = "break --delete-all"
    "bph" = "break --help"

# Resources

* [Dotify](https://github.com/mattdbridges/dotify) - A CLI tool for managing dotfiles across multiple machines.
* [Dotphiles](https://github.com/dotphiles/dotphiles) - A community driven framework of dotfiles.
* [GitHub Dotfiles](http://dotfiles.github.com)
* [Thoughtbot](https://github.com/thoughtbot/dotfiles)
* [Ryan Bates](http://github.com/ryanb/dotfiles)
* [Blake Walters](https://github.com/markupboy/dotfiles)
* [James Edward Grey II](https://github.com/JEG2/dotfiles)
* [Gabe Berke-Williams](https://github.com/gabebw/dotfiles)
* [Mathias Bynens](https://github.com/mathiasbynens/dotfiles)
* [Adam Jahnke](https://github.com/adamyonk/dotfiles)
* [Nicolas Gallagher](https://github.com/necolas/dotfiles)
* [Color Bash Prompt](https://wiki.archlinux.org/index.php/Color_Bash_Prompt)

# Versioning

Read [Semantic Versioning](http://semver.org) for details. Briefly, it means:

* Patch (x.y.Z) - Incremented for small, backwards compatible bug fixes.
* Minor (x.Y.z) - Incremented for new, backwards compatible public API enhancements and/or bug fixes.
* Major (X.y.z) - Incremented for any backwards incompatible public API changes.

# Contributions

Read CONTRIBUTING for details.

# Credits

Developed by [Brooke Kuhlmann](http://www.redalchemist.com) at [Red Alchemist](http://www.redalchemist.com)

# License

Copyright (c) 2010 [Red Alchemist](http://www.redalchemist.com).
Read the LICENSE for details.

# History

Read the CHANGELOG for details.
