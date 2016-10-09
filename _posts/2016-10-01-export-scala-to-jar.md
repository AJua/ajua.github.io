---
title: export scala to runnable jar
category: Dev
tags: [scala]
---
If you use sbt to build you can use one of the one-jar plugins. They will put all dependencys into one big jar file (inclusive all the scala.jar files). This means that you only need one jar file and don't have to manage all the dependencys.

As an example with sbt-assembly (mostly copied from https://github.com/sbt/sbt-assembly):

project/plugins.sbt:

```
addSbtPlugin("com.eed3si9n" % "sbt-assembly" % "X.X.X")
```

build.sbt:

```
import AssemblyKeys._ // put this at the top of the file
seq(assemblySettings: _*)
```

then you can generate the jar with:

```
sbt assembly
```

參考 [export-scala-application-to-runnable-jar](http://stackoverflow.com/questions/8064699/export-scala-application-to-runnable-jar)
