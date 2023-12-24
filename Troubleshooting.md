# Maven - Blocked mirror for repositories

Insecure repositories which start with http:// are blockd since Maven 3.8.1.

Solution
1. Change the custom repository to use https://
2. Add mirrors in settings.xml 

```xml
<mirrors>        
    <mirror>
      <id>mirror-id</id> 
      <mirrorOf>repository-id-in-pom.xml</mirrorOf>
      <name>Human Readable Name for this Mirror.</name>
      <url>http://my.repository.com/repo/path</url>
    </mirror>
<mirror>
```
