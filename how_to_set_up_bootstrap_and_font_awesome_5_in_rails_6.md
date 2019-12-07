### How to Set Up Bootstrap 4 and Font Awesome 5 in Rails 6
- Add the following to `Gemfile`:
  ```
  gem 'bootstrap',  '~>4.3.1'`
  gem 'font_awesome5_rails'
  ```
- `mkdir app/javascript/stylesheets`
- Create new file `app/javascript/stylesheets/_custom.scss`. You can put any custom scss in this file. 
- Create new file `app/javascript/stylesheets/application.scss` with the following contents:
  ```
  @import "bootstrap";
  @import '@fortawesome/fontawesome-free';
  @import 'custom';
  ```
- Change `stylesheet_link_tag` to `stylesheet_pack_tag` in `views/layouts/application.html.erb`. 
- `yarn add bootstrap jquery popper.js @fortawesome/fontawesome-free`
- Replace the contents of `config/webpack/environment.js` with the following:
  ```
  const { environment } = require("@rails/webpacker");
  const webpack = require("webpack");
  environment.plugins.append(
  "Provide",
  new webpack.ProvidePlugin({
  $: "jquery",
  jQuery: "jquery",
  Popper: ["popper.js", "default"]
  })
  );
  module.exports = environment;
  ```
- Create new file `app/javascript/packs/custom.js` with the following contents:
  ```
  $(function() {
    $('[data-toggle="tooltip"]').tooltip();
  });
  
  $(function() {
    $('[data-toggle="popover"]').popover();
  });
  ```
- Add the following lines to `app/javascript/packs/application.js`: 
  ```
  import "bootstrap";
  import "../stylesheets/application";
  import "./custom";
  import "@fortawesome/fontawesome-free/js/all";
  
  window.jQuery = $;
  window.$ = $;
  ```

- At this point, `tree app/javascript` should print out:
  ```
  app/javascript/
  ├── channels
  │   ├── consumer.js
  │   └── index.js
  ├── packs
  │   ├── application.js
  │   └── custom.js
  └── stylesheets
      ├── application.scss
      └── _custom.scss
  
  3 directories, 6 files
  ```
- Restart your server.

[Source](https://hackernoon.com/integrate-bootstrap-4-and-font-awesome-5-in-rails-6-u87u32zd)
