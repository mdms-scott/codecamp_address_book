rails new address_book
cd address_book

rails s
  show intro page

  $ rails g model person
      invoke  active_record
      create    db/migrate/20120827201209_create_people.rb
      create    app/models/person.rb
      invoke    test_unit
      create      test/unit/person_test.rb
      create      test/fixtures/people.yml

db/migrate/*_create_people.rb
  add attributes
    t.string  :first_name
    t.string  :last_name
    t.string  :email
    t.string  :phone

rake db:migrate
look at db/schema.rb

app/models/person.rb

rails g controller people
  $ rails g controller people
      create  app/controllers/people_controller.rb
      invoke  erb
      create    app/views/people
      invoke  test_unit
      create    test/functional/people_controller_test.rb
      invoke  helper
      create    app/helpers/people_helper.rb
      invoke    test_unit
      create      test/unit/helpers/people_helper_test.rb
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/people.js.coffee
      invoke    scss
      create      app/assets/stylesheets/people.css.scss

define index method
  fill in

create app/views/people/index.html.erb
  hello world!

delete intro page in public

rails s
  uh oh whats wrong?

config/routes.rb
  uncomment root line and change to people
  add resources line

refresh browser
  hey-o!

the basic table and such
  iterating and blocks
  calling ruby data in a view

but we need some data!?

controller
  create new action

app/views/people/new.html.erb
  rails form helper
  submit!
  ruh roh!

controller
  create create action
  params
  the save if else block
  redirection

browser
  try to create
  ruh roh mass assignment!

app/models/person.rb
  attr_accessible

browser
  refresh
  bingo!

but Matt I want to get to the new page without having to type it in!
  app/views/people/index.html.erb
  link_to
  paths! (rake routes)

but Matt, what if I want to delete someone?
  okay, if you rememebr from rake routes, there was a destroy
  make a delete link that points that that action
  click it
  ruh roh, no controller action!

controller
  create destroy action

browser
  delete
  bazinga!

but Matt what if I need to edit a contact?
  edit link
  unknown action again

controller
  create edit method
  find by params id
  test
  create update action
  update_attributes

but Matt what if I want to view one entry on its own?
  rake routes
  what is this show action?

controller
  create show action
  view link

app/views/people/show.html.erb
  string interpolation for full name
  displaying attributes