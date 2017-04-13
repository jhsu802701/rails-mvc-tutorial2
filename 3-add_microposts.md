# Chapter 3: Adding Microposts

## Adding the Micropost Class
* Enter the command "rails generate scaffold Micropost content:text user_id:integer".  This creates the micropost class with the parameters content (in text format) and user_id (in integer format).
* Enter the command "rails db:migrate" to run the database migrations.
* Enter the command "sh outline.sh". This adds the annotation comments to relevant files, provides a block diagram of the models, and updates the block diagram of the controllers.

## Viewing the App and Database
* Replace the "users" at the end of the URL in your browser with "microposts".  Press Enter.  Now you see the index of microposts, which is currently empty.
* Create a micropost.  Enter "First micropost!" for the content and "1" for the User.  (In other words, the first user, Michael Hartl, posts the message "First micropost!".)  Click on "Back" to return to the micropost index page, which now shows the first micropost.
* Create another micropost with the content "Second micropost!" for the content and "1" for the user.
* Create a micropost with the content "Third micropost!" for the content and "2" for the user.  This micropost belongs to the second user, Foo Bar.
* Create a micropost with the content "Fourth micropost!" for the content and "2" for the user.  This micropost also belongs to the second user, Foo Bar.
* Use the SQLite Browser in your host OS to view the microposts table in the database. You should now see the microposts you just entered.
