# Maven Archive Package Type [![Build Status](https://travis-ci.org/zaplatynski/archive-packagetype.svg?branch=master)](https://travis-ci.org/zaplatynski/archive-packagetype)  [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.zaplatynski/archive-packagetype/badge.svg?style=flat)](http://mvnrepository.com/artifact/com.github.zaplatynski/archive-packagetype)

A Maven archive package type to create an archive like zip or tar.gz.
I made this because I didn't want to use the built-in jar packagetype  if I only wanted to have a 
zip created.

## How to use

In your `pom.xml` add this:
```xml
<project>

    <groupId>my-group</groupId>
    <artifactId>my-archive-artifact</artifactId>
    <version>1.2.3</version>
    
    <!-- NEW: make only a archive file -->
    <packaging>archive</packaging>

    ...
    <build>
    
        <plugins>
            
            <!-- make new FSM package type available to Maven -->
            <plugin>
                <groupId>com.github.zaplatynski</groupId>
                <artifactId>archive-packagetype</artifactId>
                <version>1.0.0</version>
                <!-- this is important when extending core Maven functionality: -->
                <extensions>true</extensions>
            </plugin>
            
            <!-- define how the archive file look like -->
             <plugin>
                <artifactId>maven-assembly-plugin</artifactId>
                <version>2.6</version>
                <configuration>
                    <appendAssemblyId>false</appendAssemblyId>
                    <descriptors>
                        <descriptor>src/assembly/archive.xml</descriptor>
                    </descriptors>
                </configuration>
            </plugin>
            
        </plugins>    
        ...
    </build>
</project>
```
Inside the above mentioned `archive.xml` you need to specify the [Maven assembly plugin]
(http://maven.apache.org/plugins/maven-assembly-plugin/) descriptor to create a typical archive 
file layout:
```xml
<assembly xmlns="http://maven.apache.org/ASSEMBLY/2.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/ASSEMBLY/2.0.0 http://maven.apache.org/xsd/assembly-2.0.0.xsd">
    <id>myZip</id>
    <formats>
        <format>zip</format>
    </formats>
    <includeBaseDirectory>false</includeBaseDirectory>
    ...
</assembly>
```
See the [Maven assembly plugin documentation](http://maven.apache.org/plugins/maven-assembly-plugin/assembly.html) for more information.

## Build

```
mvn clean install
```
