##葫芦娃编程作业（三）
![Calabash](http://a1.att.hudong.com/38/79/19300405417449133774797662036.jpg)
##简介
* 葫芦娃和蝎子精准备在二维空间作战



##功能
* 葫芦娃和蝎子精团队分别位于空间的两侧
* 爷爷和蛇精分别位于两侧为两边加油助威
* 两个团队均可变换阵型
* 初始站定后蝎子精团队将变换一次阵型

##用到的面向对象概念&机制
* 将各个生物体以及排队布阵都抽象为了类，好处是能够实现不同对象的分离，使得代码结构清晰，易于维护与扩展。
* 使用了继承，使得葫芦娃等具有独有特征的生物体可以在一般生物体上的基础上扩充新的方法，减少了代码的重复性，也使得相关类之间的层次更加清晰。
* 用到了“消息”。使得对象之间能够相互通信，使Control这个对象存在更加合理，也使得请求或者修改某个对象的某些属性的值更加简便。



##设计思路
* 创建一个生物体类，葫芦娃、蝎子精等子类均从生物体类中继承。
    * 生物体类中包含坐标类成员，存储此时生物体对应二维空间的坐标。
	* 生物体类中还有一个私有成员“属性”，用来标识生物体类型。
	* 将蝎子精和小喽啰都包含在一个Monster类里面，用属性来唯一标识。

* 各生物体子类中分别包含了各个生物体独有的方法
* 一个Mysort类将葫芦娃排好队或者打乱队形
* 一个阵型类，包含：
	* 存储二维空间信息
		* 用 '.' 表示此地没有生物体
		* 'C' 'M' 'G' 'S' 分别表示此地的生物体是葫芦娃，蝎子精团队，爷爷，蛇精
	* 排阵等一切和改变位置有关的方法
