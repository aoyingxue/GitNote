### 简述
在之前读取csv文件的时候，发现第一列被读到了dataframe的column中了，而不是读到了index中，查阅完文档后得到解决。

### 解决办法
```
index_col : int or sequence or False, default None 
Column to use as the row labels of the DataFrame. If a sequence is given, a MultiIndex is used. If you have a malformed file with delimiters at the end of each line, you might consider index_col=False to force pandas to not use the first column as the index (row names)
```
比如说，下面这个代码就可以解决了~ 
将第一列变为index。这样的读取进来~
```
data = pd.read_csv('1.csv', index_col=0)
```