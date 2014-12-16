---
layout: post
title: "在 OS X 下使用 Automator 批量修改图片大小"
date: 2013-04-18 00:30
comments: true
categories: 
- OS X Tips
---
看到朋友的这篇 [OSX下在Finder里批量修改图片大小](http://www.leonzhang.com/2013/04/01/osx-finder-batch-resize-images/) ，作为一个业余玩相机的也曾为此而困扰。在此抛砖引玉介绍一个更方便的，使用 OS X 系统自带程序 ["Automator"](https://en.wikipedia.org/wiki/Automator_\(software\)) 解决的方法：

1. 打开`Automator`
2. “Document Type” 中选择 `Service` (意味着功能将会出现在 Finder 的右键菜单)
3. “Service receives selected” 选择 `image files` in `Finder`
4. 从左侧边栏的 “Library” 中选择 `Photos`，并从二级菜单中的将 `Scale Images` 拖到右侧空白区 （出现确认提示点击 “Add”）
5. 右侧区域会出现两个流程 “Copy Finder Items” 和 “Scale Images”，分别表示缩放的尺寸和输出文件夹
6. 最后 `File` - `Save` ，命名服务为 “缩放图片到50%” 或其他任意名称

{% img http://sonicwu.com/statics/images/batch-resize-pic-on-osx-0.png %}

至此之后 Finder 中选择任意数量的图片时，右键菜单均会出现这个操作

{% img http://sonicwu.com/statics/images/batch-resize-pic-on-osx-1.png %}

这只是 `Automator` 很简单的一次示例，它还能做到的更多。