# Chapter 1: Starting the New App

## New Rails App
* Create the new Rails app by entering the command "rails new mvc2".
* Enter the command "cd mvc2" to enter your new app's root directory.
* Enter the command "rails db:migrate" to migrate the database.

## Server
* Create the server.sh file with the following content:
```
#!/bin/bash

echo 'View page at http://localhost:3000/'
echo 'If you are using Docker or Vagrant,'
echo 'the port number may be something else.'
echo 'If you are using Docker Machine,'
echo 'replace "localhost" with a numerical' 
echo 'IP address (probably 192.168.99.100).'

echo '-----------------------'
echo 'rails server -b 0.0.0.0'
rails server -b 0.0.0.0
```
* Start tmux.  Use one tmux window to run the server and one tmux window to enter commands.
* While the local server is running, open the web browser in your host environment and go to the appropriate URL. You should see the Ruby on Rails default splash screen. Keep this web browser tab open, and refresh it periodically to see the progress in this project.

## Gemfile
* Add the following lines to the end of the Gemfile:
```
# BEGIN: for outline.sh
group :development do
  gem 'annotate' # Adds comments listing parameters and the output of "rails routes"
  gem 'railroady' # Generates block diagrams
  gem 'rails-erd' # Generates block diagrams
end
# END: for outline.sh
```
* Enter the command "bundle install".  This action installs the annotate, railroady, and rails-erd gems.

## Outlining
* Create the file outline.sh in your app's root directory, and give it the following content:
```
echo '-----------------------------'
echo 'bundle exec annotate --routes'
bundle exec annotate --routes

echo '--------------------'
echo 'bundle exec annotate'
bundle exec annotate

d_mo='log/diagram-models.jpg'
d_co='log/diagram-controllers.jpg'

echo '---------------'
echo 'Using rails-erd'
bundle exec erd --attributes=foreign_keys,primary_keys,timestamps,inheritance,content --filetype=dot --filename=log/diagram-models --inheritance --notation=bachman
dot -Tjpg log/diagram-models.dot > $d_mo
echo
echo "Models diagram is at $d_mo"
echo

echo '---------------'
echo 'Using railroady'
bundle exec railroady -i -l TestLabel -v -a --all-columns -j -m -p -z -t --engine-controllers -C | dot -Tjpg > $d_co
echo
echo "Controllers diagram is at $d_co"
echo

echo '************************'
echo 'outline.sh OUTPUT FILES:'
echo $d_mo
echo $d_co
```
* Enter the command "sh outline.sh" to make use of the annotate, rails-erd, and railroady gems.  Because this is a blank app, there are no models yet, and the only controller currently in use is the basic application controller.
