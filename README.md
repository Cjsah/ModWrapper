# A Mod Wrapper for Fabric Mod

- First

```shell
git submodule add https://github.com/Cjsah/ModWrapper.git <FolderName>
```

- In the settings.gradle, add the following line:

```groovy
include(":<FolderName>")
```

To embed additional local projects as nested JARs, optionally set a comma-separated
list of `<project>::<task>` entries in the root project's `gradle.properties`:

```properties
wrapper_include_projects=compat-module::jar,another-module::remapJar
```

Project paths are relative to the root project; a leading `:` is optional. Each
selected task must be an archive task whose JAR contains its own `fabric.mod.json`.
The wrapper builds these JARs, embeds them under `META-INF/jars`, and lists them in its metadata.
Omit the property or leave it empty to include no additional projects.
