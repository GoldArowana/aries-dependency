# aries-dependency

## 使用方式

在父pom中引入：
```xml
    <repositories>
        <repository>
            <id>maven-repo-master</id>
            <url>https://raw.github.com/goldarowana/maven-repo/master/</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
        </repository>
    </repositories>
    
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>com.aries.maven</groupId>
                <artifactId>aries-dependency</artifactId>
                <version>1.0.2-SNAPSHOT</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
```

