# Chapter 4: Analysis

Now that you have set up the Rails Tutorial Toy App, it's time to analyze it.  Note that most of the analysis will be on the features not provided in the previous tutorial.

## Models
* The file app/models/user.rb defines the user class.  The file app/models/micropost.rb defines the micropost class.
* The annotate gem prints a list of parameters in the comments at the beginning of the model files.

## Routes
* The Rails router (at config/routes.rb) recognizes URLs that can be visited by web site visitors and selects the appropriate controller action and view.  In this project, the Rails router lists users and microposts as resources.
* The annotate gem prints the output of the "rails routes" command in the beginning of the config/routes.rb file.  This output includes the path name, HTTP action, path, and controller action.

## Views
The user view pages are in the app/views/users directory.  The micropost view pages are in the app/views/microposts directory.  When a specific method is called by the controller, the corresponding view page is displayed.

## Controller
* The user controller is defined in the app/controllers/users_controller.rb file.  The micropost controller is defined in the  app/controllers/microposts_controller.rb file.
* The public methods index, show, new, edit, create, update, and destroy are defined in these controller files.  These methods are accessible to the web browser and have definitions in the config/routes.rb file.
* The private methods set_user, user_params, set_micropost, and micropost_params are defined in the controller as well.  These methods are not accessible to the web browser and do not have definitions in the config/routes.rb file.  However, the private methods are used by the public methods in the process of performing their functions.
