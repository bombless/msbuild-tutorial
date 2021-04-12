# Lesson 2

## Compile and build a single .java file

In this lesson we will write a Java source code file with a single `main()` entry.
Then we compile and run it with our MSBuild configuration.

The Java code is simple:
```java
// code for Main.java
class Main {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

and here's our MSBuild configuration:
```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
 <PropertyGroup>
  <TargetDir>./target/</TargetDir>
  <ClassName>Main</ClassName>
 </PropertyGroup>
 <Target Name="Task">
  <MakeDir Directories="$(TargetDir)" />
  <Exec Command="javac -d $(TargetDir) $(ClassName).java" />
  <Exec WorkingDirectory="$(TargetDir)" Command="java $(ClassName)" />
 </Target>
</Project>
```

We defined property `TargetDir` and `ClassName` to keep better flexibility,
then we define our task here, which creates a folder if it doesn't exist yet,
then compile and run the Java program.
