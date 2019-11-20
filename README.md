[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/software-engineering-immersive/)

# Asset Pipeline

[Launchschool Article](https://launchschool.com/blog/rails-asset-pipeline-best-practices)

- Allows for pre-processors such as Coffee, Sass, and ERb
- Minifies JS and CSS files
- Combines them all into one, so there are less requests to the server
- Browsers allow 10 parallel requests at any time, so if you have 15+ JS/CSS files, it can become a serious hindrance to load time

***How it works in a Nutshell***

- Your Javascript files and CSS files all get compressed into 2 files: application.js and application.css. 
- Those compressed files get sent down to the public/assets directory and are served up for your viewing pleasure. 
- Your images and other files in app/assets get sent down the pipe to public/assets as well and are served from there.

***Three Features***

- Concatenation
    - Rails uses Sprockets, a fancy term for puppetmaster, to take all your Javascript files and merge it into one single .js file. It does the same thing for CSS. This is brilliant because serving up less files means load times are that much faster.  
    - 15 Javascript or CSS files take longer than 1 Javascript or CSS file to load.

- Compression
    - Once those files have been merged together, they undergo a metamorphosis and are shrunk down to a more manageable size. Extra whitespace and comments are removed. 
    - When we code, our CSS files are formatted in a way to make things look pretty and visually appealing. But when you’re a machine, you don’t need comments or pretty indents and spaces. You’re a machine! And all this equates to faster loading times, since it’s less bits being transferred.

- Precompilation (of high-level languages)
    - Some of the best things about being a web developer right now is being able to use handy new next-gen higher-level languages. No longer do we have to survive by actually writing out every. single. HTML tag by hand. No longer do we have to write out lines and lines of code and make sure you get every bracket, comma, and semi-colon right. 
    - Now we have meta-languages like Coffeescript, Sass, ERB, HAML, and the list goes on! At this stage, our Rails Coffeescript and Sass files get converted – precompiled – to vanilla Javascript and CSS.



## Making our app look even better using Bootswatch

It's time to start paying attention to how our app looks. We've been learning and using Bootstrap for a little while now, so let's style our application! There is a wonderful resource called bootswatch that lets us use free templates which means we can use bootstrap and not have our app look like every other bootstrap page! 

#### Getting Started

We need to include a couple gems in order to get started. In our Gemfile let's include 

```ruby
gem 'bootstrap-sass'
gem 'bootswatch-rails'
```

After running `bundle` in the terminal, let's create a new file in our `app/assets/stylesheets` folder named `custom.css.scss` so that we can include our scss extentions. Now paste in the following code

```ruby
# The following will import variables, bootstrap itself, then the bootswatch style

@import "bootswatch/journal/variables";
@import "bootstrap";
@import "bootswatch/journal/bootswatch";

# If you want to import your own styles just use 

@import "name_of_scss file"

# Here are the free themes you can use:

// Amelia
// Cerulean
// Cosmo
// Cyborg
// Darkly
// Flatly
// Journal
// Lumen
// Paper
// Readable
// Sandstone
// Simplex
// Slate
// Spacelab
// Superhero
// United
// Yeti
```
