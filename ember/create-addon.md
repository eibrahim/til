#Create an Ember addon and use in development


* `ember addon my-addon`
* For live reload when developing an addon use the isDevelopingAddon hook:
  ```
  // addon index.js
  isDevelopingAddon: function() {
    return true;
  }
  ```
* Run `npm link` from the root of your addon project. This will make your addon locally available by name.
* In your project folder run `npm link my-addon`
* In your project `package.json` require `my-addon: '*'`
* Now you can use `ember g my-addon` in your project

PS: More details at [http://ember-cli.com/extending/#link-to-addon-while-developing](http://ember-cli.com/extending/#link-to-addon-while-developing)

