Style
=====

A guide for programming in style.

High level guidelines:

* Be consistent.
* Don't rewrite existing code to follow this guide.
* Don't violate the conventions without a good reason.

Git
---

* Avoid including files in source control that are specific to your
  development machine or process.
* Delete local and remote feature branches after merging.
* Perform work in a feature branch.
* Use @username in review comments
* Rebase frequently to incorporate upstream changes.
* Use a [pull request](http://goo.gl/Kmdee) for code reviews.
* Write a [good commit message](http://goo.gl/w11us).

Formatting
----------

* Avoid inline comments.
* Break long lines after 80 characters.
* Delete trailing whitespace.
* Don't include spaces after `(`, `[` or before `]`, `)`.
* Don't vertically align tokens on consecutive lines.
* If you break up an argument list, keep the arguments on their own lines and
  closing parenthesis on its own line.
* If you break up a hash, keep the elements on their own lines and closing curly
  brace on its own line.
* Indent continued lines two spaces.
* Indent private methods equal to public methods.
* Use 2 space indentation (no tabs).
* Use an empty line between methods.
* Use spaces around operators, after commas, after colons and semicolons, around
  `{` and before `}`.
* Don't misspell.
* Use [Unix-style line endings](http://goo.gl/04ehM) (`\n`).

Naming
------

* Avoid abbreviations.
* Avoid types in names (`user_array`).
* Name the enumeration parameter the singular of the collection.
* Name variables, methods, and classes to reveal intent.
* Treat acronyms as words in names (`XmlHttpRequest` not `XMLHTTPRequest`),
  even if the acronym is the entire name (`class Html` not `class HTML`).
* Name variables created by a factory after the factory (`user_factory`
  creates `user`).

CSS / LESS / SASS
-----------------



JavaScript
----------

* Use CoffeeScript.

CoffeeScript
------------

* Initialize arrays using `[]`.
* Initialize empty objects and hashes using `{}`.
* Use `CamelCase` for classes, `lowerCamelCase` for variables and functions,
  `SCREAMING_SNAKE_CASE` for constants, `_single_leading_underscore` for
  private variables and functions.
* Prefer `is` to `== ` or `===`
* Use `&&` and `||` for Boolean expressions.

Ruby
----

[Sample](/sientia/guides/blob/master/style/samples/ruby.rb)

* Prefer `detect` over `find`.
* Prefer `inject` over `reduce`.
* Prefer `map` over `collect`.
* Prefer `select` over `find_all`.
* Prefer single quotes for strings.
* Use `%{}` for single-line strings needing interpolation and double-quotes.
* Use `&&` and `||` for Boolean expressions.
* Use `{...}` for single-line blocks. Use `do..end` for multi-line blocks.
* Use `?` suffix for predicate methods.
* Use `CamelCase` for classes and modules, `snake_case` for variables and
  methods, `SCREAMING_SNAKE_CASE` for constants.
* Use `def self.method`, not `def Class.method` or `class << self`.
* Use `def` with parentheses when there are arguments.
* Use `each`, not `for`, for iteration.
* Use [heredocs](http://rubyquicktips.com/post/4438542511/heredoc-and-indent) for 
  multi-line strings.


Rails
-----

* Avoid `member` and `collection` routes.
* Avoid the `:except` option in routes.
* Use the `:only` option to explicitly state exposed routes.
* Don't reference a model class directly from a view.
* Don't use protected controller methods.
* Name initializers for their gem name.
* Order Mongoid associations alphabetically by attribute name.
* Order Mongoid validations alphabetically by attribute name.
* Order controller contents: filters, public methods, private methods.
* Order model contents: constants, macros, public methods, private methods.
* Order resourceful routes alphabetically by name.
* Put application-wide partials in the
  [`app/views/application`](http://goo.gl/5Z8Vv) directory.
* Use `_path`, not `_url`, for named routes everywhere except mailer views.
* Never use `url_for` helper!
* Use the default `render 'partial'` syntax over `render partial: 'partial'`.
* Don't use non RESTful public methods in controllers
* Avoid => Hashes

Background Jobs
---------------

* Put sidekiq classes in `app/workers`.

Email
-----

* always use multipart

Testing
-------

[Sample](/thoughtbot/guides/blob/master/style/samples/testing.rb)

* Factories:
  * Avoid listing a lot of traits in tests - create specific factories instead, consisting of traits.
  * Keep factories minimal.
  * Order contents:
    * definitions
    * sequences
    * traits.
  * Order attributes:
    * implicit attributes
    * explicit attributes
    * child factory definitions
    * --> each section's attributes are alphabetical!
  * Order factory definitions alphabetically by factory name.
  * Have an individual `<model_name_plural>.rb` file per model.
* Describing specs:
  * Don't prefix `it` block descriptions with 'should' (not `it "should do something"` but `it "does something"`).
  * Name outer `describe` blocks after the method under test. Use `describe ".method"` for class methods and `describe "#method"` for instance methods.
  * Use "double quoted strings" for descriptions (`it "checks object's state"` is easier to read than `it 'checks object\'s state'`).
* Model specs:
  * Order Mongoid association tests alphabetically by attribute name.
  * Order Mongoid validation tests alphabetically by attribute name.

* Prefer `eq` to `==` in RSpec.
* Separate setup, exercise, verification, and teardown phases with newlines.
* Use an `it` example for each execution path through the method.
* Use [stubs and spies](http://goo.gl/EciDJ) (not mocks) in isolated tests.
