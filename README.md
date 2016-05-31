Agency Leroy Developer Guidelines
==========

# Tools

## Dash

* Free
* Download: [http://kapeli.com/dash](http://kapeli.com/dash)
* Browse and search through APIs of different frameworks â€“ much faster than your browser

![http://f.cl.ly/items/0X1L1J0j1S3m0H113m26/Screen%20Shot%202013-08-12%20at%2008.56.40.png](http://f.cl.ly/items/0X1L1J0j1S3m0H113m26/Screen%20Shot%202013-08-12%20at%2008.56.40.png)

## ImageOtim

* Free
* Download: [https://imageoptim.com/](https://imageoptim.com/)
* Drag the whole img folder of a project into the window at it will compress all images with the optimal algorithms


## PG Commander

* Free
* Download: [http://eggerapps.at/pgcommander/](http://eggerapps.at/pgcommander/)
* Inspect and manipulate your PostgreSQL database

	![http://f.cl.ly/items/1j1P0N0D1h0I0S1y3z04/Screen%20Shot%202013-08-12%20at%2009.00.17.png](http://f.cl.ly/items/1j1P0N0D1h0I0S1y3z04/Screen%20Shot%202013-08-12%20at%2009.00.17.png)
	
## Postico

* Free
* Download: [https://eggerapps.at/postico/](https://eggerapps.at/postico/)
* Sucessor to PG Commander

	![https://eggerapps.at/postico/screenshots/table-content-view.png](https://eggerapps.at/postico/screenshots/table-content-view.png)


## Shuttle

* Free
* Download [http://fitztrev.github.io/shuttle/](http://fitztrev.github.io/shuttle/)
* Save SSH aliases for servers in an nice menu

![http://f.cl.ly/items/1F0u3x3v3t1l3u0T0b2x/Screen%20Shot%202013-08-12%20at%2009.01.39.png](http://f.cl.ly/items/1F0u3x3v3t1l3u0T0b2x/Screen%20Shot%202013-08-12%20at%2009.01.39.png)


## Codekit

* $25
* Buy: [http://incident57.com/codekit/](http://incident57.com/codekit/)
* Mostly for non-rails projects
* Compiles SASS, CoffeeScript etc automatically when you save your file, and refreshes your browser automatically, extremely useful if you code with a divided screen
* Losslessly compresses all images
* Sync project settings across the whole team of developers
* Combines and minifies

	![http://f.cl.ly/items/2F28002Q3J262o3y272l/Screen%20Shot%202013-08-12%20at%2009.03.10.png](http://f.cl.ly/items/2F28002Q3J262o3y272l/Screen%20Shot%202013-08-12%20at%2009.03.10.png)


## Git Tower

* 49€
* Buy: [http://www.git-tower.com/](http://www.git-tower.com/)
* If version-control in the commandline isn't for you
* Makes it really easy to do a lot of very compex git functions that would otherwise have you reading docs every time you want to do something a little different

![http://f.cl.ly/items/0f1F1M2J403M0S470A45/Screen%20Shot%202013-08-12%20at%2009.04.41.png](http://f.cl.ly/items/0f1F1M2J403M0S470A45/Screen%20Shot%202013-08-12%20at%2009.04.41.png)

## Editors

### Use whatever you like.

* Sublime Text
* Atom
* Vim
* Textmate
* Caffeinated
* Smultron
* Coda
* Espresso
* Dreamweaver.. just kidding


If you do choose Vim, please teach others.


# Front-end

## General

* Avoid inline comments
* Break long lines after 80 characters
* Delete trailing whitespace (get the SublimeText plugin)
* Don't include spaces after `(`, `[` or before `]`, `)`
* Don't vertically align tokens on consecutive lines
* If you break up an argument list, keep the arguments on their own lines and closing parenthesis on its own line
* If you break up a hash, keep the elements on their own lines and closing curly brace on its own line
* Indent continued lines two spaces
* Indent private methods equal to public methods
* Use 2 space indentation (no tabs)
* Use an empty line between methods
* Use newlines around multi-line blocks
* Use spaces around operators, after commas, after colons and semicolons, around `{` and before `}`

## CSS
* **SCSS** > SASS (more readable for new developers)
* **Bourbon** > Compass (not as heavy)

## SCSS

### Framework
* We use Zurb Foundation
* For most things, Foundation has an answer so it really pays off to read through the documentation carefully
* Always remove unused components from the SCSS imports

### Formatting
* Use hyphens when naming mixins, extends, classes & variables: `span-columns` not `span_columns` or `spanColumns`
* Use space between property and value: `width: 20px` not `width:20px`
* Use a blank line above selector that has styles
* Prefer hex color codes `#000`
* Use `//` for comment blocks not `/* */`
* Use a space between selector and `{`
* Use single quotation marks for attribute selectors and property values
* Use only lowercase, including colors
* Don't add a unit specification after 0 values, unless required by a mixin (`margin-top: 0` not `margin-top: 0px`)

### Order

* Place @extends and @includes at the top of your declaration list
* Place media queries directly after the declaration list
* Place concatenated selectors second
* Place pseudo states and elements third
* Place nested selectors last
* In Sublime Text, you can just press F5 to sort your selection alphabetically (might require plugin)

```scss
a {
  @includes transition(color, 0.35s);
  color: $link-color;
  &:hover {
    color: darken($link-color, 5%);
  }
  i {
    color: lighten($link-color, 10%);
  }
}
```

### Naming

* Use meaningful names: `$link-color` not `$link` or `$blue`
* **Append the prefix js- to ID's that are used by Javascript**

  ```html
  <nav id="js-dropdown">
    <ul>
      <li><a href="#">Item 1</a></li>
      <li><a href="#">Item 1</a></li>
    </ul>
  </nav>
  ```

* Avoid nesting more than 4 selectors deep

  Example:
  
  ### Bad:
  ------------


  ```scss
  header {
    nav {
      ul {
        li {
          a {
            color: #000;
          }
        }
      }
    }
  }
  ```

* Use HTML tags on vague classes that need a qualifier like `header.application` not `.main`
* Avoid using the HTML tag in the class name: `section.news` not `section.news-section`
* Avoid using HTML tags on classes for generic markup `<div>`, `<span>`: `.widgets` not `div.widgets`
* Avoid using HTML tags on classes with specific class names like `.featured-articles`
* Avoid using comma delimited selectors
* Avoid nesting within a media query

## BEM CSS

BEM stands for Block Element Modifier and provides a ruleset for naming of CSS classes. While the syntax might seem weird at first, the benefits provided clearly outweights any downsides. Each block should be built as a stand alone component that can be inserted anywhere on the webpage without breaking. The styling of each block should be separated into a single partial scss file, which may use globally defined variables and mixins.

The class naming follows the following syntax:

```scss
 .block {
   /* Component container styling */
 }
 .block__element {
   /* Styling of individual elements of the component */
 }
 .block__element--modifier {
   /* Styling of elements with a modifier, for example 'active' */
 }
```

### Folder structure

```
  # For SCSS
  - components
    - _panels.scss
    - _slideshows.scss
    - _tabs.scss
    - _side-nav.scss
  main.scss
  
  # For Javascript/Coffeescript
  - components
    - _panels.coffee
    - _slideshows.coffee
    - _tabs.coffee
    - _side-nav.coffee
```

### Naming

```scss
.tip {
  background: $secondary-color;
  &__title {
    color: #219251;
    font-size: 14px;
    font-weight: 500;
    margin: 0;
    padding: 0;
    text-transform: none;
  }
  &__content {
    padding: 0;
    margin: 0;
    font-size: 15px;
  }
  &--padded {
    padding: 30px;
  }
}
```

```html
  <div class='tip tip--padded'>
    <h4 class="tip__title">Title</h4>
    <p class='tip__content'>Content</p>
  </div>
```

### Special cases

If you want to have certain styling only applied to (for example) the frontpage, this is not defined in a frontpage.scss file but by using scss parent selector syntax:

```scss
  .hero {
    height: 600px;
    width: 100%;
    &__title {
      font-size: 36px;
      .frontpage & {
        font-size: 50px;
      }
    }
    &__content {
      font-size: 12px;
    }
  }
```

```html
<body class="frontpage">
	<div class="hero">
	  <h1 class="hero__title hero__title">Title</h1>
	  <p class="hero__content">
	    Body comes here.
	  </p>
	</div>
</body>
```

If the styling has to be applied to more than one page, consider using a --modifier instead:

```scss
    &__title {
      font-size: 36px;
      &--large & {
        font-size: 50px;
      }
   }
```

```html
<div class="hero">
  <h1 class="hero__title hero__title--large">Title</h1>
  <p class="hero__content">
    Body comes here.
  </p>
</div>
```

## JavaScript
* **CoffeeScript** > JavaScript (CoffeeScript encourages a more object-oriented design and is more readable and compiles to more efficient javascript code than most developers are capable of writing themselves, without making it any harder)
* React.js / Ember.js
* **Handlebars.js** templating
* Variables refering to a jQuery object are prepended with $

  Example:

  `var $dropdown = $('#main .language-dropdown');`

* Don't use the same jQuery selector multiple times, as it slows down the DOM. Rather save it in a reusable variable
  
  Example:

  ### Bad:
  ------------
   
  ```javascript
  $('header nav:first').addClass("first");

  $('header nav:first li a').click(function(){   
    return false;    
  });
  ```

  ### Good:
  -----------

  ```javascript
   $first_header = $('header nav:first');    
   $first_header.find('li a').click(function(e){    
      e.preventDefault();   
   });
  ```

## CoffeeScript

* Initialize arrays using `[]`
* Initialize empty objects and hashes using `{}`
* Use `CamelCase` for classes, `lowerCamelCase` for variables and functions, `SCREAMING_SNAKE_CASE` for constants, `_single_leading_underscore` for private variables and functions
* Prefer `is` to `==` or `===`
* Prefer `or` and and to `||` and `&&`

```JavaScript
if (el['option_type_name'] === key && el['name'] === value) {...}
```

```CoffeeScript
if el['option_type_name'] is key and el['name'] is value
```

## Templating
* **Twig** / **ERB**


## Optimization

1. Serve all assets minified, combined and gziped
2. "Smush" images with ImageOptim
3. Use CDN
4. Dns prefetch with for example `<link rel="dns-prefetch" href="//www.googletagservices.com" />` so that for example font-libraries load faster


# Back-end

## Ruby

* Avoid ternary operators (`boolean ? true : false`). Use multi-line if instead to emphasize code branches
* Avoid explicit return statements
* Don't use self explicitly anywhere except class methods (`def self.method`) and assignments (`self.attribute =`)
* Prefer `detect` over `find`
* Prefer `inject` over `reduce`
* Prefer `map` over `collect`
* Prefer `select` over `find_all`
* Prefer single quotes for strings
* Use `_` for unused block parameters
* Use `%{}` for single-line strings needing interpolation and double-quotes
* Use `&&` and `||` for Boolean expressions
* Use `{â€¦}` for single-line blocks. Use `do..end` for multi-line blocks
* Use `?` suffix for predicate methods.
* Use `CamelCase` for classes and modules, `snake_case` for variables and methods, `SCREAMING_SNAKE_CASE` for constants
* Use `def self.method`, not `def Class.method` or `class << self`
* Use `def` with parentheses when there are arguments
* Use `each`, not `for`, for iteration
* Use heredocs for multi-line strings

## Rails

* Ruby 1.9 syntax prefered over 1.8.* (`foo: "bar"` over `:foo => "bar"`) 
* Don't use SQL syntax outside of models
* Don't change a migration after it has been merged into master if the desired change can be solved with another migration
* Don't reference a model class directly from a view
* Don't use instance variables in partials. Pass local variables to partials from view templates:

  `<%= render 'article', :collection => @articles %>`
  
* When possible render collections like this:
  
  `<%= render @articles %>`

  It will call the _article partial

* If there are default values, set them in migrations:

  `change_column :bookings, :payment_status, :integer, :default => 0`

* Use only one instance variable in each view
* Always index foreign keys when adding relations

 Example:

 If `User` `has_many :articles` you will need to `add_index :articles, :user_id` in the database migration.


* Law of demeter (don't chain associations)

  ### Bad:
  ---------

  #### View: 
   `article.user.name`

  ### Good:
  ----------

  #### View: 
    `article.user_name`

  #### Model:   
  `delegate :name, to: :user, prefix: true`


* Use scopes or `def self.method`:
  
  ### Bad:
  ---------

  #### Controller:

  `Aricle.find_by_user_id(params[:user_id]).where(:updated_at < 1.month.ago..Time.now).page(3)`

  ### Good:
  ---------

  #### Model:

  `scope :recent, -> { where(:updated_at < 1.month.ago..Time.now) }`

  #### Controller:

  `user.articles.recent.page(3)`
  
* Avoid global variables
* Avoid long parameter lists
* Limit collaborators of an object (entities an object depends on)
* Limit an object's dependencies (entities that depend on an object)
* Prefer small methods. Between one and five lines is best
* Prefer small objects with a single, well-defined responsibility. When an object exceeds 100 lines, it may be doing too many things
* Avoid member and collection routes.
* Use private instead of protected when defining controller methods
* Name date columns with `_on` suffixes
* Name datetime columns with `_at` suffixes (`created_at`, `updated_at`)
* Name initializers by their gem name
* Order ActiveRecord associations alphabetically by attribute name
* Order ActiveRecord validations alphabetically by attribute name
* Order controller contents: filters, public methods, private methods
* Order model contents: constants, macros, public methods, private methods
* Put application-wide partials in the app/views/shared directory
* Use `def self.method`, not the `scope :method` DSL
* Use the default `render 'partial'` syntax over `render partial: 'partial'`

## PHP

* PHP is still a fact of life
* We use CraftCMS
* Snake case variable and function names, `$variable_name` and `some_function()` not `$variableName` and `someFunction()`
* One space in between operators and their operands: `$value / 2`, `$variable = 5`, `$variable <= 20`
* Function declarations and conditionals: opening bracket on the same line, one space each in before and after the parentheses: `if ($var > 0) {` not `if($var > 0){` or

  ```php
  if ($var > 0)
  {
    // ...
  }
  ```

* `else` should be on the same line as the closing bracket of the previous conditional and the opening bracket of the next block, like this: `} else {`
* Always use brackets for conditionals and loops, even for ones that run a single line of code

  ```php
  if ($var > 0) {
    some_function();
  }
  ```
not

 ```php
 if ($var > 0)
   some_function();
 ```
 
* Prefer `foreach` over `for` when applicable
* Prefer `echo` over `print`
* Prefer full tags over short tags: `<?php ?>` not `<? ?>`
* Files that only contain PHP should omit the end `?>` tag (as EOF is considered the end)
* Global variables: Avoid like crazy
* Always end statements in semicolons, even when PHP doesn't care: `<?php echo $variable; ?>` not `<?php echo $variable ?>`
* Declare new variables at the beginning of their scope
* Declare empty non-object variables as their type's empty primitive: `$some_array = array()`, `$some_string = ''`
* Single quotes for strings
* Use statement syntax for conditionals/loops when writing templates:

  ```php
  <?php foreach ($array as $key => $value): ?>
    <li><?php echo $value; ?></li>
  <?php endforeach; ?>
  ```

## Microframeworks

For static pages, we might want to consider using micro-frameworks such as

  * Phoenix (Elixir)
  * Flask (Python)
  * Revel (Go)
  * Sinatra (Ruby)
  * Camping (Ruby)
  * Padrino (Ruby)
  * Express (Node)
  * Scalatra (Scala)
  
We would just need one person who can take markup and plug it in to one of these frameworks and deploy


# Monitoring & Maintenance

## Notify when everything is working

Something you don't think about a lot is notifications about that everything is working. Maybe you have a Cron job that is supposed to do an expensive calculation every hour, but someone broke it and now it's not being executed. How do you know?

### Dead Man's Snitch

#### $19 / month

* Unlimited snitches
* You set the interval of how often a task should be run, for example "every 5 hours" and it will alert you if the task hasn't fired within that timespan

#### Free

* 1 snitch



## Notify when server goes down

### Pingdom

#### Free
   ---------
  * 1 website per server
  * 1 Real User Monitoring site
  * 20 SMS alerts per month
  
#### $39.95 / month
   ---------
  * 5 websites pers server
  * 200 SMS alerts per month
  

### Skylight

#### Free
  * Limited amount of requests
  * Better breakdown and insight than Newrelic
  * Only for Rails applications :(
   
  

### Newrelic


#### Free
---------
  * Alerts through iPhone app and email
  * Basic performance monitoring
  * Find bottlenecks and slow pages
  
  ![http://f.cl.ly/items/09350B442n0J3t1B3E0O/Screen%20Shot%202013-08-12%20at%2009.24.12.png](http://f.cl.ly/items/09350B442n0J3t1B3E0O/Screen%20Shot%202013-08-12%20at%2009.24.12.png)
  ![http://f.cl.ly/items/1g1N0x1Z0r412v2K1i0W/Screen%20Shot%202013-08-12%20at%2009.24.50.png](http://f.cl.ly/items/1g1N0x1Z0r412v2K1i0W/Screen%20Shot%202013-08-12%20at%2009.24.50.png)

## Restart unresponsive services and workers

### Monit

* Scripts already coded. Example:

	```
	check process nginx with pidfile /var/run/nginx.pid
      start program = "/etc/init.d/nginx start"
      stop program = "/etc/init.d/nginx stop"
      if children > 250 then restart
      if 5 restarts within 5 cycles then timeout
    ```


## Automated backups

  * Store on Amazon S3 & Glacier
  * Backs up uploaded assets and database
  * Scripts already coded

## Exception Notifications

We have to know every time a user sees an error, who the user is and the environment variables present at the time.

  * Airbrake ($45/month)
  * Exceptional ($9/month)
  * Errbit (free)
  * **Rollbar** [https://rollbar.com](https://rollbar.com)
  * Exception Notification (email only)
  
One of the best experiences you can have as a user after seing an error is someone emailing you ten minutes later telling you that the problem is fixed.

## A/B Testing

  ### Split
  
  * Easy to set up. Example:
  
  ```erb
  <% ab_test("login_button", "/images/button1.jpg", "/images/button2.jpg") do |button_file| %>
    <%= img_tag(button_file, :alt => "Login!") %>
  <% end %>
  ```
  * GUI:
  
  ![https://f.cloud.github.com/assets/78887/306152/99c64650-9670-11e2-93f8-197f49495d02.png](https://f.cloud.github.com/assets/78887/306152/99c64650-9670-11e2-93f8-197f49495d02.png)

# Server

* Serve all assets from CDN (Amazon Cloudfront & S3)
* Get a semi good server from DigitalOcean that can run multiple smaller sites
* Write config scripts for Chef/Puppet that automatically configures and installs a fresh Ubuntu server, so all our servers are configured exactly the same way. It should be as easy as writing cap:deploy:setup on the client to have a fully installed server and the website running five minutes later

## Reverse-proxy

* **Nginx**
* Varnish

## Web server

* **Puma** (need to investigate)

## Deployment

### Capistrano

* Scripts already exist and are ready

#### Commands
-------------

```
# Self-explanatory
cap deploy:start
cap deploy:restart
cap deploy:stop

# Opens a remote console
cap deploy:console

# Installs everything on a new server (use with care)
cap deploy:setup

# Deploy the latest version
cap deploy

# Deploy the latest version and migrate db
cap deploy:migrations

# Migrate database
cap deploy:db:migrate

# Bundle commands
cap deploy:bundle:<command>

# Show rails log
cap log:tail

```

## Code evaluation

We need to assure that the code we produce doesn't suck, especially since we're not doing a lot of TDD or BDD.

### Pair programming

When resources allow, have two people coding a feature together. This results in better code and ends up being a timesaver in the end, especially in bigger projects. One person is the lead and the other is the monitor for one hour, and then you switch around. Another benefit is that developers learn a lot from the other developer's workflow and style.

### Manually read commits

Don't deploy to the server without reading through commits. Github and bitbucket both allow commenting on commits and single lines in commits so use that to suggest code improvements or refactoring.

### Code Climate

* $74 per month (5 git repos)
* Automatically monitors your code for security issues and code quality
* Encourage writing better code and helps developers understand bottlenecks in their code

### Rails Best Practices

* `$ gem install rails_best_pratices`
* `$ rails_best_practices . -f html`
* Create a report on your Rails projects and finds issues such as missing database indexes, trailing whitespace, law of demeter etc

### Bullet

* Add `bullet` to you gemfile:

  ```ruby
  gem "bullet", :group => "development"
  ```
  
* Append to `config/environments/development.rb`:

```ruby
config.after_initialize do
  Bullet.enable = true
  Bullet.alert = true
  Bullet.bullet_logger = true
  Bullet.console = true
  Bullet.growl = true
  Bullet.xmpp = { :account  => 'bullets_account@jabber.org',
                  :password => 'bullets_password_for_jabber',
                  :receiver => 'your_account@jabber.org',
                  :show_online_status => true }
  Bullet.rails_logger = true
  Bullet.airbrake = true
end
```

## Test Driven Development

#### TBD

### Rspec

### Cucumber

## Continuous integration

#### Info to be added once we have defined what and how we test

### Semaphore

### CircleCI

### Codeship

* Automated Deployment

## Backup

In addition to backing up the database, use DigitalOcean's own backup system to create images of the full system.

# Email

We need to have a reliable system that delivers emails in production.

* **Sendgrid**
* Mailgun

Test mails on localhost using `gem mailcatcher`

# Git

A model git commit message:

```
[LW-217]Capitalized, short (50 chars or less) summary

More detailed explanatory text, if necessary.  Wrap it to about 72
characters or so.  In some contexts, the first line is treated as the
subject of an email and the rest of the text as the body.  The blank
line separating the summary from the body is critical (unless you omit
the body entirely); tools like rebase can get confused if you run the
two together.

Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
or "Fixes bug."  This convention matches up with commit messages generated
by commands like git merge and git revert.

Prefix your git message with the Github/ Bitbucket issue, for example [#125] or [GW-219].

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Typically a hyphen or asterisk is used for the bullet, preceded by a
  single space, with blank lines in between, but conventions vary here

- Use a hanging indent
```

# Things we need to get better at

* Cache and optimization
* Performance & Success metrics
* Split testing
* Maintenance (security updates!!)
* Continuous integration

# TO-DO
=========

  1. Create a Rails starter template / script to use for upcoming projects
  2. Create an account for Agency Leory on Amazon Web Services
