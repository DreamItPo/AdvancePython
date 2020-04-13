## type的两种用法
- 生成一个类
- 返回一个对象的类型
## type->int->1
- type->class->obj
```
# 1是通过int这个类实例化的对象, int是通过type这个类实例化的对象
>>> a = 1
>>> type(1)
<class 'int'>

>>> type(int)
<class 'type'> 

>>> b="abc"
>>> type(b)
<class 'str'>
# 自己定义一个类Student;类内容为pass
>>> class Student:
...     pass
...
>>> class MyStudent(Student):
...     pass
...
>>> stu = Student()

>>> type(stu)
<class '__main__.Student'>

>>> type(Student)
<class 'type'>

>>> type(object)
<class 'type'>

>>> type(type)
<class 'type'>

>>> a = 'abc'
>>> type(a)
<class 'str'>
>>> type(str)
<class 'type'> 
>>> type(type)
<class 'type'>

>>> a=[1,2]
>>> type(a)
<class 'list'>
>>> type(list)
<class 'type'>
# 结论 ：我们的类是由type这个类生成的对象。我们平常所熟悉的对象，其实是由type类对象创建的对象。type是用来生成类的；
# object其实是所有类都要继承的最顶层的基础类；
>>> Student.__bases__   # 查看student的基类；
(<class 'object'>,)

>>> class MyStudent(Student):  # MyStudent继承Student;
...     pass
...

>>> MyStudent.__bases__       #求 MyStudent的基类
(<class '__main__.Student'>,)  #显示MyStudent的基类是Student
#type是一个类，同时，type也是一个对象。
>>> type.__bases__
(<class 'object'>,)    #type的父类是object

#python中一切都是对象，那么object这个基类也是对象。这个object是由什么类生成的呢？
>>> type(object)  
<class 'type'>   


>>> object.__bases__  #object的父类是空
()
```

## type、object和class的关系
![](http://qiniu.rearib.top/FuGb8QAEGTpbO7AyZtE8VreIHcGF)



#type是最重要的，它创建了所有对象，如object、函数、list；     list不仅是类，还是type类的对象。
object是最顶层的类；连type的父类也是object;
  #太狠了，连自己都不放过。type能自己实例化自己。type如果当做对象来看，那么属于type类的一个对象；
>>> type(type)
<class 'type'>
