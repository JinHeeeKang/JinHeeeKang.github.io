---
title: "리스트 비어 있는지 확인 할때"
excerpt_separator: "<!--more-->"
categories:
  - Python 문법
tags:
  - Python
  - 문법
  
---

# 빈리스트인지 확인 할 때

- 권장하는 방법 
```
if not x:
    print("List x is Empty")
```

- 권장하지 않는 방법
```
if not len(x):
    print("List x is Empty")
```
