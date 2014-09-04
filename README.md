# wheelmap-open-source

Source code of wheelmap.org

## Installation

### Requirements

If you are working on a mac, please install homebrew. See: http://brew.sh/

Then install the following required tools
    brew install git wget

#### Latest ruby 2.1.2 via rbenv
    brew install rbenv ruby-build
    rbenv install 2.1.2
    echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
    echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

Restart your shell and install bundler
    rbenv global 2.1.2
    gem install bundler
    rbenv rehash

### Dependencies

#### Mysql
    brew install mysql
    mkdir -p ~/Library/LaunchAgents
    ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist

#### ImageMagick
    brew install imagemagick

### Clone the app from github
    git clone https://github.com/sozialhelden/wheelmap-open-source.git
    cd wheelmap-open-source
    bundle install --path vendor/bundle

## Getting started

Copy the examle database config and set it right.
    cp config/database.SAMPLE.yml config/database.yml

Edit database.yml to reflect your current database settings.


Now lets create the actual database and prepare minimal data
    bundle exec rake db:create:all db:migrate db:seed

And finally get some POI data into the database:
    wget http://download.geofabrik.de/europe/germany/berlin-latest.osm.bz2
    bzcat berlin-latest.osm.bz2 | bundle exec rake osm:import