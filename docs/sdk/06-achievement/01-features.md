---
id: features
title: 成就系统功能介绍
sidebar_label: 功能介绍
---

import useBaseUrl from '@docusaurus/useBaseUrl';

## 成就

成就可以增加玩家在游戏中的参与度。你可以在游戏中设置成就，鼓励玩家以不同的玩法来玩游戏。TapTap 为你的游戏增加了「白金成就」，对于那些孜孜不倦完成所有成就的玩家，可以给予象征着「通关高手」的白金成就作为奖励。

## 属性

要了解成就的工作原理，你需要熟悉与成就相关的一些配置项。

### 基础信息

以下这些基础信息项与每一项成就都相关：

**名称** 是成就的简称（例如，「驾车高手」）。该值最多可以包含 80 个字符。

**简介** 关于成就的简要说明，通常用来告诉玩家如何获得成就（例如，「驾驶汽车连续躲避 10 个障碍物」）。该值最多可以包含 400 个字符。

**图标** 是与成就相关的方形图标。有关创建成就图标的最佳做法，请参阅[「图标规则」](#图标规则)部分。

### 配置信息

除了基础信息外，普通成就还有成就 ID、分步成就和初始状态 3 个配置信息。

### **成就 ID**

成就 ID 是向 SDK 上报成就的唯一标识，你可以按照游戏自己的要求来定义成就 ID。该值只允许英文+数字，最多可以包含 32 个字符。

### **分步成就**

成就可以设定为标准或分步的。通常分步成就会让玩家在更长的时间内逐步达成成就。随着玩家逐步取得成就，你可以向 TapTap 游戏服务报告玩家的进度。TapTap 服务会记录进度信息，并在玩家达到解锁该成就的必要条件时提醒游戏，同时告知玩家成就达成。

<img src={useBaseUrl('/img/achievement01.png')} alt="" width="300" />

分步成就在游戏进程中是累积的，并且进度无法从游戏内删除或重置。例如，「赢得 20 场比赛」将被视为分步成就。而「连续赢得 5 局游戏」则不行，因为当玩家输掉游戏时，其进度将被重置。「拥有 2,000 个金币」也不符合条件，因为玩家在玩游戏时可能会获得、也会失去金币。对于后两项成就，你可以把成就设定为「连续获胜」或「金币总数」，并在玩家达成目标时解锁的标准成就。

创建分步成就时，必须定义解锁成就所需的步骤总数（此数字必须介于 2 到 20,000 之间）。步骤总数达到解锁值后，成就即被解锁（即使它已被隐藏）。你无需存储用户的累积进度。

### **初始状态** 

成就初始状态会有以下2种设定：

- **隐藏**成就，意味着对玩家隐藏了成就的细节。TapTap 游戏服务会在成就处于隐藏状态时为其提供特殊的描述和图标。如果成就中包含你不想过早透露游戏内容，我们建议将其隐藏起来（例如，「惊喜，你一定会发现这个宝藏！」）。
- **显示**成就，意味着玩家一开始就可以看到该成就，我们建议大部分成就初始状态都为显示成就。

## 图标规则

上传图标的规则为 512×512px，PNG 或 JPG 文件。你只需要提供成就解锁时的图标即可，我们会自动生成未解锁状态时的灰度版本。因此，我们建议你的成就图标包含彩色元素，以便用户可以轻松的区分成就的已解锁和未解锁状态。

在 SDK 界面显示成就图标时，该图标会覆盖一个圆圈，圆圈外的四个角是被遮罩起来的。请确保你的图标在这种情况下看起来还是不错。

<img src={useBaseUrl('/img/achievement02.png')} alt="" width="300" />

在所有的语言环境中，都将使用同样的成就图标。因此不建议在图标里包含任何文本或本地化的内容。

## 创建成就配置

### 创建成就

要为新游戏创建一个成就，你可以在**开发者中心**、**游戏服务**下找到**生态服务**标签。选择**成就**菜单，然后点击**创建普通成就**。

![img](/img/achievement03.png)

然后你需要填写成就的相关信息。

![img](/img/achievement04.png)

点击保存，这个成就进入到待发布状态。点击提交发布，所有的成就将发布到线上。

### 编辑成就

要编辑已经创建的成就，请在成就列表里点击**编辑**。此时，你将看到与第一次创建成就时一样的配置页面，你可以根据需要进行编辑。

完成成就编辑后，点击**保存**按钮。新编辑的成就将处于**待发布**状态，你可以对其进行测试。如果工作正常，点击**提交发布**，所有成就将发布到线上。

另外，成就发布后，**成就ID**、**分步成就**和**初始状态**这三项配置将无法修改。

### 最少成就

游戏必须拥有 5 项成就才能发布。你可以在少于 5 个成就的情况下进行测试，但游戏发布之前至少要创建 5 个普通成就。

### 删除/重置成就

成就在发布后，**不能**被删除和重置。

你只能通过点击成就列表末尾的按钮，来删除和重置**待发布**的成就。

![img](/img/achievement05.png)

## 白金成就

除了在游戏内触发的普通成就外，我们对于那些孜孜不倦完成所有成就的玩家，还给予象征着「通关高手」的**白金成就**作为奖励。

### 申请白金成就

为了确保白金成就的质量，我们对申请条件做了一定的门槛。你在申请白金成就时，审核人员会根据游戏质量是否高于平均水平来判断审核结果。

白金成就的申请和创建并不影响游戏成就的发布，你可以随时提交已经准备好的普通成就。

![img](/img/achievement06.png)

### 创建白金成就

当游戏获得了白金成就资质后，你可以点击**创建白金成就**按钮，为你的游戏创建白金成就。白金成就需要配置图标、名称和简介。他的触发条件由玩家获得全部普通成就后自动获得。

白金成就不受游戏上线的影响，你可以在游戏上线前创建好白金成就，也可以在游戏上线后来做这件事情。如果有玩家在白金成就发布前，已经获得到全部的普通成就，你再为游戏创建白金成就，玩家依然可以自动获得。

## 添加成就翻译

### 多语言设置

在添加成就翻译之前，你需要为游戏设置多语言。你可以在**开发者中心**、**游戏服务**下找到**生态服务**标签。在**成就**卡片的左侧点击**多语言设置**。

![img](/img/achievement07.png)

然后为你游戏内的成就勾选需要的语言，点击确定生效。你也可以在右侧已选框中删除添加错误的语言。

![img](/img/achievement08.png)

在多语言设置中，你还可以改变**默认语言**。但修改这个配置项要格外小心，修改前确保所有的成就都填上了新的默认语言翻译。

### 添加翻译

完成以上步骤后，你就可以在编辑成就页面里点击语言标签右侧的「+」，选择你刚刚添加的语言。

![img](/img/achievement09.png)

至此，你可以为成就添加**名称**和**简介**的翻译。成就的图标和配置信息将继承默认语言的配置，你不需要重复的添加。

## 游戏内的展示

我们提供游戏内的成就面板展示，玩家根据你指定的入口打开成就界面，查看已经拥有和未被解锁的游戏成就。请参阅[「开发指南」](/sdk/achievement/guide#打开成就展示页)。

<img src={useBaseUrl('/img/achievement10.png')} alt="" width="600" />

<!-- 
## 在 TapTap 展示游戏成就

当玩家在游戏中获得了成就，同时也会在 TapTap 平台上展示。玩家会在**我的游戏**里看到所有成就，也可以访问好友主页上查看好友的成就。

（功能正在开发，敬请期待！）
-->