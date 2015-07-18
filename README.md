# invesdwin-checkstyle-plugin

This plugin contains additional checks for checkstyle. It is packaged as an eclipse plugin, so it can be used with `http://eclipse-cs.sourceforge.net` by just putting the invesdin-checkstyle-plugin jar inside `eclipse/dropins/`.

## Maven

Releases and snapshots are deployed to this maven repository:
```
http://invesdwin.de:8081/artifactory/invesdwin-oss
```

Dependency declaration:
```xml
<dependency>
	<groupId>de.invesdwin</groupId>
	<artifactId>invesdwin-checkstyle-plugin</artifactId>
	<version>1.0.0-SNAPSHOT</version>
</dependency>
```


## Checks

Currently this plugin contains the following checks:

* `de.invesdwin.checkstyle.InternalImportCheck`: with this you can enforce the rule that `internal` packages are not used outside of your module. You can also change the name of the package by using the `internalPackageName` property.
```xml
<module name="de.invesdwin.checkstyle.InternalImportCheck">
	<property name="internalPackageName" value="internal" />
</module>
```
* `de.invesdwin.checkstyle.NotNullParameterAnnotationCheck`: Findbugs can parse @Nonnull, but not @NotNull in parameters correctly, this check verifies that the developer does not use the wrong annotation.
```xml
<module name="de.invesdwin.checkstyle.NotNullParameterAnnotationCheck" />
```
