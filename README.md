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

Currently, IMS Global certifies this module's LTI provider for LTI 1.0.

## Requirements

You will need a Bash environment to run the installation scripts. The scripts
use standard developments tools, including `python` version 2.7, `git`, and `zip`/`unzip`.

## Configuration

Course Builder modules are managed by Course Builder. To get started with this module, first clone the Course Builder repository:

```sh
git clone https://code.google.com/p/course-builder
```

Next, change directory to the Course Builder root:

```sh
cd course-builder/coursebuilder
```

Finally, use `scripts/modules.sh` to install this module:

```sh
sh scripts/modules.sh \
  --targets=lti@https://github.com/google/coursebuilder-lti-module
```

You can then start a local server and the module will be ready for configuration:

```sh
sh scripts/start_in_shell.sh
```

## Using the LTI module

Once you've got a Course Builder deployment running the LTI module, you must
configure it for use. See [the LTI implementation module
docs](https://github.com/google/coursebuilder-lti-module/tree/master/src/lti.py)
for details.


## Development and testing

To do development on this module, keep in mind that Course Builder owns the local setup of the module on your machine rather than the other way around. In particular, Course Builder owns where this module's source lives, which is in `$HOME/coursebuilder_resources/modules/lti`. That directory is a git repository with a remote at the git address you passed to `modules.sh`, which in this case is `https://github.com/google/coursebuilder-lti-module`.

You can modify module code and execute git commands here as you would normally. Additionally, the tests and source of this module are available under your Course Builder root directory via the following two symlinks:

```sh
modules/lti -> $HOME/coursebuilder_resources/modules/lti/src
tests/ext/lti -> $HOME/coursebuilder_resources/modules/lti/tests
```

but keep in mind that the Course Builder directory has a git repository for Course Builder, not for your module.

With this setup, you can start your server as you would with vanilla Course Builder, and the LTI module will be installed and ready for configuration:

```sh
sh scripts/start_in_shell.sh
```

You can run the LTI module's tests with

```sh
sh scripts/test.sh tests.ext.lti.functional_tests
```

and they are run when you execute the full Course Builder test suite:

```sh
python scripts/run_all_tests.py
```
