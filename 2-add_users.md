# Chapter 2: Adding Users

## Adding the User Class
* Enter the command "rails generate scaffold User name:string email:string".
* Enter the command "rails db:migrate" to run the database migrations.
* Enter the command "sh outline.sh".  This adds the annotation comments to relevant files, provides a block diagram of the models, and updates the block diagram of the controllers.

## Viewing the App and Database
* In your web browser, add "/pupils" to the end of the URL, and press Enter. You should now see the index of pupils, which is currently empty.
* Add a few users to the app.
* Use the SQLite Browser in your host OS to view the users table in the database.  You should now see the users you just entered.
