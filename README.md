# Sparrow

Sparrow is a Scala library for converting Spark Dataframe rows to case classes.

[![Build Status](https://travis-ci.org/ypg-data/sparrow.svg)](https://travis-ci.org/ypg-data/sparrow)
[![Join the chat at https://gitter.im/ypg-data/sparrow](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ypg-data/sparrow)
[![Download latest version](https://api.bintray.com/packages/ypg-data/sparrow/sparrow/images/download.svg)](https://bintray.com/ypg-data/sparrow/sparrow/_latestVersion)

## Status

The project is still in an experimental state and the API is subject to change
without concerns about backward compatibility.

## Requirements

This library requires Spark 1.3+.

## Limitations and Known Issues

 - Fields of type `java.sql.Timestamp` is not supported.
 - Custom wrapper fields types is not supported.
 - Conversion of certain other field types are not supported.

See the [CodecLimitationsTest](core/src/test/scala/com.mediative.sparrow/CodecLimitationsTest.scala) for details.

## Getting Started

The best way to get started at this point is to read the [API
docs](https://ypg-data.github.io/sparrow/api) and look at the [examples in the
tests](https://github.com/ypg-data/sparrow/tree/master/core/src/test/scala/com.mediative.sparrow).

To use the libray in an SBT project add the following two project settings:

    resolvers += Resolver.url("Sparrow Releases", url("https://dl.bintray.com/ypg-data/sparrow"))(Resolver.ivyStylePatterns)
    libraryDependencies += "com.mediative" %% "sparrow" % "0.1.0"

## Building and Testing

This library is built with SBT, which needs to be installed. To run the tests
and build a JAR run the following commands from the project root:

    $ sbt test
    $ sbt package

To build a package for Scala 2.11 run the following command:

    $ sbt ++2.11.7 test package

## Contributing

Bugs and feature requests should be reported in the [GitHub issue
tracker](https://github.com/ypg-data/sparrow/issues/new) and answer the
following questions:

 - Motivation: Why should this be addressed? What is the purpose?
 - Input: What are the pre-conditions?
 - Output: What is the expected outcome after the issue has been addressed?
 - Test: How can the results listed in the "Output" be QA'ed?

For code contributions, these are the suggested steps:

 - Identify the change you'd like to make, e.g. fix a bug or add a feature.
   Larger contributions should always begin with [first creating an
   issue](https://github.com/ypg-data/sparrow/issues/new) to ensure that the
   change is properly scoped.
 - Fork the repository on GitHub.
 - Develop your change on a feature branch.
 - Write tests to validate your change works as expected.
 - Create a pull request.
 - Address any issues raised during the code review.
 - Once you get a "+1" on the pull request, the change can be merged.

## Releasing

To release version `x.y.z` run:

    $ sbt release -Dversion=x.y.z

This will take care of running tests, tagging and publishing JARs and API docs.

## License

Copyright 2015 Mediative

Licensed under the Apache License, Version 2.0. See LICENSE file for terms and
conditions for use, reproduction, and distribution.
