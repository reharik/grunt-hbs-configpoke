# grunt-hbs-configpoke

> Take handlebars template, compile and render results to a file.  For use poking config files

## Getting Started
This plugin requires Grunt `~0.4.2`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-hbs-configpoke --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

Sorry about the docs here.  Had to whip it out.  Will write up docs and maybe even test soon as I can.  In meantime if you need help don't hesitate to email me.

```js
grunt.loadNpmTasks('grunt-hbs-configpoke');
```

## The "hbs_configpoke" task

### Overview
In your project's Gruntfile, add a section named `hbs_configpoke` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  hbs_configpoke: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
});
```

### Options

#### options.separator
Type: `String`
Default value: `',  '`

A string value that is used to do something with whatever.

#### options.punctuation
Type: `String`
Default value: `'.'`

A string value that is used to do something else with whatever else.

#### options.outputFormat
Type: `String`
Default value: ``
Possible values : ['xml', 'json']

### Usage Examples

#### Default Options
In this example, the default options are used to do something with whatever. So if the `testing` file has the content `Testing` and the `123` file had the content `1 2 3`, the generated result would be `Testing, 1 2 3.`

```js
grunt.initConfig({
  hbs_configpoke: {
    options: {},
    files: {
      'dest/default_options': ['src/testing', 'src/123'],
    },
  },
});
```

#### Custom Options
In this example, custom options are used to do something else with whatever else. So if the `testing` file has the content `Testing` and the `123` file had the content `1 2 3 &`, the generated result in this case would be `Testing: 1 2 3 &amp; !!!`

```js
grunt.initConfig({
  hbs_configpoke: {
    options: {
      separator: ': ',
      punctuation: ' !!!',
      outputFormat: 'xml'
    },
    files: {
      'dest/default_options': ['src/testing', 'src/123'],
    },
  },
});
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
0.1.1 added ability to specify output type ( xml, json ) and excaped endcoded characters
0.1.2 bug fix with string replace
