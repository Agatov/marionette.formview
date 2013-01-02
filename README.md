# Marionette.Formview

A Flexible and customizable Backbone.Marionette Form View.

- Model Field Definitions
- Basic/Custom Field Validations
- Attaches to an existing Form on the DOM
- Use with Backbone Models

## Getting Started

This is a plugin built on top of the base Marionette ItemView.

Basic knowledge of Backbone(http://backbonejs.org/) and Backbone.Marionette(http://marionettejs.com/) is recommended

Quick JSFiddle Example : http://jsfiddle.net/hxvXL/1/(http://jsfiddle.net/hxvXL/1/)

```
var LoginFormView = Marionette.FormView.extend({

    el: '#formContainer',

    //define form fields
    fields: {
        email: {
            el: ".email",
            required: "Please enter a valid Email Address.",
            validations: {
                email: "Please enter a valid Email Address."
            }
        },
        password: {
            el: ".password",
            required: "Please enter your password.",
            validations: {
                password: "Please enter a valid Password."
            }
        }
    },

    //custom validation rules
    rules: {
        password: function(val) {
            return /^['a-zA-Z]+$/.test(val);
        }
    },

    //handle successful submissions
    onSubmit: function(evt) {
        evt.preventDefault();
    },

    //handle validation failures
    onSubmitFail: function(errors) {

    }
});
```

### Dependencies

- Marionette - v1.0.0-beta4

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using grunt.

## Release History

- 0.1.1 Minor Bug Fixes
- 0.1.0 Initial release

## License

Copyright (c) 2012 OneHealth Solutions, Inc
Licensed under the Apache 2.0 license.

## Author

Chris Miller