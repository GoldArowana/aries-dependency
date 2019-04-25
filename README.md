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

## 每次运行都会下载maven-metadata.xml，导致运行很慢怎么办？
根据输出内容，看看是哪里的metadata.xml，如果是里面有`arowana`字样，那应该就是我的仓库导致的。

修改```<updatePolicy>always</updatePolicy>```为```<updatePolicy>daily</updatePolicy>```

总体如下：
```xml
<repositories>
    <repository>
        <id>maven-repo-master</id>
        <url>https://raw.github.com/goldarowana/maven-repo/master/</url>
        <snapshots>
            <enabled>true</enabled>
            <updatePolicy>daily</updatePolicy>
        </snapshots>
    </repository>
</repositories>
```
也就是修改了更新策略，就不会每次运行都重新下载