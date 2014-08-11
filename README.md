# coursebuilder-lti-module

This module adds support for [Learning Tools
Interoperability](http://www.imsglobal.org/lti/index.html) (LTI) versions 1.0
through 1.2 to [Course Builder](https://code.google.com/p/course-builder/). This
is not an official Google product.

LTI is a standard that allows different online learning tools to talk to each
other. It is provided by [IMS Global](http://www.imsglobal.org/), a nonprofit
member organization.

Course Builder is an open source platform for authoring and delivering online
educational content for hundreds of thousands of users.

## Requirements

You will need a Bash environment to run the installation scripts. The scripts
use standard developments tools, including Python 2.7, `git`, and `zip`/`unzip`.

## Configuration

To get started, clone this repo:

```sh
git clone https://github.com/google/coursebuilder-module-lti.git
```

Next, run the setup script:

```sh
sh scripts/setup.sh
```

This will download and install Course Builder to `examples/coursebuilder`. The
script will also patch the Course Builder install to make this module available.
Source files will be installed to `examples/coursebuilder/modules/lti`, and
tests will be installed to `examples/coursebuilder/tests/ext/lti`.

Once Course Builder is installed, you can run its scripts from
`examples/coursebuilder/scripts`. These include startup scripts, test scripts,
and so on. See
[the Course Builder documentation](https://code.google.com/p/course-builder/wiki/CourseBuilderChecklist)
for details.

## Development and testing

Once Course Builder is installed, you can start a local server with

```sh
sh examples/coursebuilder/scripts/start_in_shell.sh
```

You can run all tests with

```sh
python examples/coursebuilder/scripts/run_all_tests.py
```

and you can run the tests for the LTI module only with

```sh
sh examples/coursebuilder/scripts/test.sh tests.ext.lti.functional_tests
```

## Using the LTI module

Once you've got a Course Builder deployment running the LTI module, you must
configure it for use. See [the LTI implementation module
docs](https://github.com/google/coursebuilder-lti-module/tree/master/src/lti.py)
for details.
