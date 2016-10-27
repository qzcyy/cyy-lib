##版本

2.x早期

3.x现在

4.x测试

一般的我们使用3.3.5

##栅格

##在栅格中,使用row和col来定义栅格,而且所有的row和col必须放置在.container中

container:固定宽度,在一定范围内宽度固定

container-fluid:百分百宽度,会根据父亲盒子进行缩放

###在bootstrap中,每一个row被默认的分成了12行,可以使用col-数值来划分所占的屏幕比例

###如果超过了12行,则自动换行

如果想要在不同的屏幕宽度上实现不同的布局,则需要使用col-lg(大pc) col-md(正常pc) col-sm(平板) col-xs(手机)

如果只写了col-lg 则会在小于1200px的宽度下占一行

如果是 col-lg col-md 则会在小于992px 宽度下占一行

如果是col-lg col-md col-sm 会在小于768px宽度下占一行

如果都写了包括col-xs 则会根据屏幕宽度自己分配

