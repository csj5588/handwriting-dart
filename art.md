# 前言

请忘掉所有js相关内容。。。

# lesson 1

## 环境

学习或者调试dart代码之前需要提前安装一些环境。

### Flutter环境

你可以安装Flutter配套环境，这样的话你本地会随带有dart环境命令。

[Flutter开发环境安装](https://flutterchina.club/get-started/install/)

如果你财力雄厚的话可以购买[《Flutter完全手册》](https://juejin.cn/book/6844733786626719757)进行环境搭建，可以少走一些弯路。这本小册看前半部分就可以了，后半部分写的不怎么样。用来搭建环境还是没问题的。

安装完毕后打开终端看到如下命令即为安装成功。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/28febb2553194512a2359550604da693~tplv-k3u1fbpfcp-watermark.image)

可以看到展示详情中又一些命令，可以简单了解一下。

- 分析项目的Dart代码。
- 把Dart编译成各种格式。
- 创建新项目。
- 格式化Dart源代码的惯用格式。
- 使用package。
- 运行Dart程序。(default)
- 在此包中测试运行测试。

### DartPad

你可以在[DartPad](https://dartpad.cn/)在线调试dart代码,类似于[CodeSandBox](https://codesandbox.io/)。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/00240b93944a48568c3c07177fe39538~tplv-k3u1fbpfcp-watermark.image)

这篇文章采用第一种Flutter环境进行演示。因为起因是因为Flutter需要Dart语法。

## Lesson__1

### Main

学习dart第一步就从main函数开始, 创建一个index.dart文件，并写入：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aa3f272b9fa446fdbdfa024211b76e61~tplv-k3u1fbpfcp-watermark.image)

学习语言之前都需要经历一下hello world的洗礼。执行这个文件，执行命令如下：

```shell
$ dart index.dart
```

输出：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6a3f85123a204a3194c45d3d3e24513d~tplv-k3u1fbpfcp-watermark.image)

我们试着把函数main换一个名字.

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/480d93f6d6564ff9849df2a75cf5934c~tplv-k3u1fbpfcp-watermark.image)

则会抛出一个没有main函数的错误。

> main()函数，这是一种特殊的、必需的顶级函数，应用程序从这里开始执行。

函数内`print`对标javascript中的`console`理解即可

### Var

可以看到上方Demo中使用了var声明了一个变量text, 这里的var与javascript中的并不一样。

首先记住一个概念Dart语法中没有所谓的`隐式类型转换`。

我们已知在javascript中是包含`隐式类型转换`概念的，比如说。

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7b8c3f079ee94d52a35a06f25813350b~tplv-k3u1fbpfcp-watermark.image)

学习javascript的过程中你一定会听到过一句话, js是弱语言。

js中var是可以被赋予其他类型数据的，并且隐式转换了表达式中的变量类型。Dart中是没有此过程的。

如果在Dart中重复上述过程，表现如下：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e1e441eb55b6437d828a8c84a2b71645~tplv-k3u1fbpfcp-watermark.image)

> Error: A value of type 'int' can't be assigned to a variable of type 'String'

由上述可知，var在声明的时候就根据右侧的值确定下来了变量类型。上述我们赋予的`'Hello World'`则为String类型。

Dart在编译期会自动匹配var变量的实际类型，并用实际类型来替换该变量的声明，这看上去就好像我们在编码的时候是用实际类型进行申明的。

如果在声明的时候我们没有给予值呢？

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/02e294e50d5f4774898b1a79b304c2e6~tplv-k3u1fbpfcp-watermark.image)

输出：

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c17be01b9a43493388c83f4e3c6e47fd~tplv-k3u1fbpfcp-watermark.image)

可以看到这样的话是可以进行数据类型转换的。区别在于是否在声明的时候赋予值。

## 命名规则

命名规则与javascript保持一致。

  - 标识符不能是关键字。
  - 标识符可以包含字母和数字。
  - 标识符不能包含空格和特殊字符，但下划线(_)和美元($)符号除外。
  - 变量名称不能以数字开头。
  
## 类型检查

Dart与Typescript一样支持类型检查。Dart通过在变量名前加上数据类型来支持。

  - String text = 'Hello World'
  - int number = 666

## NULL

在javascript中有两个特殊的数据类型，null和undefined，官方介绍如下：

- 在 JavaScript 中，没有值的变量，其值是 undefined。typeof 也返回 undefined。
- 在 JavaScript 中，null 是 "nothing"。它被看做不存在的事物。

在Dart中是没有undefined这个数据类型的。所有未初始化的变量的初始值为null。这是因为Dart将所有值都视为对象。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3ea8aff47d8045f3a7b1d6fbbdb0436d~tplv-k3u1fbpfcp-watermark.image)

