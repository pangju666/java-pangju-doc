---
layout: doc
---

<script setup>
const springBootVersion = import.meta.env.VITE_V2_SPRING_BOOT_VERSION;
const dependenciesVersion = import.meta.env.VITE_V2_DEPENDENCIES_VERSION;
</script>

## 简介
统一管理 Java 项目依赖版本的 BOM，涵盖数据库、安全、文档、图像处理、计算机视觉等多场景常用库，解决版本冲突，简化配置。

### Spring Boot 版本
spring-boot-dependencies {{ springBootVersion }}

## 如何使用

Spring Boot 项目建议使用 import 引入，然后设置 parent

### parent引入
```xml-vue
<parent>
    <groupId>io.github.pangju666</groupId>
    <artifactId>pangju-dependencies</artifactId>
    <version>{{ dependenciesVersion }}</version>
    <relativePath/>
</parent>
```

### import引入
```xml-vue
<!-- Spring Boot 项目需要引入 spring-boot-starter-parent -->
<parent>
    <groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-parent</artifactId>
	<version>{{ springBootVersion }}</version>
	<relativePath/>
</parent>

<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>io.github.pangju666</groupId>
            <artifactId>pangju-dependencies</artifactId>
            <version>{{ dependenciesVersion }}</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```
