### 1. 导入 Pandas
   import pandas as pd # This is the standard[1](baidu.com)
### 2. 将csv写入pandas
   #Reading a csv into Pandas.
df = pd.read_csv('uk_rain_2014.csv', header=0)
### 3. 查看前 x 行的数据：
#Getting first x rows.
df.head(5)
我们只需要调用 head() 函数并且将想要查看的行数传入。
### 4. 你可能还想看看最后几行：
#Getting last x rows.
df.tail(5)
### 5. 修改pandas dataframe的列名：
``` 
# 显示df每列的名称
df.columns.values

# 将第三列的列名改为'new name'
>>> df.rename(columns={ df.columns[2]: "new name" }, inplace=True)

# 假如df一共有三列，你想把所有列名依次改为'col_1', 'col_2', 'col_3'
>>> df.columns = ['col_1', 'col_2', 'col_3']

#更换列的名字 Changing column labels.
df.columns = ['water_year','rain_octsep', 'outflow_octsep',
              'rain_decfeb', 'outflow_decfeb', 'rain_junaug', 'outflow_junaug']

df.head(5)
   ```
 ### 6. 数据集的总行数
```
#Finding out how many rows dataset has.
len(df)
```
### 7. 基本统计数据
```
# Finding out basic statistical information on your dataset.

#Limit output to 3 decimal places.
pd.options.display.float_format = '{:,.3f}'.format 
df.describe()
```
这将返回一张表，其中有诸如总数、均值、标准差之类的统计数据：
![image.png](0)
### 8. 提取某列数据
```
# Getting a column by label
df['rain_octsep']

# Getting a column by label using .
df.rain_octsep
```
   - ++布尔过滤 (boolean masking)++ 

```
# Creating a series of booleans based on a conditional
df.rain_octsep < 1000 
#Or df['rain_octsep] < 1000
```
上面的代码将会返回一个由布尔值构成的 dataframe。True 表示在十月-九月降雨量小于 1000 mm，False 表示大于等于 1000 mm。我们可以用这些条件表达式来过滤现有的 dataframe。
```
# Using a series of booleans to filter
df[df.rain_octsep < 1000]

# 复合条件表达式 Filtering by multiple conditionals
df[(df.rain_octsep < 1000) & (df.outflow_octsep < 4000)] 
# Can't use the keyword 'and'
```
  - 使用字符串方法来进行过滤：
```
# Filtering by string methods
df[df.water_year.str.startswith('199')]
```
### 9. 提取行数据
 - 行标签是==数字型==的：iloc()基于数字
  ```
#Getting a row via a numerical index
df.iloc[30]
   ```
 - 通过设置==索引==：
 ```
# Setting a new index from an existing column
df = df.set_index(['water_year'])
df.head(5)
```
将 water_year 列设置为索引：
![image.png](1)
 - 字符型数据：loc() 基于标签
 ```
# Getting a row via a label-based index
df.loc['2000/01']
```
 - ix()：基于标签，但同时支持数字型索引作为==备选==
 - 标签排序：调用 sort_index 方法
 ```
df.sort_index(ascending=False).head(5) #inplace=True to apple the sorting in place
```
 - 恢复索引：reset_index
 ```
# Returning an index to data
df = df.reset_index('water_year')
df.head(5)
```
这一语句会将索引恢复成数据形式：
![image.png](2)
### 10.对数据集应用函数 apply / applymap
```
# Applying a function to a column
def base_year(year):
    base_year = year[:4]
    base_year= pd.to_datetime(base_year).year
    return base_year

df['year'] = df.water_year.apply(base_year)
df.head(5)
```
上面的代码创建了一个叫做 year 的列，它只将 water_year 列中的年提取了出来。这就是 apply 的用法，即对一列数据应用函数。如果你想对整个数据集应用函数，就要使用 applymap 。
![image.png](3)
### 11. 重新建立数据集结构
 1. groupby
   ```
#Manipulating structure (groupby, unstack, pivot)
# Grouby
df.groupby(df.year // 10 *10).max()
```
groupby 会按照你选择的列对数据集进行分组。上例是按照年代分组。不过仅仅这样做并没有什么用，我们必须对其调用函数，比如 max 、 min 、mean 等等。例中，我们可以得到 90 年代的均值。
![image.png](4)
你也可以按照多列进行分组：
```
# Grouping by multiple columns
decade_rain = df.groupby([df.year // 10 * 10, df.rain_octsep // 1000 * 1000])[['outflow_octsep',                                                              'outflow_decfeb', 'outflow_junaug']].mean()
decade_rain
```
![image.png](5)
 2. unstack：将一列数据设置为列标签
 ```
# Unstacking
decade_rain.unstack(0)
```
![image.png](6)
### 10. 散点图
  - Tag0.plot.scatter(x='xloc',y='yloc',c='t')