输出:

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bc2c85589dae45b2b83fb2cd71c6b956~tplv-k3u1fbpfcp-watermark.image)

万物皆对象这句话在开发javascript的过程中你一定听到过，因为现在的javascript开发过程中基本按照面向对象编程思维开发，面试的时候时不时的也会问到你：什么是面向对象编程？。

在Dart中彻底贯彻了万物皆对象这句话。

没有undefined状态并不意味着没有undefined状态，什么意思呢。官方是没有承认有undefined状态的，但是在代码中发现了，也不要惊讶。

## 常量声明

使用final和const关键字来声明常量。Dart阻止修改使用final或const关键字声明变量的值。这些关键字可以与变量的数据类型一起使用，也可以与 var 关键字一起使用。

const关键字用来表示一个编译时常数。使用const关键字声明的变量是隐式final的。

下图展示如果要修改const声明的值时候的场景。

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/064f8e320eea408485ad279291431485~tplv-k3u1fbpfcp-watermark.image)

那么为什么要两个声明常量的类型呢？在Dart中常量分为了两种.

- cosnt变量的初始值只能是编译时确定的值。
- final变量的初始值可以在编译时确定，也可以在运行时确定

什么是运行时确定的常量呢？

- new DateTime.now()
- new Random()

如上就是运行时确定的常量，这样的常量使用final，仔细想一下这里你会想明白的。

或者还有个实际用到的项目场景，在做开发过程中，我们一般要通过网络请求获取业务数据，在编辑阶段网络请求的返回数据是完全不知道的，所以在这个时候使用const 是不行的，应该使用 final 关键字。

## 算术运算符

| 运算符 | 意义 |
| --- | --- |
| + | 加 |
| - | 减去 |
| -expr | 一元减号，也称为否定(反转表达式的符号) |
| * | 乘 |
| / | 除 |
| ～/ | 除以 |
| % | 获取整数除法的余数(模数) |
| ++ | 自增 |
| -- | 自减 |

算术运算符中，因为Dart中没有`隐式类型转换`这个概念，所以就避免了一些javascript中的特殊场景，比如：

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/de6abec6e4b44cc09bf6479366bfc20e~tplv-k3u1fbpfcp-watermark.image)

输出：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6fbeef2ffabd4168b6d9fc21e7c15586~tplv-k3u1fbpfcp-watermark.image)

大家只需要记住类型是严格的即可。

`~/`这个运算符比较有意思，单独讲一下，它可以达到只取整的效果，比如说`10 ~/ 3`输出`3`。

这一点在javascript中实现则如下。

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5fdcab440fc24a27abdc5c8b9792a91f~tplv-k3u1fbpfcp-watermark.image)

一种是除之后转换整数类型，一种是除之后再向下取整。

经过对比之后，是不是希望javascript赶紧加入这个运算符。

## 关系运算符

| 运算符 | 描述 | 实例 |
| --- | --- | --- |
| > | 大于 | (A > B) is False |
| < | 大于 | (A < B) is True |
| >= | 大于等于 | (A >= B) is False |
| <= | 小于等于 | (A <= B) is True |
| == | 相等 | (A == B) is True |
| != | 不相等 | (A != B) is True |

与javascript一致，运算结果返回Boolean类型。

## 类型测试运算符

| 运算符 | 意义 |
| --- | --- |
| is | 如果对象是指定的类型，则为True |
| is！ | 如果对象不是指定的类型，则返回false |

基本理解为类型判断，运算符返回Boolean类型

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f8593469930a4879bfac3633cc63cfb8~tplv-k3u1fbpfcp-watermark.image)

我们可以用`is`来回过头论证上面讲`var`的时候提及的编译时类型声明。看一下这个例子：


----- 

按位运算符
位与	a&b	返回每个位位置的一个，两个操作数的相应位为1。
位或	一个| b	在每个位的位置返回一个，其中一个或两个操作数的相应位是1。
位亦或	a ^ b	在每个位位置返回一个，其中任一个但不是两个操作数的相应位都是1。
位否	~a	反转其操作数的位。
左移位	一个«b	将二进制表示b(<32)位向左移位，从右移零。
有符号右移位	a»b	将二进制表示b(<32)位向右移位，丢弃移位的位。

逻辑运算符

&&	与 − 仅当指定的所有表达式都返回true时，运算符才返回true

(A > 10 && B > 10) is False.
||	或 − 如果指定的至少一个表达式返回true，则运算符返回true

(A > 10 || B > 10) is True.
!	取反 − 运算符返回表达式结果的反函数。. 例如: !(7>5) 返回 false

!(A > 10) is True.

三目一样
a ?? b



