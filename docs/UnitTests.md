# Unit Tests

The unit tests are based around [Mocha](http://mochajs.org/) and
[Sinon](http://sinonjs.org/). This gives a very simple mocking and test interface.

They are run using [Karma](https://karma-runner.github.io), which also provides
for code coverage.

# WebExtension Stubbing

WebExtensions are automatically stubbed by the
[sinon-chrome](https://github.com/acvetkov/sinon-chrome) package.

# Test Files

The test files live in the `test/unit` directory. `karma.conf.js` controls the
loading and running of tests.

# Running the Tests

```shell
$ npm run test:karma
```

# Viewing coverage output

You can view the code output in the `build/coverage/` directory, this is in html
format, so you can load it in the browser.

# Enabling Travis and Coveralls

Travis & Coveralls are both free to use for public repositories.

Note: If you do not intend to enable Coveralls, please drop the
`env -> global -> secure` option in `.travis.yml`.

* First of all, visit [coveralls.io](https://coveralls.io) and either start a new
  account, or sign in to your existing one.
* Go to `Add repo`.
* Find your repository and turn the status to `on`.
  * You may need to `Sync Repo` if it is a recently created repository.
* Click the `Details` button for the repository you just turned on and copy the
  `repo_token`.
* [Encrypt the environment variable](https://docs.travis-ci.com/user/environment-variables/#Encrypting-environment-variables)
  e.g.
  * `travis encrypt COVERALLS_REPO_TOKEN=my_repo_token`
* Copy the `secure: ...` output line and replace the `secure` line in `.travis.yml`
  with the contents.
* Commit & push the results.
* Go to `https://travis-ci.org/` and sign in.
* Go to your account settings if you're not already there.
* Find your repository and turn on Travis for it.
  * Again, you might need to sync your account.

Congratulations, you should now be set up. All pushes to your repository and pull
requests should automatically be tested. If the tests are successful, the code
coverage status will be published to the PR.
