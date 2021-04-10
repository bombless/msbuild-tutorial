## Lesson 1

# Hello World

First thing first, let's make a traditional hello-world project for MSBuild.

Create file `hello-world.xml` with content below:
```xml
<Project><Target Name="HelloWorld"><Message Text="Hello World" /></Target></Project>
```

Now build this project with MSBuild:
```sh
msbuild build.xml
```

Then we should see its output:
```sh
HelloWorld:
  Hello World
```
