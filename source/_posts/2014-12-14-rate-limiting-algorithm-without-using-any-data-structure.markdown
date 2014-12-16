---
layout: post
title: "不使用任何数据结构的速率限制算法"
date: 2014-12-14 21:19:56 +0800
comments: true
categories: 
- Algorithm
---
没有使用任何数据结构和定时器，最简洁的速率限制算法：[Token Bucket（令牌桶）](http://en.wikipedia.org/wiki/Token_bucket)

{% codeblock lang:python RateLimiter.py %}
import time

class RateLimiter:

    def __init__(self, max_rate=20.0, per_seconds=10.0):
        self.allowance = max_rate
        self.max_rate = max_rate
        self.per_seconds = per_seconds
        self.last_checked = int(time.time())

    def acquire(self):
        current = int(time.time())
        elapsed = current - self.last_checked        
        self.last_checked = current

        self.allowance += elapsed * (self.max_rate / self.per_seconds)
        
        # throttle
        if self.allowance > self.max_rate:
            self.allowance = self.max_rate

        if self.allowance < 1.0:
            return False

        self.allowance -= 1.0
        return True
{% endcodeblock %}

初始给予`max_rate`个令牌，每次请求消耗 1 个，每秒钟恢复`max_rate / per_seconds`个，最多恢复到`max_rate`个令牌。

效果：每`per_seconds`秒最多允许`max_rate`次请求。
