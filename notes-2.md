Ruby on Rails - Proyect

rails new organizador -T --database=postgresql
yarn add bootstrap jquery popper.js
yarn add roboto-fontface 

rails g simple_form:install --bootstrap
	
rails g scaffold Category name:string description:text

rails g scaffold Task name:string description:text due_date:date category:references

rails db:create
Then
rails db:migrate
Or
rails db:setup ~ create and migrate

Step check: db/schema.rb and migration files

Installing annotate gem
bi ~ bundle install

annotate --models


i18n-tasks add-missing

Adding rails-i18n gem

Adding models' validations

Adding devise to manage Users
	rails g devise:install  (creates config initializers and locales)
	Model creation "rails g devise User"

	Devise will add new routes and we can check them by "rails routes"
	http://192.168.1.212:3000/rails/info/routes

Protecting Application routes with Devise authentication

Adding a link to log out in the Application layout
	Using link_to view helper

Updating a model, adding a new column ~ user relationship
	rails g migration AddOwnerToTask user:references
	Using a model's property name that doesn't match the db column name
	Using "rails db:reset" to rerun the migrations since there are new columns that
	don't allow nulls. For production live systems instead of running a reset we could 
	use a 3 step migration, one that allows nulls in the new column, populate the column
	and a 3rd migration to avoid nulls

Cancancan gem to control the access
Using rescue_from in the controller to catch exceptions

Model Callbacks
	https://guides.rubyonrails.org/active_record_callbacks.html
 
Using rails db:seed to populate data
	db/seeds.rb
rails g migration addCodeToTask code:string

rails g mailer ParticipantMailer
	Creating email notification when a new task is created
	Using the letter_opener gem to test the email templates in development
		config/environments/development.rb


