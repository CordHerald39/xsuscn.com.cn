---
title: "启用 TUN 后仍失败：接管方式与节点协议要分开查"
category: "tutorials"
label: "实用教学"
description: "启用 TUN 后仍失败：接管方式与节点协议要分开查，按步骤核对条件、错误与恢复方法。"
date: "2026-10-04"
updated: "2026-10-04"
author: "XSUS中文资料编辑"
draft: false
---

## TUN 不会改变节点的协议
TUN 是客户端接入流量的一种方式，节点协议与传输选项则决定代理出站。打开 TUN 不能把不受当前内核支持的配置变成兼容配置，也不能替代个人账户或服务端检查。
## 分两次验证
先在客户端支持的普通代理模式下，用一个明确采用该代理的应用完成请求。再开启 TUN，检查虚拟网卡、路由和权限日志；保留相同节点与目标。若前一阶段就失败，应先处理配置和出站问题。
## 只有 TUN 失败时
查看当前内核文档中 auto-route、出口网卡和平台限制。多网卡、其他 VPN 或受管理网络可能影响路由；先停用本人控制的其他网络工具作单变量对照，不删除系统网卡或重置整个网络。无法判断时恢复原模式。
## 记录兼容性边界
写清系统、内核版本、工作模式和错误环节。浏览器请求成功不能证明所有应用都已被 TUN 接管，UDP 应用也要按自身任务另行验证。
## 原始资料
[Mihomo TUN 文档](https://wiki.metacubex.one/config/inbound/tun/)；[全局配置](https://wiki.metacubex.one/config/general/)。参阅[内核版本核对](/tutorials/core-version-compatibility/)。
