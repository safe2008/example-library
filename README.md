# example-library

Example library to be published in GitHub.

This project is the result of the following tutorial: https://medium.com/@supermanue/how-to-publish-a-scala-library-in-github-bfb0fa39c1e4

```bash
$HOME/.sbt/1.0/github.sbt
credentials += 
  Credentials(
    "GitHub Package Registry",
    "maven.pkg.github.com",
    "USERNAME",
    "TOKEN")

export GITHUB_TOKEN=xxxxx
sbt bloopInstall
sbt publish

# you’ll need to add an external resolver build.sbt
externalResolvers += "ExampleLibrary packages" at "https://maven.pkg.github.com/safew2008/example-library"
libraryDependencies += "safe2008" %% "example-library" % "0.1.0-SNAPSHOT"

# final.scala
import org.supermanue.exampleLibrary.ExampleClass
val itWorked = ExampleClass("hello world")

```