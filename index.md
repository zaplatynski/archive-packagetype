---
title: Maven Archive Package Type
---

# Welcome!

Sometimes there are Maven projects which are part of Maven multi projects and have only the task 
to zip some files together. To make things not more complicated than they have to be I created 
this Maven package type which supports this scenario. You don't need to misuse the jar package 
type, even rename the jar to zip (and break other Maven related conventions) or reconfigure 
install and deploy. Just use the Maven assembly plugin and do this: 

```xml
<project>
    ...
    <packaging>archive</packaging>
    ...
    <build>
        ...
        <plugins>
            
            <plugin>
                <groupId>com.github.zaplatynski</groupId>
                <artifactId>archive-packagetype</artifactId>
                <version>1.0.0</version>
                <extensions>true</extensions>
            </plugin>
         
             <plugin>
                <artifactId>maven-assembly-plugin</artifactId>
                <version>2.6</version>
                <configuration>
                    ...
                </configuration>
            </plugin>
            ... 
        </plugins>
        ...
      </build>
      ...
</project>
```

## More information

How to use this Maven package type is documented in the GitHub respository' ReadMe
at [github.com/zaplatynski/archive-packagetype](https://github.com/zaplatynski/archive-packagetype). 

##  Disclaimer

Maven is a trademark of the [Apache Software Foundation](https://www.apache.org).