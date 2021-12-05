### matplotlib

matplotlib  开发2D 3D 图表

```python
import matplotlib.pyplot as plt
plt.figure(figsize=(), dpi=) #创建画布
plt.plot(x, y，color="r", linestyle="--", label="北京")
#折线图plot 删点图scatter 柱状图bar 直方图hist 饼pie
plt.show()    #显示图像
plt.xticks()  #自定义X,y刻度
plt.xlabel("时间") #X轴
plt.savefig("test.png")  #保存图片 
#plt.show()会释放figure资源，如果在显示图像之后保存图片将只能保存空图片
plt.grid(True, linestyle="--", alpha=0.5)  #添加网格显示
plt.title("中午11点--12点某城市温度变化图", fontsize=20)  #标题
```



### Numpy    

NumPy     支持常见的数组和矩阵操作，提供了一个N维数组类型ndarray，它描述了相同类型的“items”的集合。计算时间快

属性

| 属性          | 属性解释       |                                   |         |
| ------------- | -------------- | --------------------------------- | ------- |
| ndarray.shape | 数组维度的元组 | np.array([[1,2,3],[4,5,6]]).shape | (2,2,3) |
| ndim          | 维数           |                                   |         |
| size          | 元素数量       |                                   |         |
| itemsize      | 一个元素的长度 |                                   |         |
| dtype         | 元素的类型     |                                   |         |

复制

```Python
a1 = np.array(a)   a2 = np.asarray(a) # 复制  索引
numpy.array(object, dtype = None, copy = True, order = None, subok = False, ndmin = 0)
```

生成0,1 的数组

```python
ones = np.ones([4,8], dtype)   ones2 = np.ones_like(ones, dtype)  zeros = np.zeros([4,8], dtype)
```

生成固定范围数组

```python
np.linspace(0, 100, 11)    # start, stop, num, endpoint(是否包含stop， 默认为ture)
np.arange(10, 50, 2)     # 等差数组 start, stop, step, dtype  
np.logspace(0, 2, 3)     # 等比数列 start, stop, num(个数，默认为50个
np.random.randn(d0, d1, …, dn)                   #从标准正态分布中返回一个或多个样本值
np.random.normal(loc=0.0, scale=1.0, size=None)  #均值 方差 数量
np.random.rand(d0, d1, …, dn)                    #从[0,1) 分布中返回一个或多个样本值
np.random.uniform(low=0.0, high=1.0, size=none)  #从均匀分布【low，high）中随机采样
np.random.randint(low=0.0, high=1.0, size=none, dtype="l")  #从均匀分布【low，high）中随机采样的整数
```

数组操作

```python
a[,, 0:3]  #切片
a.reshape([-1, 10])    # -1: 表示通过待计算   20/10 = 2 假设共a含有20个
a.T.shape              # 装置
a.astype(np.int32)     # 类型修改
a.unique(temp)         # 数组去重
```

数组运算

```python
a > 10                 # 大于10的元素为TRUE，否则为false
a[a>10] = 1            # 大于10的元素为1
np.all([0:2, :] > 60)  # 判断前2名是否都及格
np.any([0:2, :] > 60)  # 判断前2名是否有及格的
np.where(a > 50, 1, 0) # 三元运算符
data.query("open<24 & open>23").head()
np.where(np.logical_and(a > 60, a < 80), 1, 0)   # 符合逻辑
np.where(np.logical_or(a > 60, a < 80), 1, 0)
data.applu(func, axis=0)  # 自定义计算
# 统计运算  min(a, axis)， max(a, axis])， median(a, axis)， mean(a, axis, dtype)， std(a, axis, dtype)， mode(a, axis, dtype)
# 最小值，最大值，中位数，平均值，标准差，众数 
# 矩阵，英文matrix，和array的区别矩阵必须是2维的，但是array可以是多维的
# 向量是一种特殊的矩阵，讲义中的向量一般都是列向量，
np.matmul(a, b)  np.dot(a,b)   
# 矩阵乘法 二者都是矩阵乘法。 np.matmul中禁止矩阵与标量的乘法。 在矢量乘矢量的內积运算中，np.matmul与np.dot没有区别。
```



### Pandas     增强图表可读性   便捷的数据处理能力  读取文件方便  

Pandas中一共有三种数据结构，分别为：Series、DataFrame和MultiIndex（老版本中叫Panel ）。 对应 一维， 二维， 三维

```python
import pandas as pd
pd.Series([6.7,5.6,3,10,2], index=[1,2,3,4,5])  pd.Series(data=None, index=None, dtype=None)
pd.Series({'red':100, 'blue':200, 'green': 500, 'yellow':1000})
# series 属性  index, values
pd.DataFrame(np.random.randn(2,3))          pd.DataFrame(data=None, index=None, columns=None)
# DataFrame 属性  shape, index, columns, values
#显示 前5行 data.head(5)  后5行 data.tail(5)
data.reset_index(drop=True)    # 重置索引,drop:默认为False，不删除原来索引，如果为True,删除原来的索引值
```

 **注：Pandas从版本0.20.0开始弃用：推荐的用于表示3D数据的方法是通过DataFrame上的MultiIndex方法 ** 



### 文件读取与储存

```python
pandas.read_csv(filepath_or_buffer, sep =',', usecols)   # usecols:指定读取的列名，列表形式
DataFrame.to_csv(path_or_buf=None, sep=',', columns=None, header=True, index=True, mode='w', encoding=None)   # mode w 重写 a 追加
```

#### 缺失处理

```python
pd.isnull(df), pd.notnull(df)  # 断是否含nan
df.dropna(axis='rows')            # 删除存在缺失的值，不会修改原数据，需要接受返回值
df.fillna(value, inplace=True)    #
df.replace(to_replace=, value=)   # 数据替换
```



| str           | fuhao          | shizi                             |         |
| ------------- | -------------- | --------------------------------- | ------- |
| ndarray.shape | 数组维度的元组 | np.array([[1,2,3],[4,5,6]]).shape | (2,2,3) |
| ndim          | 维数           |                                   |         |
| size          | 元素数量       |                                   |         |





