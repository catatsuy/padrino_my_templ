# padrino my template

## initial

    padrino g project sample_blog -d sequel -a mysql -c scss -e slim -t rspec


## Dependencies

Debian:

    mysql-server libmysqlclient-dev


## Setup

    vagrant up
    vagrant ssh
    curl -L https://raw.github.com/catatsuy/dotfiles/master/quick.sh | bash
    curl -L https://raw.github.com/catatsuy/dotfiles/master/setup.sh | bash
    chsh -s /bin/zsh
    rbenv install 2.1.1
    gem install bundler
    gem install padrino
    # dependency packages
    sudo aptitude install -y mysql-server libmysqlclient-dev


## Develop

mysql:

    mysql -uroot
    CREATE DATABASE testdb;
    GRANT ALL PRIVILEGES ON testdb.* to 'testuser'@'localhost' IDENTIFIED BY 'passpass' WITH GRANT OPTION;
    FLUSH PRIVILEGES;

padrino:

    bundle install --path=vendor/gems
    # rackup
    bundle exec padrino s --host=0.0.0.0 --port=3000 -e development
    # seed
    bundle exec padrino rake sq:migrate:up
    # model
    padrino g model User
    ## del
    padrino g model User -d


## URL

 * [Guides Home - Padrino Ruby Web Framework](http://www.padrinorb.com/guides)
