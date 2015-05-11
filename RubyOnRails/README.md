

# Ruby on Rails with Heroku
These are the basic steps needed to get up to speed with development. 

### Requirements
[Ruby 2.1.5](https://www.ruby-lang.org/en/documentation/installation/) (Stable across most platforms and gems)   
[SourceTree](http://www.sourcetreeapp.com/) (Version Control for Mac or Windows)   
[GitFlow](https://github.com/nvie/gitflow/wiki/Installation) (Version Control for Linux or Ubuntu)   
[Postgre SQL](https://devcenter.heroku.com/articles/heroku-postgresql#local-setup) (Heroku doesn't support sqlit3)   
[Cucumber] (https://github.com/cucumber/cucumber-rails) (cucumber testing)   
[Rspec] (https://github.com/rspec/rspec-rails) (rspec testing)    
[Heroku] (https://github.com/jonibatista/ballin-brain/wiki/Heroku) (setting up a heroku app)
### Setup Environment in Windows
1. [RailsInstaller](http://railsinstaller.org/en)


### Setup Environment in Ubuntu 14.04LTS
1. [Install Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)   
`sudo apt-get install git-core`

2. [Install Git Flow](http://danielkummer.github.io/git-flow-cheatsheet/)   
`sudo apt-get install git-flow `

3. [Install Ruby on Rails using RVM](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-on-ubuntu-12-04-lts-precise-pangolin-with-rvm)  
```  
sudo apt-get update     
sudo apt-get install curl
command curl -sSL https://rvm.io/mpapis.asc | gpg --import
\curl -L https://get.rvm.io | bash -s stable    
```
Close and open a new terminal   
```
source ~/.rvm/scripts/rvm   
rvm requirements     
rvm install 2.1.5 
rvm use ruby 2.1.5   
rvm rubygems current    
gem install rails   
gem install cucumber
gem install rspec-rails
sudo apt-get install -y nodejs
```

4. [Set up PostgreSQL](https://gorails.com/setup/ubuntu/14.10)     
```no-highlight   
sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main' > /etc/apt/sources.list.d/pgdg.list"
wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install postgresql-common
sudo apt-get install postgresql-9.3 libpq-dev  
```
The postgres installation doesn't setup a user for you, so you'll need to follow these steps to create a user with permission to create databases. Feel free to replace chris with your username.
```
sudo -u postgres psql
create user chris;
alter user chris superuser;
create database my_database_development;
\q
```

5.[Clone the repository in desire location](https://help.github.com/articles/generating-ssh-keys/#platform-linux)    
`git clone https://github.com/your-github-repo.git`  
or    
`git@github.com:username/your-github-repo.git`  
  
6.Inside the repository, set up the project    
```
bundle install
rake db:migrate
rails server
```  

7.Download Master
```
git checkout master
git checkout develop
git flow init -d
```

8.[Create a new feature branch](https://github.com/nvie/gitflow/wiki/Command-Line-Arguments)
```
git flow feature start[-F]<name>[<base>]
git flow feature finish[-Fkr]
```   

