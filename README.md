![Bower version](https://img.shields.io/bower/v/vaadin-grid.svg) [![Build Status](https://travis-ci.org/vaadin/vaadin-grid.svg?branch=master)](https://travis-ci.org/vaadin/vaadin-grid) [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/vaadin/vaadin-core-elements?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

# &lt;vaadin-grid&gt;

[&lt;vaadin-grid&gt;](https://vaadin.com/elements/-/element/vaadin-grid) is a free, high quality data grid / data table [Polymer](http://polymer-project.org) element, part of the [Vaadin Core Elements](https://vaadin.com/elements).

```html
<script src="../webcomponentsjs/webcomponents-lite.js"></script>
<link rel="import" href="../iron-ajax/iron-ajax.html">
<link rel="import" href="vaadin-grid.html">

<dom-module id="my-grid">
  <template>
    <iron-ajax auto handle-as="json" last-Response="{{items}}"
    url="https://randomuser.me/api?results=100"></iron-ajax>

    <vaadin-grid demo items="[[items.results]]" visible-rows="8">
      <table>
        <colgroup>
          <col name="name.first" resizable>
          <col name="name.last" resizable>
          <col name="email"  resizable flex>
        </colgroup>
      </table>
    </vaadin-grid>
  </template>
  <script>
    Polymer({
      is: "my-grid"
    });
  </script>
</dom-module>
<my-grid></my-grid>
```

[<img src="https://github.com/vaadin/vaadin-grid/raw/master/screenshot.png" width="481" alt="Screenshot of vaadin-grid" />](https://vaadin.com/elements/-/element/vaadin-grid)

## Contributing

1. Fork the <component-name> repository.

1. Make sure you have [npm](https://www.npmjs.com/) installed.

1. When in the <component-name> directory, run `npm install` to install dependencies.


## Running demos and tests in browser

1. Install [polyserve](https://www.npmjs.com/package/polyserve): `npm install -g polyserve`

1. When in the <component-name> directory, run `polyserve --open`, browser will automatically open the component API documentation.

1. You can also open demo or in-browser tests by adding **demo** or **test** to the URL, for example:

  - http://127.0.0.1:8080/components/vaadin-date-picker/demo
  - http://127.0.0.1:8080/components/vaadin-date-picker/test


## Running tests from the command line

1. Install [web-component-tester](https://www.npmjs.com/package/web-component-tester): `npm install -g web-component-tester`

1. When in the <component-name> directory, run `wct` or `npm test`, browser will automatically open the component API documentation.


### &lt;vaadin-grid&gt; specific development instructions

The internal implementation of vaadin-grid (1.0) is written in [GWT](http://gwtproject.org), as it is based on the same implementation which is used in [Vaadin Framework 7](https://vaadin.com/framework).

Below are instructions how to work with the GWT/Java code:

#### Compiling the GWT module

The compiled module is in the repository (`vaadin-grid.min.js`), so you don't need to compile it unless you modify any `.java` files.

First, make sure you've installed all the necessary tooling:
- [Node.js](http://nodejs.org)
- [JDK8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
- [Maven](http://maven.apache.org/download.cgi)

Install [Gulp](http://gulpjs.com):

```shell
$ npm install -g gulp
```

Install npm dependencies:

```shell
$ npm install
```

Run the GWT compilation:

```shell
$ gulp gwt
```

Compiling using "pretty" output:
```shell
$ gulp gwt --gwt-pretty
```

#### Running and debugging in GWT SuperDevMode

To easily debug the Java code in the browser, use SDM:
```shell
$ gulp gwt:sdm
```


## Following the coding style

We are using [ESLint](http://eslint.org/) for linting JavaScript code. You can check if your code is following our standards by running `gulp lint`, which will automatically lint all `.js` files as well as JavaScript snippets inside `.html` files.


## License

Apache License 2.0