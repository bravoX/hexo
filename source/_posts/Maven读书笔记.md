title: Maven读书笔记
date: 2015-12-23 10:09:31
tags:
---



以前对Maven的了解只是停留在简单使用阶段，对于深层次的原理不甚了解，无意中看到infoq上的一个系列教程，出于以后项目需要和个人学习发展，对maven系列文章进行了学习。[详见](http://www.infoq.com/cn/author/%E8%AE%B8%E6%99%93%E6%96%8C)

接着通读了《Maven权威指南》对maven进行了进一步全面的学习。但是这还远远不够，需要在以后的项目中不断思考，优化maven配置，在实战中将maven的优势发挥到极致。

本文主要记录自己学习中的点滴。
## 坐标规划
坐标主要用来定位当前当前工程，涉及到的属性包括

 - groupId
 - artifactId
 - version
 - classifier
 
## 继承
模块机制，子模块可以继承父模块的属性，从而对pom进行重构。涉及属性
 - modles
 - parent
每个pom都有一个超级pom，有默认的属性。

## Profile
profile可以提供多环境的编译部署

## 生命周期

 -  process-resources
 - 	compile
 - process-classes
 - process-test-resources
 - test-compile
 - test
 - prepare-package
 - package

生命周期加上插件的使用，可以按需定制工作流程。

## maven plugin
maven所有的功能实现都是通过plugin来实现的。可以根据自己的需求进行编写plugin。经常用到的plugin罗列如下：

 - maven-archetype-plugin
 - maven-assembly-plugin
 - maven-antrun-plugin
 - maven-dependency-plugin
 - maven-help-plugin
 - maven-resources-plugin
 - maven-surefire-plugin
 - jetty-maven-plugin

详细的plugin参考可以查看具体用法，这里不做过多说明。

## 属性引用
属性引用主要是便于系统的灵活配置和升级，例如数据库连接配置、版本信息等。有四大类别。

 - env
 - project
 - settings
 - Java系统属性

## 包依赖
maven最大的优势就是依赖包的管理，可以灵活自主配置，查看方便，冲突检测比较强大。

 - 版本界限：(,) [,]
 - 排除传递性依赖
 - scope限制：compile/runtime/provided/test/system


