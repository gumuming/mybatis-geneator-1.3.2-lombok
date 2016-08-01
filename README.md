# MybatisGenerator
MyBatis代码生成器，生成Model、Dao、Mapper等

## 说明
1.基于原生的mybatis-geerator，修改了Mapper.xml文件的空格，原来是两个空格，因为强迫症，改成了四个空格，也就是一个Tab键，后续可能会加上Model自动生成注释等。。
2.执行方式：ShellRunner.java

```
修改记录：

1、Mapper.xml空格改成四个空格
修改详情：

org.mybatis.generator.api.dom.OutputUtilities

mybatis-generator 里面我觉得首先最应该改的就是 OutputUtilities 这个类，它里面有个 xmlIndent 方法是用来控制生成的 xml 文件中空格的缩进，默认是两个空格
但四个空格对于我们来说已经深入骨髓了，所以必须改。 在 sb.append( "  " ) 里面增加两个空格就可以了。 

2、修改dao包下的名称，由原来的XXXMapper改成XXXDao
修改详情：
org.mybatis.generator.api.IntrospectedTable

calculateJavaClientAttributes方法(大概820行)
 sb.append("Mapper");注释掉改成 sb.append("Dao");
```
