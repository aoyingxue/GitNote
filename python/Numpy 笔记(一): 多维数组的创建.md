
Numpy 笔记(一): 多维数组的创建


## ndarray 的创建
### 从已有数据中创建
从 list, tuple 对象中创建:
```
import numpy as np

a = np.array([1, 2, 3, 4])
print 'a is:', a

b = np.array((1, 2, 3, 4))
print 'b is:', b
a is: [1 2 3 4]
b is: [1 2 3 4]

```


### 从文件中读取

从文件中读取的方法有: fromfile, load, *loadtxt*。其中 fromfile 方法不建议使用，因为 fromfile 读取的文件要求是用 tofile 保存的，而 tofile 方法保存数据到文件时的具体行为是和具体平台有关的。

load 方法读取 save 方法保存下来的二进制文件:

```
import numpy as np
from tempfile import TemporaryFile

origin_array = np.array([1, 2, 3, 4])
np.save('/tmp/array', origin_array)

array_from_file = np.load('/tmp/array.npy')
print array_from_file
[1 2 3 4]

```

可以看一下 /tmp/array.npy 这个文件:

```
file /tmp/array.npy
/tmp/array.npy: data

```

如果希望保存的文件是可读的，那么可以用 savetxt 这个方法，用这个方法保存的数据则用 loadtxt 来读取:

```
import numpy as np

origin_array = np.array([1, 2, 3, 4])
np.savetxt('/tmp/array.txt', origin_array)

array_from_file = np.loadtxt('/tmp/array.txt')
print array_from_file
[ 1.  2.  3.  4.]
再来看一下 /tmp/array.txt 里面的内容:

cat /tmp/array.txt
1.000000000000000000e+00
2.000000000000000000e+00
3.000000000000000000e+00
4.000000000000000000e+00
```


### 从字符串中读取

用 fromstring 方法可以从字符串中读取数据并转换为 一维数组:

```
import numpy as np

array = np.fromstring('1 2 3 4', dtype=float, sep=' ')
print array
[ 1.  2.  3.  4.]
```

如果是用 tostring 将一个多维向量转换为字符串，然后再用 fromstring 读取，也只能得到一个一维数组。另外如果是读用 tostring 转换成的字符串， 建议使用 fromstring 的时候显式指定数组中元素的数据类型 ，不然就 有可能 发生下面这样的悲剧:

```
import numpy as np

array = np.array([1, 2, 3, 4], dtype=int)
print np.fromstring(array.tostring())
[  4.94065646e-324   9.88131292e-324   1.48219694e-323   1.97626258e-323]
```

==fromiter==: 从可迭代对象中生成一维数组

和第一种方法的不同之处在于:

只能返回一维数组
必须显式指定数组中元素的数据类型
输入可以是 所有可迭代对象 ，包括 list、tuple、string、unicode, generator，但需要注意的是，这里的 list 和 tuple 不能有嵌套。
```
# coding: utf-8
import numpy as np


def count_generator():
    for i in range(4):
        yield i


print 'from list:', np.fromiter([1, 2, 3, 4], int)
print 'from tuple:', np.fromiter([1, 2, 3, 4], int)
print 'from string:', np.fromiter('1234', int)
print 'from unicode:', np.fromiter(u'白日依山尽', 'U1')
print 'from generator:', np.fromiter(count_generator(), int)


try:
    print 'from nested list:', np.fromiter([[1, 2], [3, 4]], int)
except ValueError:
    print 'bad list'
from list: [1 2 3 4]
from tuple: [1 2 3 4]
from string: [1 2 3 4]
from unicode: [u'\u767d' u'\u65e5' u'\u4f9d' u'\u5c71' u'\u5c3d']
from generator: [0 1 2 3]
from nested list: bad list
```

### 创建特定形状的多维数组并进行填充
==ones==

### 创建给定形状的多维数组并将数组中所有元素填充为 1:

```
import numpy as np

print np.ones((3, 4))
[[ 1.  1.  1.  1.]
 [ 1.  1.  1.  1.]
 [ 1.  1.  1.  1.]]

```

==zeros==

