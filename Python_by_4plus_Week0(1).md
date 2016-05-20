#Python爬虫之Week0
##再次入坑
小白又来给自己挖坑了。上次是Python 2期，这次是爬虫，没错，还是Python，不过是从2.7到3，反正上次也没学多少，没啥切换成本，科科。

##一 准备工作
###Step 1 安装Python环境
在下是Mac党，之前安装了Homebrew，于是一行代码一键安装甚是舒爽~
![Homebrew大法好](http://upload-images.jianshu.io/upload_images/448013-ceceee4010592d63.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在终端输入「Python3」检查一下装好没：

![Python3安装成功！](http://upload-images.jianshu.io/upload_images/448013-d74c5debed081b54.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###Step 2 使用IDE工具
IDE工具什么鬼？
Wikipedia一下，原来是集成开发环境（Integrated Development Environment），一类辅助开发计算机程序的应用软件。

Soga，那么，装！
[PyCharm CE 官方下载地址（我选的免费社区版）](https://www.jetbrains.com/pycharm/download/)
![图标不算丑](http://upload-images.jianshu.io/upload_images/448013-494ccdaf013f2fec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

PS：选择这个而不是 Sublime，是因为文本编辑器更轻量级，和 IDE 相比弱爆了，为了debug 更顺利，也因为既然选择了一套教程，那就将偏见进行到底！

菜单里 「appearance」 里把 theme换成 「darcula」 ，「Colors & Fonts」里面更换就可以，此处更换成「Monokai」主题。

至此，开工前基础准备完成！（散花~）

##二 Python基础中的基础——变量与字符串

由于之前py2期和《笨办法学Python》跟到33课，有了点点底子（天啊，我还是有底子的人！）所以此部分会比较简略。

PS：再次说下《笨办法学Python》是本好书。* [点此为作者建的免费Learn Python The Hard Way网站（视频收费），邮电出了中文版至第三版](http://learnpythonthehardway.org/book/intro.html)

###变量（赋值）
不要随便给变量命名哟，不然会给日后的你带来困惑的！
命名请尽量使用英文命名（顺便学英语不是）

###print（）打印

###string （字符串）
一种Python数据类型
"任何在这双引号之间的文字"
'单引号其实与双引号完全一样'
'''三个引号，给过长的文字，
可以随意换行'''

###字符串的基本用法——合并

###integer（整数）

`type（）`
当不知道变量是什么类型，通过`type（）`函数来查看类型

`#coding:utf-8`
 中文注释会报错，So开头加上此行代码


![不同数据类型的转化](http://upload-images.jianshu.io/upload_images/448013-6e4e089d7e3a1912.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

PS：字符串也可以相减相乘啦~ 
至此，掌握了字符串最基本用法！
```
Perform = ' Good job! '
Name = '4+,'
today = Name + Perform 
print(today)

4+, Good job! 
```

###字符串的分片与索引
通过 ' string[x] ' 的方式进行索引、分片(slice)

![对照理解表（从0开始！）](http://upload-images.jianshu.io/upload_images/448013-3d0981f2f780ca83.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

实际项目中，切片是神器！编写完爬虫后，在网页中解析出部分图片链接，像是这样

![解析出来的图片url](http://upload-images.jianshu.io/upload_images/448013-278682470a1b16b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

为了进行统一命名，观察规律，决定以链接尾部倒数10个字符进行命名，于是输入代码如下：
![](http://upload-images.jianshu.io/upload_images/448013-9922416ea6384d38.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
得到结果 `0kuwex.jpg`

###字符串的Method（方法）
Python是面向对象编程（不要想到那个段子去XD）
Method（方法）——对象拥有各种功能，特性，专业术语

（吃个午饭休息一下，恩，今天吃煎三文鱼和鳗鱼太卷）
（吃完休息完啦，继续继续）

>**e.g.1**实现输入电话号码后只显示后4位，其余用*遮挡

>![](http://upload-images.jianshu.io/upload_images/448013-3854a05baa6b38e7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
>新字符串'replace()'进行遮挡，'phone_number[:9]'代表要被替换掉的部分（不包括第9位，从0开始计数），后面的''*'*9'表示将要替换成什么字符，也就是把星号乘以9，显示9个 *。 

-
>**e.g.2**电话号码联想功能（大概思路）

>![](http://upload-images.jianshu.io/upload_images/448013-4fb3175ff97892d1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##字符串格式化符
常见的填空题

![](http://upload-images.jianshu.io/upload_images/448013-3387df2516a618f7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

'.format()'批处理的三种方式

![](http://upload-images.jianshu.io/upload_images/448013-3ed5cc46c4cfbbde.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>**至此，掌握了变量和字符串的基本概念和常用方法欧耶。**

##三 最基本的魔法——函数

![看图说话，恩](http://upload-images.jianshu.io/upload_images/448013-cb89eb34b89b308f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

总之，Python中所谓函数，就是把要处理的对象放到一个名字后的括号里。
3.50版本为例，有68个内建函数（Built-in Functions）
我的理解里，函数像是已经设定好常用功能的模板
* [Python官网上各个函数的介绍：2. Built-in Functions — Python 3.5.1 documentation](https://docs.python.org/3/library/functions.html)

###创建函数
除了内建函数，还要学会设计符合自身使用需求的函数。

'def' 即 define ，定义。创建函数。
'arg' 即 argument ，参数。
'return' 即返回结果
使用函数这种行为叫做call（调用）

![Define a function named 'funtion' which has two arguments : arg1 and arg2, return the result--'Something' ](http://upload-images.jianshu.io/upload_images/448013-ec504b90dd523864.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>Tips:珍爱生命，从缩进开始。

###传递参数与参数类型
对一开始就设定了必要参数的函数来说，我们打出函数的名称并向括号中传递参数实现对函数的call，只要把参数放进函数的括号中即可。

![计算梯形面积的自建函数](http://upload-images.jianshu.io/upload_images/448013-e9cc767c6f53fc96.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
传递参数的方式有两种
1. 位置参数 （positional argument）

![位置参数 ](http://upload-images.jianshu.io/upload_images/448013-736817e9468a0b80.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2. 关键词参数 （keyword argument）

![关键词参数 ](http://upload-images.jianshu.io/upload_images/448013-bbe1bea664672903.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###默认参数
给参数设定默认值，只需在**定义的时候给参数赋值即可**（不同于传入参数，这可是在定义的时候！）

![如图部分没太懂](http://upload-images.jianshu.io/upload_images/448013-63563349357e35f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###设计自己的函数
e.g.敏感词过滤器

##修订
2016.5.2 创建
