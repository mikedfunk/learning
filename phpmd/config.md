## Configuring phpmd

* [docs](https://phpmd.org/documentation/creating-a-ruleset.html) for creating a custom ruleset
* [ruleset documentation](https://phpmd.org/rules/index.html)
* configuration is very similar to [phpcs](../phpcs.md).

e.g. save this in `phpmd.xml`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="My Ruleset"
    xmlns="http://pmd.sf.net/ruleset/1.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://pmd.sf.net/ruleset/1.0.0 http://pmd.sf.net/ruleset_xml_schema.xsd"
    xsi:noNamespaceSchemaLocation="http://pmd.sf.net/ruleset_xml_schema.xsd">
    <description>My Description</description>
    <rule ref="rulesets/codesize.xml">
        <exclude name="ExcessiveClassLength" />
    </rule>
    <rule ref="rulesets/controversial.xml">
        <exclude name="CamelCasePropertyName" />
        <exclude-pattern>legacy-code/*</exclude-pattern>
    </rule>
</ruleset>
```

Then run it manually to test via: 
```sh
phpmd /path/to/MyPhpFile.php text ./phpmd.xml
```
where `text` is the reporter.

Unfortunately phpmd doesn't have a mode to show you the exact rule and ruleset each violation is violating like phpcs does. However you can look them up in [the rule docs](https://phpmd.org/rules/index.html). In some cases that still doesn't have the exact error string. In that case, check out the actual ruleset xml e.g. [codesize xml](https://github.com/phpmd/phpmd/blob/master/src/main/resources/rulesets/codesize.xml) which has the actual error string template. This helped me to find "overall complexity" error where those words were never mentioned in the docs :angry:.
