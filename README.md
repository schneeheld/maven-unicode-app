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

## Jenkins JNLP agent configuration

### Operating system

Make sure the `%MAVEN_HOME%\bin` is added to the `PATH` system variable

Make sure the `JAVA_HOME` is set, e.g. `JAVA_HOME=C:\Java\jdk1.8.0_191` 

### Jenkins agent configure

Add Advanced JVM options `-Dfile.encoding=UTF8`
This will make the command line looks similar to

```
java -Dfile.encoding=UTF8 -jar agent.jar -jnlpUrl http://blackbird:8080/computer/managed-node-win-cmd-01/slave-agent.jnlp \
-secret 3a30479b6b82e80c33a6ef0b630557ba8776412a52d7f45593508d05eee86f3c -workDir "c:\jenkins1"
```

### Encoding options

- `sun.jnu.encoding` affects the creation of file name (this possibly gets set by LANG on unix before starting java)
- `file.encoding` affects the content of a file

