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

#### 模块application.properties

```
info.groupId= @project.groupId@
info.artifactId= @project.artifactId@
info.version= @project.version@

```

#### 模块application-XXX.properties

```
logging.registry.files[0].name=app_log
logging.registry.files[0].description=application's log 
#logback.xml配置的实际的日志目录
logging.registry.files[0].path=../logs
#logback.xml配置的实际的日志文件名
logging.registry.files[0].filename=(${spring.application.name}).+(.log)$
```

## 如何测试admin-client添加成功

请求服务的actuator

```
http://ip:port/actuator
```

返回

```
{
    "_links": {
        "self": {
            "href": "http://10.253.10.178:6041/actuator",
            "templated": false
        },
        "archaius": {
            "href": "http://10.253.10.178:6041/actuator/archaius",
            "templated": false
        },
        "nacos-config": {
            "href": "http://10.253.10.178:6041/actuator/nacos-config",
            "templated": false
        },
        "nacos-discovery": {
            "href": "http://10.253.10.178:6041/actuator/nacos-discovery",
            "templated": false
        },
        "logfile": {
            "href": "http://10.253.10.178:6041/actuator/logfile",
            "templated": false
        },
        "logfile-arg0": {
            "href": "http://10.253.10.178:6041/actuator/logfile/{arg0}",
            "templated": true
        },
        "metricsInfo": {
            "href": "http://10.253.10.178:6041/actuator/metricsInfo",
            "templated": false
        },
        "beans": {
            "href": "http://10.253.10.178:6041/actuator/beans",
            "templated": false
        },
        "caches": {
            "href": "http://10.253.10.178:6041/actuator/caches",
            "templated": false
        },
        "caches-cache": {
            "href": "http://10.253.10.178:6041/actuator/caches/{cache}",
            "templated": true
        },
        "health": {
            "href": "http://10.253.10.178:6041/actuator/health",
            "templated": false
        },
        "health-path": {
            "href": "http://10.253.10.178:6041/actuator/health/{*path}",
            "templated": true
        },
        "info": {
            "href": "http://10.253.10.178:6041/actuator/info",
            "templated": false
        },
        "conditions": {
            "href": "http://10.253.10.178:6041/actuator/conditions",
            "templated": false
        },
        "configprops": {
            "href": "http://10.253.10.178:6041/actuator/configprops",
            "templated": false
        },
        "env-toMatch": {
            "href": "http://10.253.10.178:6041/actuator/env/{toMatch}",
            "templated": true
        },
        "env": {
            "href": "http://10.253.10.178:6041/actuator/env",
            "templated": false
        },
        "loggers": {
            "href": "http://10.253.10.178:6041/actuator/loggers",
            "templated": false
        },
        "loggers-name": {
            "href": "http://10.253.10.178:6041/actuator/loggers/{name}",
            "templated": true
        },
        "heapdump": {
            "href": "http://10.253.10.178:6041/actuator/heapdump",
            "templated": false
        },
        "threaddump": {
            "href": "http://10.253.10.178:6041/actuator/threaddump",
            "templated": false
        },
        "metrics-requiredMetricName": {
            "href": "http://10.253.10.178:6041/actuator/metrics/{requiredMetricName}",
            "templated": true
        },
        "metrics": {
            "href": "http://10.253.10.178:6041/actuator/metrics",
            "templated": false
        },
        "scheduledtasks": {
            "href": "http://10.253.10.178:6041/actuator/scheduledtasks",
            "templated": false
        },
        "mappings": {
            "href": "http://10.253.10.178:6041/actuator/mappings",
            "templated": false
        },
        "refresh": {
            "href": "http://10.253.10.178:6041/actuator/refresh",
            "templated": false
        },
        "features": {
            "href": "http://10.253.10.178:6041/actuator/features",
            "templated": false
        },
        "service-registry": {
            "href": "http://10.253.10.178:6041/actuator/service-registry",
            "templated": false
        },
        "jardeps": {
            "href": "http://10.253.10.178:6041/actuator/jardeps",
            "templated": false
        },
        "appinfo": {
            "href": "http://10.253.10.178:6041/actuator/appinfo",
            "templated": false
        },
        "gc": {
            "href": "http://10.253.10.178:6041/actuator/gc",
            "templated": false
        }
    }
}
```
返回的actuator列表完整则admin-client添加成功

