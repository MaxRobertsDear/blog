---
title: First Group Project - Day 8 Reflections
date: "2019-05-30T22:12:03.284Z"
description: Cleaning up the codebase
---

### Week 2, Thursday, Morning
This morning we discussed the user stories that revolved around where to redirect a user if a login fails. This was to ensure we have interpreted the client’s requirements correctly.

* Change redirect from login page to sign-up page.
* Update tests for user controller (coverage is currently 89%).
* Merge together branches.
* Update wiki with useful resources we’ve used.


### Reflection
Our wiki would be of more use to us if we were able to view the resources we referenced in order to solve issues. Our approach this morning will be to review active branches and, so we can have the same files for clarity, mob together to merge the branches that require merging before splitting up again into teams.

---

### Week 2, Thursday, Afternoon
We have now merged most branches and fixed conflicts / RSpec errors. Our app was not visible in heroku, despite deploying. After looking into the production environment, we realised that its database was out-of-date as it was missing a users table.
It was resolved using [this StackOverflow question](https://stackoverflow.com/questions/28416156/devise-user-sign-up-on-heroku-deployment) - we did find that the first solution here was unnecessary, and we only needed to:

Run `heroku pg:reset DATABASE --app “acebook-isambard”`

Run `heroku run rake db:migrate --app “acebook-isambard”`. 

The posts page now has a functioning delete button, allowing a user to delete their posts. However, a user can ONLY delete posts that they have made themselves. This was achieved by adding `<% if current_user.id == post.user_id %>` before displaying the delete button.

Understanding what the button should look like (and how to style it) in order to delete a post: [StackOverflow Question.](https://stackoverflow.com/questions/47966824/style-rails-button-to/47966832)

Determining what should be added to the PostsController in order to allow for a post to be deleted: [StackOverflow Question.](https://stackoverflow.com/questions/4177686/how-do-you-delete-an-activerecord-object)

### Reflection
We feel we haven't interacted with our client enough, so we will be reaching out to them today to see if they would like any final changes. We are prioritising the posts page this afternoon, by focusing on implementing likes and the editing of posts as well as minor bug fixes.

* Like and unlike posts.
* Edit posts.
* Time on posts is 1 hour out (fix).
* Order posts: most recent at top.
* Redirect to sign up.
* Finish merging of styling branch.
* Check-in with client.

---

### Retrospective
Although we did not complete the like functionality today, we did make great progress with adding features for the posts (deleting, editing).

[How to edit ActiveRecord attributes.](https://zaiste.net/rails_activerecord_updating_attributes_object_fields/)

The styling branches have also been merged. We realised we should also look into adding comments, however as we will be presenting our product tomorrow we need to determine how much of that feature we can implement before the presentation. Our focus tomorrow will be on fixing any current styling issues and working on adding likes.

---

### Useful links + problem solutions
* [Devise wiki - great starting point for many devise issues](https://github.com/plataformatec/devise/wiki/_pages)
* [How to make the Sign up page be root page (in Devise)](https://stackoverflow.com/questions/18903145/how-to-make-sign-up-page-be-root-page-in-devise)
* [How to redirect unauthorised visits](https://github.com/plataformatec/devise/wiki/Redirect-to-new-registration-(sign-up)-path-if-unauthenticated)
* By default, Devise's `authenticate_user!` filter will redirect unauthenticated users to the login page. 

Example:
```ruby
class PostsController < ApplicationController
  before_action :authenticate_user!
  def new
    @post = Post.new
  end
end
```

* [How to stub the authentication process when testing](https://github.com/plataformatec/devise/wiki/How-To:-Stub-authentication-in-controller-specs)
* make sure to also load the test helpers into spec/rails_helper.rb

```ruby
require 'spec_helper'
require 'rspec/rails'
# note: require 'devise' after require 'rspec/rails'
require 'devise'

RSpec.configure do |config|
  # For Devise > 4.1.1
  config.include Devise::Test::ControllerHelpers, :type => :controller
  # Use the following instead if you are on Devise <= 4.1.1
  # config.include Devise::TestHelpers, :type => :controller
end
```
