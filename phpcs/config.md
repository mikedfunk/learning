## Configuring phpcs

* [docs](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-ruleset.xml) for creating a custom ruleset
* [ruleset/sniffs documentation](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Customisable-Sniff-Properties)
* configuration is very similar to [phpmd](../phpmd.md).

e.g. save this in `phpmd.xml`:
```xml
<?xml version="1.0"?>
<ruleset name="My Coding Standard">
  <description>My Desc</description>
  
  <arg name="colors" />

  <exclude-pattern>*/vendor/*</exclude-pattern>

  <rule ref="PSR2">
    <exclude name="PSR2.ControlStructures.ControlStructureSpacing"/>
    <exclude name="PSR2.Methods.MethodDeclaration" />
    <exclude name="PSR2.Classes.PropertyDeclaration">
        <exclude-pattern>legacy-code/*</exclude-pattern>
    </exclude>
  </rule>
</ruleset>
```

Then run it manually to test via: 
```sh
phpcs /path/to/MyPhpFile.php
```
where `text` is the reporter.
