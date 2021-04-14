# Lesson 3
## Multiple tasks

In this lesson we will complete very similar task as lesson 2,
with a little bit modification on it.

Here's today's `build.xml`
```xml
 <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
 <PropertyGroup>
  <ClassName>Main</ClassName>
  <TargetDir>$(MSBuildProjectDirectory)/target/</TargetDir>
 </PropertyGroup>
 <Target Name="Task">
  <MakeDir Directories="$(TargetDir)" />
  <Exec Command="javac -d $(TargetDir) $(MSBuildProjectDirectory)/$(ClassName).java" />
  <Exec WorkingDirectory="$(TargetDir)" Command="java $(ClassName)" />
 </Target>
 <Target Name="Clean">
  <RemoveDir Directories="$(TargetDir)" />
 </Target>
</Project>
```

So this time we compile and run a Java program as previous lesson,
but we add a task `Clean` so we can use it to clean the `target`
folder.

Use `msbuild build.xml -t:Clean` to run this cleanup task.
