# wheelmap-open-source

Source code of wheelmap.org

## Getting Started

1. If you are working on a mac, please install homebrew. See: http://brew.sh/

2. Install git


  brew install git

3. Install latest ruby 2.1.2 via rbenv


  brew install rbenv ruby-build
  rbenv install 2.1.2
  echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
  echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

4. Restart your shell and install bundler

    rbenv global 2.1.2
    gem install bundler
    rbenv rehash

5. Install dependencies

  5.1 Mysql

    brew install mysql
    mkdir -p ~/Library/LaunchAgents
    ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist

  5.2 ImageMagick

    brew install imagemagick

6. Clone the app from github

    git clone https://github.com/sozialhelden/wheelmap-open-source.git
    cd wheelmap-open-source
    bundle install --path vendor/bundle



