---
title: Maven Archive Package Type
---

# Welcome!

Sometimes there are Maven projects which are part of Maven multi projects and have only the task 
to zip some files together. To make things not more complicated than they have to be I created 
this Maven package type which supports this scenario. You don't need to misuse the jar package 
type, even rename the jar to zip (and break other Maven related conventions) or reconfigure 
install and deploy. Just use the Maven assembly plugin and do this: 

## More information

```xml
<project>
    ...
    <packaging>archive</packaging>
    ...
</project>
```

How to use this Maven package type is documented in the GitHub respository' ReadMe
at [github.com/zaplatynski/archive-packagetype](https://github.com/zaplatynski/archive-packagetype). 

##  Disclaimer

Maven is a trademark of the [Apache Software Foundation](https://www.apache.org).