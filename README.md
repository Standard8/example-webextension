[![Build Status](https://travis-ci.org/Standard8/example-webextension.svg?branch=master)](https://travis-ci.org/Standard8/example-webextension)
[![Coverage Status](https://coveralls.io/repos/github/Standard8/example-webextension/badge.svg?branch=master)](https://coveralls.io/github/Standard8/example-webextension?branch=master)

This repository is intended as an example repository containing templates and good
practices for creating a
[WebExtension based add-on](https://developer.mozilla.org/Add-ons/WebExtensions)
for Firefox.

# Aims

The aim of this repository is to bring together tools and services into a
template/example repository, so that add-on developers can have a good starting
point for created WebExtensions that includes testing suites.

# What's here

This repository includes a small WebExtension as an example, and includes the
infrastructure to build and test it using Firefox.

It has test suites for [lint](https://en.wikipedia.org/wiki/Lint_(software)),
[unit](https://en.wikipedia.org/wiki/Unit_testing), and
[integration/](https://en.wikipedia.org/wiki/Integration_testing)
[functional](https://en.wikipedia.org/wiki/Functional_testing)
testing. There's also code coverage for the unit tests.

Additionally the test suites are run on the Travis service providing continuous
testing coverage. This may be reflected in a developer's own repository where it
is open source, providing coverage of pull requests etc.

# Quick Start

* Copy the files from this repository into a new one you've created (don't forget
  the .* files, but not the .git folder!).
* Edit `package.json` and `manifest.json` to set up the names and information for
  your extension. Also edit the `message.json` files in `add-on/_locales/` to set
  up the user visible names and descriptions.
* Run `npm install`
* Run `npm test` to check that everything is OK.
  * You may need to update `module.exports.promiseAddonButton` with the new add-on
    name.

If you're publishing your extension on github:

* Create a repository on github (if you haven't already), and commit & push the code.
* Enable [Travis & Coveralls](docs/UnitTests.md#enabling-travis-and-coveralls).
  * Update the top of this README.md if you want the correct badges for your test
    status & code coverage displayed.
* Enable a [module updating tool](docs/ModulesUpdating.md).

# Source Tree Outline

* `add-on/`
  * The add-on source code. In a separate directory so that the `web-ext` tool
    will only ship files in that directory.
* `docs/`
  * Useful documents!
* `test/`
  * Tests for the add-on including unit and functional tests.
* `.eslintrc.js`, `.eslintignore`
  * The configuration for [eslint](http://eslint.org/), used to
    [lint](https://en.wikipedia.org/wiki/Lint_(software)) the code.
* `.travis.yml`
  * Setup for continuous integration via [Travis CI](https://travis-ci.org/) -
    default setup is to build every time you push or someone creates a PR.
* `karma.config.js`
  * The configuration for running the functional tests in `test/functional`.

# Documentation

It is intended that all parts of this repository have at least outline
documentation. If you find any parts that are missing, please file an issue or
create a PR.

* [Building, running code and tests](docs/Developing.md)
* [Keeping modules up to date via automated services](docs/ModulesUpdating.md)
* Testing
  * [Linting](docs/Linting.md)
  * [Unit Tests](docs/UnitTests.md)
  * [Functional Tests](docs/Functional.md)

# Issues

If you've found an issue with WebExtensions themselves, or wish to discuss them
further, please use the
[add-ons community on discourse](https://discourse.mozilla-community.org/c/add-ons)

For issues and items not working properly in this repository, please see the
[issues list](https://github.com/standard8/example-addon-repo/issues), or file a new one.
