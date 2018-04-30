# sql-join-illustration
sql-join-illustration

join 是两张表做交连后里面条件相同的部分记录产生一个记录集， 
union是产生的两个记录集并在一起，成为一个新的记录集 。

## join
可以通过下面这张图来了解join命令
![142233278855062](https://i.imgur.com/tvpRAhB.jpg)

## union

要求：两次查询的列数必须一致

推荐：列的类型可以不一样，但推荐查询的每一列，想对应的类型以一样

可以来自多张表的数据：多次sql语句取出的列名可以不一致，此时以第一个sql语句的列名为准。

如果不同的语句中取出的行，有完全相同(这里表示的是每个列的值都相同)，那么union会将相同的行合并，最终只保留一行。也可以这样理解，union会去掉重复的行。

如果不想去掉重复的行，可以使用union all。

如果子句中有order by,limit，需用括号()包起来。推荐放到所有子句之后，即对最终合并的结果来排序或筛选。

如：(select * from a order by id) union (select * from b order by id);

在子句中，order by 需要配合limit使用才有意义。如果不配合limit使用，会被语法分析器优化分析时去除。

[source](http://www.cnblogs.com/CraryPrimitiveMan/p/3665154.html)