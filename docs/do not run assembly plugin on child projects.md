# do not run assembly plugin on child projects

```xml
<plugin>
    <artifactId>maven-assembly-plugin</artifactId>
    <version>2.6</version>
    <configuration>
        <descriptors>
            <descriptor>package.xml</descriptor>
        </descriptors>
        <appendAssemblyId>false</appendAssemblyId>
        <runOnlyAtExecutionRoot>true</runOnlyAtExecutionRoot>
    </configuration>
    <executions>
        <execution>
            <id>make-assembly</id>
            <phase>package</phase>
                <goals>
                <goal>single</goal>
            </goals>
        </execution>
    </executions>
</plugin
```