1. 导入 Pandas
   import pandas as pd # This is the standard
2. 将csv写入pandas
   #Reading a csv into Pandas.
df = pd.read_csv('uk_rain_2014.csv', header=0)
3. 查看前 x 行的数据：
#Getting first x rows.
df.head(5)
我们只需要调用 head() 函数并且将想要查看的行数传入。
4. 你可能还想看看最后几行：
#Getting last x rows.
df.tail(5)
5. 修改pandas dataframe的列名：
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
 6. 数据集的总行数
```
#Finding out how many rows dataset has.
len(df)
```
7. 基本统计数据
```
# Finding out basic statistical information on your dataset.

#Limit output to 3 decimal places.
pd.options.display.float_format = '{:,.3f}'.format 
df.describe()
```
这将返回一张表，其中有诸如总数、均值、标准差之类的统计数据：
![image.png](0)
8. 提取某列
```
# Getting a column by label
df['rain_octsep']

# Getting a column by label using .
df.rain_octsep
```
    ++布尔过滤 (boolean masking)++ 

 7. 散点图
  - Tag0.plot.scatter(x='xloc',y='yloc',c='t')