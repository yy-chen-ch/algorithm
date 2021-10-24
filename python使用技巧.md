#### 内置函数

查看数据类型  type(100, "we", [], {})



#### 类（Class）

```python
class Student:
    place = 'sc' #类属性
    #实体属性
    def __init__(self,name, age): 
        self.name = name;
        
    def eat(self):  #实例方法
        print("实例方法")
    @classmethod  
    def cm(class):  #类方法  classmethod修饰
        print("类方法  classmethod修饰")
    @staticmethod
    def cms:
    	print("静态方法 ")
stu1 = Student("zhangs", 50)
```