类似 ones ，但用 0 进行填充:

```
import numpy as np

print np.zeros((3, 4))
[[ 0.  0.  0.  0.]
 [ 0.  0.  0.  0.]
 [ 0.  0.  0.  0.]]

```

==empty==

类似 ones, 但不进行初始化，得到的多维数组中的元素值是不确定的。

```
import numpy as np

print np.empty((3, 4))
[[  6.93164023e-310   1.66900197e-316   4.64956088e-317   4.00193173e-322]
 [  1.77481898e-316   6.93164023e-310   9.30845863e-039   2.42092166e-322]
 [  6.93164023e-310   6.93164023e-310   4.68423639e-320   0.00000000e+000]]

```

==full==

类似 ones, 但需要自己手动指定需为多维数组填充的值。
```
import numpy as np

print np.full((3, 4), 17)
[[ 17.  17.  17.  17.]
 [ 17.  17.  17.  17.]
 [ 17.  17.  17.  17.]]

```

从 numerical range 创建多维数组
==arange==

创建一个一维的数组，用法同 Python 内建方法 range:

```
import numpy as np

print np.arange(10)
print np.arange(0, 10)
print np.arange(9, -1, -1)
[0 1 2 3 4 5 6 7 8 9]
[0 1 2 3 4 5 6 7 8 9]
[9 8 7 6 5 4 3 2 1 0]

```

==linspace==

给定一个区间，取其 N 等分点组成一个一维数组:
```
import numpy as np

print np.linspace(1, 10, num=10)
[  1.   2.   3.   4.   5.   6.   7.   8.   9.  10.]

```

==logspace==

给定一个 对数尺度(log scale)区间 ，取其 N 等分点对应的 线性尺度(linear scale)上的数值:

```
import numpy as np

print np.logspace(1, 3, num=3)
print np.log10(np.logspace(1, 3, num=3))
[   10.   100.  1000.]
[ 1.  2.  3.]

```

==meshgrid==

根据给定的坐标向量创建坐标矩阵。
```
import numpy as np


print np.meshgrid(np.arange(0, 6))
print

x, y = np.meshgrid(np.arange(-1, 2), np.arange(0, 2))
print 'x is:', x
print 'y is:', y
print

print 'points built by (x, y):'
print np.rec.fromarrays([x, y])
[array([0, 1, 2, 3, 4, 5])]

x is: [[-1  0  1]
 [-1  0  1]]
y is: [[0 0 0]
 [1 1 1]]

points built by (x, y):
[[(-1, 0) (0, 0) (1, 0)]
 [(-1, 1) (0, 1) (1, 1)]]

```

在上面的例子中，所得到的是 X 轴上 [-1, 0, 1] 和 X 轴上 [0, 1] 构成的一个 3x2 的网格，共有 6 个点。返回的两个值中的 x 是这 6 个点 在 X 轴上的投影， y 则是这 6 个点在 y 轴上的投影。

meshgrid 方法的参数数量不受限，可以得到任意 N 维空间中的坐标矩阵。

了解 meshgrid 方法的功能后，可以来做一些有趣的事情，比如:
```
import numpy as np
import matplotlib.pyplot as plt

x, y = np.meshgrid(np.arange(-1, 1, 0.01), np.arange(-1, 1, 0.01))

contor = np.sqrt(x ** 2 + y ** 2)
plt.imshow(contor)
plt.colorbar()

plt.savefig('contor.png')
'../../../assets/img/contor.png'
contor.png

```
![image.png](1)

==mgrid==

mgrid 的功能与 meshgrid 类似，但有几点不同:

mgrid 不是函数，而是一个类的对象
mgrid 和 meshgrid 的使用方式不一样，meshgrid 需要传入一维数组作为对象，而 mgrid 则直接使用 '[]' 运算符

```
import numpy as np

np.meshgrid(np.arange(-1, 2), np.arange(-1, 2))
np.mgrid[-1:2, -1:2]

```

返回值的前两个顺序相反

