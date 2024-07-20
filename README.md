# 莉丽冒险世界

## 简介

项目概况：

- ﻿通过有限状态机实现了人物的动作切换，采用Input System操作玩家。怪物也采用状态机，设计简单的WayPoint类规划巡逻点。
- ﻿数据存储为二进制，Json，PlayerPrefs三种形式，Serializable游戏数据对象GameData，便于存取。
- ﻿﻿人物动画为Setlnteger等触发方式，效果融合平滑。实现loading，存档，暂定等UI界面并搭Animation突出效果，用一些协程做效果延迟处理，熟悉特效制作方式。
- ﻿使用物理系统计算出人物向量速度，设计多种机关障碍物，泳池沼泽，检查点，传送点，导轨台，跳跃台，旗杆等关卡元素，使用碰撞器触发器和一些3D数学计算。
- ﻿﻿使用常见单例和观察者设计模式，注重逻辑解耦。

## 设计文档

核心代码是entity和playstate部分

设计重点就是维护一个有限状态机，PlayerState包含N多状态，玩家一个时刻只能是处于一个状态，方便管理。而除了状态，切换状态也同样重要，例如`player.states.Change<IdlePlayerState>();`

经常使用这个Change。

其余的PlayerStateManager等都是围绕这个状态机来实现的，方便管理用。

**这个游戏的核心就是通过合理的架构维护状态机，然后修正玩家的状态，其中最主要的就是垂直和水平两个速度，各种手感都是维护这两个变量而呈现出来的。**

## 链接

![莉丽冒险世界](DEMO\screenshot.png)

详细文档左转博客：https://gongqihua.github.io/

演示Demo在Demo文件夹下：[传送门](DEMO\Odyssey.mp4)。
