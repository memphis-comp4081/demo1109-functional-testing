
# Demo 11/09: Functional Testing in Rails

## Resources
* Video: https://youtu.be/1IxqsIWCbuc
* Rails Guide Documentation: http://guides.rubyonrails.org/testing.html#functional-tests-for-your-controllers
* Devise Documentation: https://github.com/plataformatec/devise
 
## Goals
* Testing Page with No Authentication ([6:15](https://youtu.be/1IxqsIWCbuc?t=6m15s))
  - Methods:
    + `get blah_blah_url`
    + `assert_response :success`
  - Commands:
    + `rails test`
  - Subgoal: Fix generated fixture ([12:00](https://youtu.be/1IxqsIWCbuc?t=12m00s))
  - Subgoal: Check that the correct HTML/ERB template was used ([21:10](https://youtu.be/1IxqsIWCbuc?t=21m10s))
    + Gem: `rails-controller-testing`
    + Method: `assert_template :blah_blah`
* Testing Page with Devise Authentication ([25:23](https://youtu.be/1IxqsIWCbuc?t=25m23s))
  - Included module: `Devise::Test::IntegrationHelpers`
  - Method: `sign_in blah_blah`
* Create many-to-many association between User and Book model classes ([39:42](https://youtu.be/1IxqsIWCbuc?t=39m42s))
  - Commands:
    + `rails g model BooksUsers book:references user:references`
    + `rails d model UsersBooks` (to undo a mistake)
    + `rails c` (Rails console, e.g., for trying out model classes)
  - Method: `has_and_belongs_to_many :blah_blahs, optional: true`
  - Pitfall: Join tables must have the names in alphabetical order (i.e., `BooksUsers` is OK, but `UsersBooks` is not).
