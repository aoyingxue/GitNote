要查看使用什么颜色来制作图，可以使用函数ggplot_build()，然后查看此对象的数据部分（在列colour中是代码）。

```
p <- ggplot(df, aes(x = value, y = value, color = type)) + 
    geom_point(shape = 21, size = 4) 


ggplot_build(p)$data 
# [[1]] 
# colour x y PANEL group 
# 1 #F8766D 1 1  1  1 
# 2 #B79F00 2 2  1  2 
# 3 #00BA38 3 3  1  3 
# 4 #00BFC4 4 4  1  4 
# 5 #619CFF 5 5  1  5 
# 6 #F564E3 6 6  1  6 

```
