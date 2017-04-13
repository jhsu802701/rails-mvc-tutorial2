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
