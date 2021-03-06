# conan-fakeit

| Bintray | Travis(develop) | Travis(latest stable) |
|---------|-----------------|-----------------------|
|[ ![Download](https://api.bintray.com/packages/gasuketsu/conans/FakeIt%3Agasuketsu/images/download.svg) ](https://bintray.com/gasuketsu/conans/FakeIt%3Agasuketsu/_latestVersion)|![Build Status](https://travis-ci.org/gasuketsu/conan-fakeit.svg?branch=develop)|![Build Status](https://travis-ci.org/gasuketsu/conan-fakeit.svg?branch=stable/2.0.5)|

[Conan.io](https://conan.io) package for [FakeIt](https://github.com/eranpeer/FakeIt)

FakeIt is a simple mocking framework for C++. It supports GCC, Clang and MS Visual C++.

## Build and test the package

Install the Conan package manager and the Conan package tools with pip

    $ pip install conan

Then build and test the package with

    $ conan create . <reference>

## Using the package

### Installation

You can manually install this package to your local cache by running

    $ conan install --options integration=standalone FakeIt/<version>@gasuketsu/stable

If you handle multiple dependencies in your project it's better to add a *conanfile.txt*

    [requires]
    FakeIt/<version>@gasuketsu/stable

    [options]
    FakeIt:integration=standalone

    [generators]
    cmake

Then you can install all requirements for your project by running

    $ conan install .

For further information on how to use Conan packages see the [Conan documentation](http://docs.conan.io/)

### Options

#### `integration`

FakeIt can be pre-configured to work with some of the major unit testing frameworks. A pre-configured
version will use the assertions mechanism of the unit testing framework to integrate the generated
error messages into the unit testing framework output.

The following frameworks are supported:

- [Boost Test](http://www.boost.org/doc/libs/release/libs/test) using `FakeIt:integration=boost`
- [Catch](https://github.com/philsquared/Catch) using `FakeIt:integration=catch`
- [Google Test](https://github.com/google/googletest) using `FakeIt:integration=gtest`
- [mettle](https://github.com/jimporter/mettle) using `FakeIt:integration=mettle`
- [MSTest](http://en.wikipedia.org/wiki/Visual_Studio_Unit_Testing_Framework) using `FakeIt:integration=mstest`
- [QTest](http://doc.qt.io/qt-5/qttest-index.html) using `FakeIt:integration=qtest`
- [tpunit++](https://github.com/tpounds/tpunitpp) using `FakeIt:integration=tpunit`
- [NUnit](https://nunit.org/) using `FakeIt:integration=nunit`

By default FakeIt is configured without any framework integration using `FakeIt:integration=standalone`.
