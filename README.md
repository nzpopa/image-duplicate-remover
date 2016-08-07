# image-duplicate-remover

> Remove duplicate images from the two given directories recursively

[![Ubuntu build Status](https://travis-ci.org/paazmaya/image-duplicate-remover.svg?branch=master)](https://travis-ci.org/paazmaya/image-duplicate-remover)
[![Windows build status](https://ci.appveyor.com/api/projects/status/gmjc0bi0bbydb667/branch/master?svg=true)](https://ci.appveyor.com/project/paazmaya/image-duplicate-remover/branch/master)
[![codecov](https://codecov.io/gh/paazmaya/image-duplicate-remover/branch/master/graph/badge.svg)](https://codecov.io/gh/paazmaya/image-duplicate-remover)

Too many images that are the same but might have different dates and other metadata.
This tool compares images based on the following criteria:

* [x] SHA-256 hash of the file, since `v0.1.0`
* [ ] File size in bytes
* [ ] Width and height
* [ ] Bit depth
* [ ] Number of unique colors

Please note that the minimum supported version of [Node.js](https://nodejs.org/en/) is `4.2.0`.

Underneath [SQLite](https://github.com/mapbox/node-sqlite3) is used for storing any meta information about the files,
as sometimes the amount of files to compare is huge.

## Installation

Make sure to have [GraphicsMagick](http://www.graphicsmagick.org/) available in the `PATH`.
It can be installed for example in Mac via [Brew](http://brew.sh):

```sh
brew install graphicsmagick
```

In Ubuntu it is usually available via:

```sh
sudo apt-get install graphicsmagick
```

Now install the command line tool globally, which might need increased privileges:

```sh
[sudo] npm install --global image-duplicate-remover
```

## Command line options

```sh
image-duplicate-remover --help
```

```sh
image-duplicate-remover [options] <primary directory> <secondary directory>

  -h, --help            Help and usage instructions
  -V, --version         Version number
  -v, --verbose         Verbose output, will print which file is currently being processed
  -n, --dry-run         Try it out without actually removing anything

Version 0.1.0
```

### Example commands

The following command shows how two folders are compared, but nothing will be removed since the `--dry-run` option is used.

```sh
image-duplicate-remover -vn a b
```

## Contributing

First thing to do is to file [an issue](https://github.com/paazmaya/image-duplicate-remover/issues).

[Please refer to a GitHub blog post on how to create somewhat perfect pull request.](https://github.com/blog/1943-how-to-write-the-perfect-pull-request "How to write the perfect pull request")

Then possibly open a Pull Request for solving the given issue.
[ESLint](http://eslint.org) is used for linting the code and unit testing is done with [tape](https://github.com/substack/tape).

Execute them by running:

```sh
npm install
npm run lint
npm test
```

Automated testing is done against [Ubuntu Trusty at Travis CI](https://travis-ci.org/paazmaya/image-duplicate-remover/)
and [Windows at AppVeyor](https://ci.appveyor.com/project/paazmaya/image-duplicate-remover).

## Version history

* `v0.1.0` (2016-08-)
    - Gets the job simply done, hence first release

## License

Licensed under [the MIT license](LICENSE).

Copyright (c) [Juga Paazmaya](https://paazmaya.fi) <paazmaya@yahoo.com>

