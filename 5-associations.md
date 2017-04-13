# Chapter 5: Associations

## Adding Associations
* Replace the contents of app/models/user.rb with the following:
```
class User < ApplicationRecord
  has_many :microposts
end
```
* A user can have microposts.
* Replace the contents of app/models/micropost.rb with the following:
```
class Micropost < ApplicationRecord
  belongs_to :user
end
```
* A micropost must belong to a user.
* These associations allow you to display every post belonging to a specific user or to display a Twitter-like feed of microposts.
* NOTE: At this point, deleting a user does NOT automatically delete the user's microposts.  Automatically deleting a given user's microposts during this process requires adding code to the user model.  This is covered in the micropost chapter of Rails Tutorial.

## Outlining
* Enter the command "sh outline.sh".
* The model block diagram has changed.  Now you see an arrow pointing from the user model to the micropost model with an open circle at the user end and a filled circle at the micropost end.
* The single arrow means a one (user) to many (microposts) relationship.
* The open circle at the user end of the arrow means that the relationship is optional.  In other words, a user without a micropost is allowed.
* The closed circle at the micropost end of the means that the relationship is mandatory.  In other words, a micropost without a user is prohibited.
