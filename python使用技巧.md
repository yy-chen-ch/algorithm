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

### 数组-列表

翻转数组   arr[::-1]

```python
#字符串与列表相互转换
".".join(list)
list = list(str)  
list = str.split(".")  #以什么分割

list.append(obj)    #末尾添加
list.count(obj)     #统计
list.extend(seq)    #末尾追加另一个序列的多个值
list.index(obj)     #找到某个值的第一个索引位置
list.insert(inswx, obj)
list.pop(obj = list[-1])
list.remove(obj)     #移除第一个匹配
list.reverse()       #翻转
list.sort(fun)       # 返回为none

```

数组-列表

```python
a = { "a": 1 }
for key in a:
for key in a.keys():
for val in a.values():
for key, val in a.items()：
```

队列

```python
import collections  
d = collections.deque([])  #双端队列
d.append('a') # 在最右边添加一个元素，此时 d=deque('a')
d.appendleft('b') # 在最左边添加一个元素，此时 d=deque(['b', 'a'])
d.extend(['c','d']) # 在最右边添加所有元素，此时 d=deque(['b', 'a', 'c', 'd'])
d.extendleft(['e','f']) # 在最左边添加所有元素，此时 d=deque(['f', 'e', 'b', 'a', 'c', 'd'])
d.pop() # 将最右边的元素取出，返回 'd'，此时 d=deque(['f', 'e', 'b', 'a', 'c'])
d.popleft() # 将最左边的元素取出，返回 'f'，此时 d=deque(['e', 'b', 'a', 'c'])
d.rotate(-2) # 向左旋转两个位置（正数则向右旋转），此时 d=deque(['a', 'c', 'e', 'b'])
d.count('a') # 队列中'a'的个数，返回 1
d.remove('c') # 从队列中将'c'删除，此时 d=deque(['a', 'e', 'b'])
d.reverse() # 将队列倒序，此时 d=deque(['b', 'e', 'a'])
f=d.copy()
print(f)#deque(['b', 'e', 'a'])
f.clear()
print(f)#deque([])

```

```python
chr(97)  #a
ord("a") #97
```

