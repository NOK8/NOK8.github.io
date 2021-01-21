---
title: Python self 引发takes exactly 1 argument (2 given)问题
tags: python,class,传参
category: 小书匠/帮助手册
slug: storywriter/upgrade_log
grammar_mindmap: true
renderNumberedHeading: true
grammar_code: true
grammar_decorate: true
grammar_mathjax: true
---

#!/usr/bin/python

``` python
# -*- coding: UTF-8 -*-

class Root(object):
    def __init__(aa, v):      #相当于def __init__(self, v):self.value， 只不过是名字不同。参数代表对象本身， 与名字无关。  
    aa.value = v                  #                  

    def get_self_id(self):
        print("sl:{}".format(id(self)))
    #设置静态method，添加标识
    @staticmethod                    
    def f():
        print('@staticmethod')

    def kl():                        
        print "pass"

def f():
    print "ssss"

if __name__ == "__main__":
    r = Root("007")
    print(id(r))
    print("r id:{}".format(id(r)))
    r.get_self_id()   #相当于调用r.get_self_id(r)， python自动添加               
	
    r.f()     #调用合法，因为是静态函数调用
    #r.kl()   #调用不合法
    f()       #相当于外包，对加工对象没有限制；而r.f()相当于给自己公司工作，对加工对象有限制。
```
    

