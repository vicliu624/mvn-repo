# mvn-repo
juaner-platform-dependency-management

# 1.0.2升级

## pom.xml变更

### 替换

#### 项目pom.xml替换

```
<properties>
   <juaner-platform.version>1.0.2</juaner-platform.version>
</properties>
```

```
    <repositories>
        <repository>
            <id>mvn-repo</id>
            <url>https://raw.github.com/vicliu624/mvn-repo/1.0.2</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
        </repository>
    </repositories>
    <pluginRepositories>
        <pluginRepository>
            <id>mvn-repo</id>
            <url>https://raw.github.com/vicliu624/mvn-repo/1.0.2</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
        </pluginRepository>
    </pluginRepositories>
```

#### 模块pom.xml新增

```
<dependencies>
  <dependency>
    <groupId>indi.vicliu.juaner</groupId>
    <artifactId>admin-client</artifactId>
    <version>1.0.2</version>
  </dependency>
</dependencies>

```


