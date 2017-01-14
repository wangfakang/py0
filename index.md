`python的基础学习`

1.python的函数参数传值还是传址？  
=========

```   
    其实python没有什么可以直接操作传值还是传址，Python参数传递采用的肯定是“传对象引用”的方式。这种方式相当于传值和传引用的一种综合。如果函数收
到的是一个可变对象（比如字典或者列表）的引用，就能修改对象的原始值－－相当于通过“传引用”来传递对象。如果函数收到的是一个不可变对象（比如数字、
、字符或者元组）的引用，就不能直接修改原始对象－－相当于通过“传值'来传递对象。   
```  

2.那些对象是可以修改、那些不可以修改？    
=========    
可变对象：字典、列表、集合    
不可变对象：数字、字符或者元组    


3.命令行和文件执行的一些差异   
=========   

我遇到的问题和这个帖子里面的问题底层原理一样：[here](https://www.zhihu.com/question/53536750)   


4.性能优化及性能测试工具   
=========   

优化先找程序的瓶颈（内存、cpu等各种资源）：   

  1. python -m cProfile -o test.out test.py    
  2.1 python -c "import pstats; p=pstats.Stats('test.out'); p.print_stats()"     
  2.2 python -c "import pstats; p=pstats.Stats('test.out'); p.sort_stats('time').print_stats()"    #根据时间进行排序
       
  然后看到个函数调用比较耗时，就去优化对应的函数。    
     
优化点：  

  1.循环逻辑里面的循环体越简单越好，能放在循环外面的就放在外面。    
  2.多重if条件判断把简单条件以及计算机容易判断的条件放在前面（逻辑短路原理）。    
  3.选择合适的数据结构比如list、set、dict依据场景。      
  4.避免系统调用。    
  5.使用pypy。     


Thx
====

* chunshengsterATgmail.com

[Back to TOC](#table-of-contents)


Author
====
* Linux\nginx\golang\c\c++\lua\python爱好者
* 欢迎一起交流  一起学习# 
* Others say good and Others good

[Back to TOC](#table-of-contents)
