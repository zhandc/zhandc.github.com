---
layout: post
title: "开天辟地第一篇（除了Hello World之外）"
description: ""
category: 胡扯
tags: [技术博客]
---
{% include JB/setup %}

n年前开始写blog，用过很多服务商提供的产品，比如livespace，sina，wordpress，QQ space等等，大部分很快就荒废了。倒不是我笔懒，实在是有太多的外界因素。比如2007年底那一会儿，在外边网速快，上livespace觉得十分方便于是发了不少，结果08年回来不多久livespace居然就撑不下去了，于是转成wordpress。用的时候真心觉得wordpress是一个好博客系统。但是后来大家知道的，wordpress和blogspot之类的都被墙了。于是转战了好几个国内的wordpress服务商，比如yo2，72颗松。但是都不长久：比如yo2后来被博客中国收购，并且开始收钱。因为在国内，所以即时通讯软件用的还是QQ多，后来QQ space能做得比较方便了，不那么花里胡哨了，于是用了一段时间的QQ space，但是还是觉得不如wordpress方便。

重申一下本人并不懒笔头，不但不懒还在自己的机器上装了一套Apache+MySQL架了wordpress系统，自娱自乐地写了n多篇。这样固然方便，但是有几点：

- 写出来的BLOG别人看不到；
- 我喜欢在离线编辑器中写blog，各种离线编辑器几乎都支持wordpress，这也是我选择wordpress的原因之一。然而本机架设的wordpress用离线编辑器总有一种脱了裤子放p的感觉；
- 我喜欢折腾，有软件升级强迫症，App store右上方的数字始终是我心中一定要抹去的阴影。对于wordpress我也不例外，那么Apache升级了我要升级，MySQL升级了我要更新，wordpress升级了，你懂得我也要升级要导出导入数据，这种感觉也很独特，真是麻烦；

所以带着这种奇异的感觉过了n多天以后，我觉得我需要改变一下了。在经历了这么多次选择相对靠谱的blog服务商随后又（被）抛弃的经历之后，我觉得应该磨刀不误砍柴工，好好分析一下什么地方架设blog最为理想了：自己购买的托管服务器，然后再买一个域名，再架设wordpress服务。这样做固然好，但是要花钱的。

在我在MAC OSX上使用homebrew之前，我一直觉得要钱还是要舒服的写BLOG这个问题估计是无解了。后来通过使用homebrew知道了有github这么个东西，而且可以架设blog，神奇的是还是静态网页的blog，更加神奇的是可以通过markdown来离线编辑。

一时间觉得自己很幸福，用markdown来写blog一定是一件很愉快的事情。于是就有了这一篇试水文。