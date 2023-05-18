# C4模型

- [C4模型](#c4模型)
  - [1 简介](#1-简介)
    - [1.1 C4模型是什么？](#11-c4模型是什么)
    - [1.1.1 C4模型的4个层次简介](#111-c4模型的4个层次简介)
    - [1.2 C4模型的优点](#12-c4模型的优点)
  - [2 基本概念](#2-基本概念)
    - [2.1 抽象(Abstractions)](#21-抽象abstractions)
      - [2.1.1 人(Person)](#211-人person)
      - [2.1.2 软件系统(Sofeware System)](#212-软件系统sofeware-system)
      - [2.1.3 容器(Container)](#213-容器container)
      - [2.1.4 组件(Component)](#214-组件component)
  - [3 视图](#3-视图)
    - [3.1 系统上下文图(System Context diagram)](#31-系统上下文图system-context-diagram)
    - [3.2 容器图(Container diagram)](#32-容器图container-diagram)
    - [3.3 组件图(Component diagram)](#33-组件图component-diagram)
    - [3.4 代码图(Code diagram)](#34-代码图code-diagram)
    - [3.5 系统景观图(System Landscape diagram)](#35-系统景观图system-landscape-diagram)
    - [3.6 动态图(Dynamic diagram)](#36-动态图dynamic-diagram)
    - [3.7 部署图(Delpoyment diagram)](#37-部署图delpoyment-diagram)
  - [4 符号](#4-符号)
  - [参考资料](#参考资料)


## 1 简介
### 1.1 C4模型是什么？
C4模型是一种绘制软件架构图的“抽象优先”方法，它基于反映软件架构师和开发人员如何思考和构建软件的抽象。C4模型的创建是为了帮助软件开发团队在前期设计会议期间和回顾性记录现有代码库时描述和交流软件架构。

C4模型是：
1. 一组分层抽象(软件系统、容器、组件和代码)
2. 一组层次图(系统上下文、容器、组件和代码)
3. 符号独立

C4模型是一种在不同的细节层次上创建代码地图的方法，就像我们使用Google地图之类的东西来放大和缩小感兴趣的区域一样。

不同层次的缩放可以用来向不同的观众讲述不同的故事。

<div align=center><img src="./c4-model/c4-overview.png"></div>

### 1.1.1 C4模型的4个层次简介
<div class="row">
    <div class="col-sm-3 centered">
        <p>
            <img src="./c4-model/map-4.jpg" alt="Google Maps" class="img-thumbnail" /><br>
            <img src="./c4-model/SystemContext.png"  />
        </p>
        <p class="smaller">
            层次 1: <b>系统上下文</b> 图提供了一个起点，显示范围内的软件系统如何适应周围的世界
        </p>
    </div>
    <div class="col-sm-3 centered">
        <p>
            <img src="./c4-model/map-3.jpg" alt="Google Maps" class="img-thumbnail" /><br>
            <img src="./c4-model/Containers.png"  />
        </p>
        <p class="smaller">
            层次 2: <b>容器</b> 图放大了软件系统的范围，显示了高级技术构建块
        </p>
    </div>
    <div class="col-sm-3 centered">
        <p>
            <img src="./c4-model/map-2.jpg" alt="Google Maps" class="img-thumbnail" /><br>
            <img src="./c4-model/Components.png"  />
        </p>
        <p class="smaller">
            层次 3: <b>组件</b> 图放到单个容器，显示其中的组件
        </p>
    </div>
    <div class="col-sm-3 centered">
        <p>
            <img src="./c4-model/map-1.jpg"/><br>
            <img src="./c4-model/class-diagram.png"/>
        </p>
        <p class="smaller">
            层次 4: <b>代码</b>(例如UML类) 图可用于放大单个组件，显示该组件是如何实现的
        </p>
    </div>
</div>

### 1.2 C4模型的优点
C4 模型是一种易于学习、对开发人员友好的软件架构图绘制方法。良好的软件架构图有助于软件开发/产品团队内部/外部的沟通、新员工的高效入职、架构审查/评估、风险识别(例如风险风暴)、威胁建模等。

## 2 基本概念
### 2.1 抽象(Abstractions)
#### 2.1.1 人(Person)
#### 2.1.2 软件系统(Sofeware System)
#### 2.1.3 容器(Container)
#### 2.1.4 组件(Component)

## 3 视图
### 3.1 系统上下文图(System Context diagram)
### 3.2 容器图(Container diagram)
### 3.3 组件图(Component diagram)
### 3.4 代码图(Code diagram)
### 3.5 系统景观图(System Landscape diagram)
### 3.6 动态图(Dynamic diagram)
### 3.7 部署图(Delpoyment diagram)

## 4 符号

## 参考资料
1. [《The C4 model for visualising software architecture》](https://c4model.com/)