```
import numpy as np

x, y = np.meshgrid(np.arange(-1, 1), np.arange(-1, 1))
xx, yy = np.mgrid[-1:1, -1:1]
print (x - yy).sum(), (y - xx).sum()

x, y, z = np.meshgrid(np.arange(-1, 1), np.arange(-1, 1), np.arange(-1, 1))
xx, yy, zz = np.mgrid[-1:1, -1:1, -1:1]
print (x - yy).sum(), (y - xx).sum(), (z - zz).sum()

x, y, z, w = np.meshgrid(np.arange(-1, 1), np.arange(-1, 1), np.arange(-1, 1), np.arange(-1, 1))
xx, yy, zz, ww = np.mgrid[-1:1, -1:1, -1:1, -1:1]
print (x - yy).sum(), (y - xx).sum(), (z - zz).sum(), (w - ww).sum()
0 0
0 0 0
0 0 0 0

```

==ogrid==

ogrid 与 mgrid 类似，也是类的对象而非函数，但和 mgrid 的不同之处在于，它返回的结果是 稀疏 的。
```
import numpy as np

x, y = np.mgrid[-1:2, 3:6]
print 'x from mgrid:'
print x
print 'y from mgrid:'
print y

x, y = np.ogrid[-1:2, 3:6]
print 'x from ogrid:'
print x
print 'y from ogrid:'
print y
x from mgrid:
[[-1 -1 -1]
 [ 0  0  0]
 [ 1  1  1]]
y from mgrid:
[[3 4 5]
 [3 4 5]
 [3 4 5]]
x from ogrid:
[[-1]
 [ 0]
 [ 1]]
y from ogrid:
[[3 4 5]]

```

==fromfunction==

fromfunction 的行为稍微有点不一样，它有三个参数:

function
shape
dtype(optional)
其中 function 的参数个数要和 shape 的长度一致，fromfunction 会对 shape 对应的多维数组中每个元素的坐标传给 function ，然后将返回值组合起来。
```
import numpy as np

def f(x, y):
    return (x, y)


def g(x, y):
    return x + y


x, y = np.fromfunction(f, (3, 3))
print 'x generated by f is:\n', x
print 'y generated by f is:\n', y
print 'array generated by g is:\n', np.fromfunction(g, (3, 3))
x generated by f is:
[[ 0.  0.  0.]
 [ 1.  1.  1.]
 [ 2.  2.  2.]]
y generated by f is:
[[ 0.  1.  2.]
 [ 0.  1.  2.]
 [ 0.  1.  2.]]
array generated by g is:
[[ 0.  1.  2.]
 [ 1.  2.  3.]
 [ 2.  3.  4.]]

```

### 创建矩阵(二维数组)
==eye:==

创建一个对角矩阵或者 super/sub diagional square matrix，且所指定的对角线上的元素值为 1.
```
import numpy as np

print np.eye(2)
print np.eye(2, 3, k=1)
print np.eye(2, 3, k=-1)
[[ 1.  0.]
 [ 0.  1.]]
[[ 0.  1.  0.]
 [ 0.  0.  1.]]
[[ 0.  0.  0.]
 [ 1.  0.  0.]]

```

==identity==

创建单位矩阵
```
import numpy as np

print np.identity(2)
print np.identity(3)
[[ 1.  0.]
 [ 0.  1.]]
[[ 1.  0.  0.]
 [ 0.  1.  0.]
 [ 0.  0.  1.]]

```

==diag==

创建对角矩阵或 super/sub diagional matrix。与 eye 的不同之处在于:

对角线上的元素值不是都为 1 ，而是手动指定
不需要制定矩阵的形状，而是靠指定对角线上元素值来确定矩阵的形状
```
import numpy as np

print np.diag([1, 1, 1])
print np.diag([3, 4], 1)
[[1 0 0]
 [0 1 0]
 [0 0 1]]
[[0 3 0]
 [0 0 4]
 [0 0 0]]

```

==diaglat==

对输入进行 flatten 然后用之创建对角矩阵
```
import numpy as np

print np.diagflat([[1, 1], [1, 1]])
[[1 0 0 0]
 [0 1 0 0]
 [0 0 1 0]
 [0 0 0 1]]

```
