# wheelmap-open-source

Source code of wheelmap.org

## Installation

If you are working on a mac, please install homebrew. See: http://brew.sh/

Install git

    brew install git

Install latest ruby 2.1.2 via rbenv
  brew install rbenv ruby-build
  rbenv install 2.1.2
  echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
  echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

Restart your shell and install bundler
    rbenv global 2.1.2
    gem install bundler
    rbenv rehash

Install dependencies

### Mysql
    brew install mysql
    mkdir -p ~/Library/LaunchAgents
    ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist

### ImageMagick
    brew install imagemagick

Clone the app from github
    git clone https://github.com/sozialhelden/wheelmap-open-source.git
    cd wheelmap-open-source
    bundle install --path vendor/bundle



