
---
layout: post
title: "MC消息中心消息发送流程"
description: "MC消息中心消息发送流程"
category: Technology
tags: [消息中心, 流程]
---

<br/>

* 某应用调用接口
* 把taskVo对象插入数据库
* 定时任务从数据库捞taskVo对象，然后丢到主队列里
* Dispath对象从主队列里捞taskVo对象分配给各个子队列发送（根据渠道种类的不同丢不同的队列）
* 然后发送