---
layout: post
title:  "Ruby 正则表达式的 o 选项"
date:   2014-01-25 23:45:00
categories: 
  - Ruby
---

如果在正则表达式中指定了 `o` 选项，那么这个此表达式中的任意 `#{...}` 替换仅在第一次求解它的时候执行替换；否则，替换在每次字面量生成 Regexp 对象时执行：

```ruby
3.times {|i| p /#{i}/}
# 输出：
/0/
/1/
/2/
```

```ruby
3.times {|i| p /#{i}/o}
# 输出：
/0/
/0/
/0/
```