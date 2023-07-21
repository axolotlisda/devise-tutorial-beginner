# devise-tutorial-beginner

Installing Devise Gem on an Application

1. Add Devise Gem
# Open up your Gemfile which can be seen on RootDirectory-of-your-rails-app/Gemfile and add this line:
gem 'devise'

save the changes to the gemfile

Then run this code on the rails console:
bundle install

2. Set up devise in your app

# Run the following command in the terminal:
rails g devise:install

3. Configure Devise
# Ensure you have defined default url options in your environments files. Open up config/environments/development.rb and add this line:

config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }
Open up app/views/layouts/application.html.erb and add:

<% if notice %>
  <p class="alert alert-success"><%= notice %></p>
<% end %>
<% if alert %>
  <p class="alert alert-danger"><%= alert %></p>
<% end %>
right above

 <%= yield %>
Open up app/views/ideas/show.html.erb and remove the line that says:

<p id="notice"><%= notice %></p>
Do the same for app/views/comments/show.html.erb. These lines are not necessary as we’ve put the notice in the app/views/layouts/application.html.erb file.
4. Setup the User model
# We’ll use a bundled generator script to create the User model.

rails g devise user
rake db:migrate
Coach: Explain what user model has been generated. What are the fields?

5. Create your first user
# Now that you have set everything up you can create your first user. Devise creates all the code and routes required to create accounts, log in, log out, etc.

Make sure your rails server is running, open http://localhost:3000/users/sign_up and create your user account.
