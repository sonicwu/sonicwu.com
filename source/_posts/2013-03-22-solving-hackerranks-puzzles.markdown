---
layout: post
title: "HackerRank 的编程挑战"
date: 2013-03-25 14:54
comments: true
categories: 
- Programming Puzzle
---
最近算是闲下来了，一口气把 Trello 中的 TODO 完成了大半，其中就包括来自 [HackerRank](http://hackerrank.com) 的编程挑战。

HackerRank 提供了不同难度的编程谜题以供挑战，目前已支持到21种编程语言。题目类型涉及 AI、Algorithmic、Code Golf，Weekly Contest 四大类。并且入门级题目并不难，曾经的 Level-1 题目 [“Tic-Tac-Toe”](https://www.hackerrank.com/challenges/tic-tac-toe) 已被提升至 AI 类别的 Track-5，而现在的 Track-1 会从简单的 [插入排序](https://www.hackerrank.com/challenges/insertionsort1) 开始。

一口气完成了 AI 分类的 Bot 系列谜题 [GitHub Repo](https://github.com/sonicwu/hacker-rank) ，在这里聊聊过程中碰到的几个问题：

### 如何保存状态？

由于机器人每一步都是重新执行代码读取输入，所以很多情况下都需要记录状态。目前可以通过读写文件来实现 [“FAQ: Can my code write to a file?”](https://www.hackerrank.com/faq/can-i-write-to-file)

### 是否需要选择最“好”的算法？

以 ["BotClean"](https://www.hackerrank.com/challenges/botclean) 系列题目为例，这是一个 [“TSP”（旅行商、货担郎问题）](http://en.wikipedia.org/wiki/Travelling_salesman_problem) ，普遍解法有 [遗传算法](https://zh.wikipedia.org/wiki/%E9%81%97%E4%BC%A0%E7%AE%97%E6%B3%95)、[模拟退火](https://zh.wikipedia.org/wiki/%E6%A8%A1%E6%8B%9F%E9%80%80%E7%81%AB)，[贪心算法](https://zh.wikipedia.org/wiki/%E8%B2%AA%E5%BF%83%E6%B3%95) 等多种。其中“贪心算法”是实现起来最简单但却并不是最优解，但由于结果验证的地图都很小，所以已经足以拿到最高分。