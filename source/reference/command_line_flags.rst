.. _command_line_flags:

***************
Command line flags
***************

venus run
----

Run tests specified as an argument to the -t or --test option. When this command is executed, venus will look for a `.venus` config file in the current directory or otherwise traverse upwards until one is found. If no config file is found you will recieve an error.

Options:

::

  -t, --test [tests]                Comma separated string of tests to run
  -p, --port [port]                 Port to run on

  -v, --verbose                     Run in verbose mode
  -d, --debug                       Run in debug mode

  -c, --coverage                    Generate Code Coverage Report

  -l, --locale [locale]             Specify locale to use

  --hostname                        Set hostname for test URLs, defaults to your ip address
  --require-annotations             Ignore JavaScript test files which do not contain a Venus annotation (@venus-*)

  -n, --phantom [path to binary]    Use PhantomJS client to run browser tests
  -s, --selenium [server url]       Use Selenium client to run browser tests
  --sauce-labs [server url]         Use Sauce Labs client to run browser tests

  --browser [browser|version]       Browser name and version to request from Selenium or Sauce Labs server
  --platform [platform]             Specify platform to use with Sauce Labs
  --username [username]             Specify username to use with Sauce Labs
  --access-key [accessKey]          Specify access key to use with Sauce Labs

  -h, --help                        Output usage information

Basic format:

::

  venus run -t [path to folder containing tests or single test file] [options]

venus init
----

Generates a `.venus` project folder with a boilerplate config file

Options:

::

  -v, --verbose                     Run in verbose mode
  -d, --debug                       Run in debug mode

  -l, --locale [locale]             Specify locale to use

  -h, --help                        Output usage information

Output:

::

  |-.venus/
    |-config
    |-adaptors/
    |-templates/
    |-libraries/

Boilerplate `.venus/config` file:

::

  // Configuration file for Venus
  // All paths can be relative (to the location of this config file) or absolute
  {
    default: {},
    libraries: {},
    binaries: {},
    static: {},
    includes: {},
    basePaths: {}
  }

venus demo
----

Runs an example venus test using Mocha and PhantomJS

Example: 

::

  venus demo