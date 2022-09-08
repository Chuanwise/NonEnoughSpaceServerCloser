# 外存不足关服器 - NonEnoughSpaceServerCloser

当 `Minecraft` 服务器外存不足时，将会有插件在后台打印日志「java.io.IOException: 设备上没有空间」，此时服务器的操作（如玩家建筑等）都无法被保存。但玩家无法察觉此异常。

服务器在后台将打印大量的日志，像是一声声的哀嚎和呼救。

约数小时后，服务器才会在极其卡顿中打印大量的日志，最后崩溃。重启服务器后，玩家在这数小时以内的 **全部劳动都会白费**。`CoreProtect` 之类的也因为外存不足无法记录玩家操作，因而谈不上还原了。

椽子说，要在外存不足时立刻关闭服务器，不能让玩家白玩。于是 **外存不足关服器** 诞生了。

插件用户 QQ 群：`1028959718`，欢迎来此交流讨论哦 (๑•̀ㅂ•́)و✧

## 平台要求

Bukkit 1.7 或兼容它的客户端

## 快速开始

只需要从 [RELEASE](https://github.com/Chuanwise/NonEnoughSpaceServerCloser/releases) 处下载最新的插件 `JAR`，将其放在服务器的 `plugins` 文件夹后重启服务器（或使用 `PlugMan` 载入）即可。

默认配置满足大部分需求，一般无需另外配置。

## 指令说明

| 指令 | 权限 | 功能 |
|-----|-----|------|
|`/nessc`|`nessc.reverse`|启动或关闭插件功能|
|`/nessc reload`|`nessc.reload`|重载配置文件|
|`/nessc info`|无|显示插件信息|
|`/nessc test`|`nessc.test`|耗尽外存以测试插件功能（测试结束后生成的大文件会自动删除），**此测试会导致已经被彻底删除的文件无法恢复**|

## 配置信息

插件目前只有一个配置文件 `config.yml`，说明如下：

```yaml
# 配置文件版本，请勿修改
version: '1.0'

# 是否启动插件功能
enable: true

# 外存不足，踢出玩家时向玩家发送的信息
kick-message: §7[§3§lNESSC§7] §b服务器外存不足，请立刻联系管理员以修复此问题！

# 多久检查一次外存空间
check-interval: 20

# 当外存空间不足多少 B 时关闭服务器
min-usable-bytes: 1024
```

## 相关事件

### 外存不足事件 - `cn.chuanwise.nessc.event.InsufficientSpaceEvent`

当插件发现设备空间不足的日志时，将会发出该事件。若其被取消，则服务器本次不会被关闭。

## 许可证

本插件基于 `MIT` 许可证开源，请遵从此开源协议使用本插件及相关代码。

```
MIT License

Copyright (c) 2022 CHUANWISE

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 画大饼

正在考虑搞一些关服前提醒腐竹的功能，如果用的人少就不搞了



