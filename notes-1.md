Ruby On Rails

gem install rails
rails -v
rails new first_app -T
rails server
rails server -b <IP address to bind>

# g as Generate
rails g model Pet name:string breed:string

rails db:migrate
rails db:migrate:status

/////
rails console

Pet.create name: "Papo", breed: "Calle"
Pet.first
Rails.application.credentials.hola

///
Secrets on Rails 
database.yml storage.yml credentials.yml.enc

EDITOR=vim rails credentials:edit

 EDITOR=nano rails credentials:edit --environment production
 	config/credentials/production.key 
 	config/credentials/production.yml.enc

 	RAILS_ENV=production rails c
	Rails.application.credentials.config

Assets
	Transformer
	Concatenator  ~ Handled by Sproket manifest file
	Compresor ~ Minify
	Fingerprinting

	Partials for assets (sections?)

	Yield ~ main content HTML

	Webpacker
	YARN

Scaffold
	rails g scaffold Book title:string author:string description:text isbn:string pages_cound:integer

		Creates model & db migration, controller, routes (using resources), views, entity helper, jbuilder and assets (sass)

Using HAML instead of ERB
	hamlit gem
Simple form gem 
	rails generate simple_form:install

dev gem
	gem install i18n-tasks
	i18n-tasks add-missing
Debuging
	bybug
	pry and pry-doc
		binding.pry
			ls Book.first
