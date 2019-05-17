## 1. pandas 二维散点图
```
Tag0=pd.read_csv("190409_UWBtest/data/tag0.csv")
print(Tag0.columns.values)
Tag0.rename(columns={Tag0.columns[0]:"t"},inplace=True)
print(Tag0.columns.values)
Tag0.plot.scatter(x='xloc',y='yloc')
print(Tag0.head())
```
![image.png](0)

## 2. matplotlib 三维散点图
 1. 只有一种点的散点图
 ```
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D  # 空间三维画图
 
 
# 数据
data = np.arange(24).reshape((8, 3))
# data的值如下：
# [[ 0  1  2]
#  [ 3  4  5]
#  [ 6  7  8]
#  [ 9 10 11]
#  [12 13 14]
#  [15 16 17]
#  [18 19 20]
#  [21 22 23]]
x = data[:, 0]  # [ 0  3  6  9 12 15 18 21]
y = data[:, 1]  # [ 1  4  7 10 13 16 19 22]
z = data[:, 2]  # [ 2  5  8 11 14 17 20 23]
 
 
# 绘制散点图
fig = plt.figure()
ax = Axes3D(fig)
ax.scatter(x, y, z)
 
 
# 添加坐标轴(顺序是Z, Y, X)
ax.set_zlabel('Z', fontdict={'size': 15, 'color': 'red'})
ax.set_ylabel('Y', fontdict={'size': 15, 'color': 'red'})
ax.set_xlabel('X', fontdict={'size': 15, 'color': 'red'})
plt.show()
```
![image.png](1)
 2. 有多种点及图例的散点图
 ```
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D  # 空间三维画图
 
 
# 数据
 
# 数据１
data1 = np.arange(24).reshape((8, 3))
# data的值如下：
# [[ 0  1  2]
#  [ 3  4  5]
#  [ 6  7  8]
#  [ 9 10 11]
#  [12 13 14]
#  [15 16 17]
#  [18 19 20]
#  [21 22 23]]
x1 = data1[:, 0]  # [ 0  3  6  9 12 15 18 21]
y1 = data1[:, 1]  # [ 1  4  7 10 13 16 19 22]
z1 = data1[:, 2]  # [ 2  5  8 11 14 17 20 23]
 
# 数据２
data2 = np.random.randint(0, 23, (6, 3))
x2 = data2[:, 0]
y2 = data2[:, 1]
z2 = data2[:, 2]
 
 
# 绘制散点图
fig = plt.figure()
ax = Axes3D(fig)
ax.scatter(x1, y1, z1, c='r', label='顺序点')
ax.scatter(x2, y2, z2, c='g', label='随机点')
 
 
# 绘制图例
ax.legend(loc='best')
 
 
# 添加坐标轴(顺序是Z, Y, X)
ax.set_zlabel('Z', fontdict={'size': 15, 'color': 'red'})
ax.set_ylabel('Y', fontdict={'size': 15, 'color': 'red'})
ax.set_xlabel('X', fontdict={'size': 15, 'color': 'red'})
 
 
# 展示
plt.show()
```
![image.png](2)
```
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

tagdf=pd.read_csv("190409_UWBtest/data/cp_uwb190417_xyz.csv")
print(tagdf.columns.values)
tagdf.rename(columns={tagdf.columns[0]:"t"},inplace=True)
print(tagdf.columns.values)

# 绘制散点图
fig=plt.figure()
ax=Axes3D(fig)
ax.scatter(tagdf.xloc,tagdf.yloc,tagdf.zloc,c=tagdf.tagID)

# 添加坐标轴(顺序是Z, Y, X)
ax.set_zlabel('Z', fontdict={'size': 15, 'color': 'black'})
ax.set_ylabel('Y', fontdict={'size': 15, 'color': 'black'})
ax.set_xlabel('X', fontdict={'size': 15, 'color': 'black'})

plt.show()
```

 3. 