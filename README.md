# maven-unicode-app
Simple maven unicode app for testing Jenkins multibranch pipelines


## Simple maven project: unicode hello

Start a project folder, for example

```
mkdir maven-unicode-app
cd maven-unicode-app
```
Generate a new maven project

```
mvn archetype:generate -DgroupId=com.unicode.hello -DartifactId=unicode-hello \
   -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

cd unicode-hello
mvn compile
java -cp target/classes com.unicode.hello.App
```
