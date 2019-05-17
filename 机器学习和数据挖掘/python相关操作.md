1. 导入 Pandas
   import pandas as pd # This is the standard
2. 写入pandas
   #Reading a csv into Pandas.
df = pd.read_csv('uk_rain_2014.csv', header=0)
3. 查看前 x 行的数据：
#Getting first x rows.
df.head(5)
我们只需要调用 head() 函数并且将想要查看的行数传入。
4. 
1. 修改pandas dataframe的列名：
``` 
# 显示df每列的名称
df.columns.values

# 将第三列的列名改为'new name'
>>> df.rename(columns={ df.columns[2]: "new name" }, inplace=True)

# 假如df一共有三列，你想把所有列名依次改为'col_1', 'col_2', 'col_3'
>>> df.columns = ['col_1', 'col_2', 'col_3']
   ```
2. 读写csv
  - Tag0=pd.read_csv("190409_UWBtest/data/tag0.csv")
3. 散点图
  - Tag0.plot.scatter(x='xloc',y='yloc',c='t')