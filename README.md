# handwriting dart

第一节：待更新,正在忙工作，晚些更新Github

## 前言

本节接着第二节讲解：数值类型、字符串类型

视频讲解地址：待上传

## 数值型

Dart中的数值型可以分为两种，int类型，double类型

### int类型

int类型为任意大小的整数。

在数学中的整数概念如下：

> 整数（integer）是正整数、零、负整数的集合。

看一个例子：

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/569e2431cbe448d19ee1511a6cadc43a~tplv-k3u1fbpfcp-watermark.image)

如果声明时为赋值会输出null，第一节课讲过原因。Dart中所有声明时未赋值变量都为null。

### double类型

Dart Double是IEEE 754标准中指定的64位浮点数。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/38d28af924724327b22451f6df614ab3~tplv-k3u1fbpfcp-watermark.image)

因为Dart中也使用了IEEE 754标准的64位浮点数类型，javascript也一样，所以大家比较了解的一些浮点数精度问题在Dart中依然存在，比如下方情况。

`0.1 + 0.2 != 0.3`

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b551734ca5684e0a8011060d454bdbde~tplv-k3u1fbpfcp-watermark.image)

`23.6 - 23 != 0.6`

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f88f2bf2587d4ba797fa89d5e0a14328~tplv-k3u1fbpfcp-watermark.image)

javascript中也是一样的场景，因为参照了同样的浮点数规则。

这一点大家注意一下即可，如果想知道具体原理，这两天我将把这类情况单独写篇文章剖析一下。

我们需要注意的是，平时开发中注意精度收拢即可。

### 属性及方法

这里我们主要讲一下int类型变量的一些属性和方法。

#### hashcode

返回数值的hash码，看一下例子：

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/504d0db147a049f895f7143ae415abc2~tplv-k3u1fbpfcp-watermark.image)

输出：

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c9b34594f73e4312a0425a796c1ac4ed~tplv-k3u1fbpfcp-watermark.image)

#### isFinite

如果数字有限，则为真；

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/67e69a0b8be7471080b01e3fd79ad162~tplv-k3u1fbpfcp-watermark.image)

什么情况为无限情况呢？Dart中有这样的一种情况

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0e18da07746f4de4b18f0f183ac97250~tplv-k3u1fbpfcp-watermark.image)

#### isInfinite

该数字是正无穷大还是负无穷大。如果都不是则返回false；

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3196e21b44664d1abdfc5df12e1a5bde~tplv-k3u1fbpfcp-watermark.image)

#### isNaN

如果数字是双重非数字值，则为真; 否则，是的。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4b5f68f905004841965fd24caddf1854~tplv-k3u1fbpfcp-watermark.image)

#### isNegative

如果数字是负数，则此属性返回布尔值true。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f3ccaecffc0647a585b2fce34af29a16~tplv-k3u1fbpfcp-watermark.image)

#### isEven & isOdd

是否是偶数，是否是奇数

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/943c251c7ba14a73b96726fabdd368f3~tplv-k3u1fbpfcp-watermark.image)

#### abs()

返回数字的绝对值。

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7dd88fc4ab284adf99dea0c520cf2ce9~tplv-k3u1fbpfcp-watermark.image)

#### ceil()

返回不小于该数字的最小整数

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2e9849d0267f4451b0a615ffb074e8b0~tplv-k3u1fbpfcp-watermark.image)

#### floor()

返回不大于当前数字的最大整数

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/866e5d79e4674c359672701da335dc0d~tplv-k3u1fbpfcp-watermark.image)

#### compareTo(x)

它返回一个整数，表示两个数字之间的关系。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/94f0682691884921a683b2e8f75bf70d~tplv-k3u1fbpfcp-watermark.image)

- 0 - 如果值相等。
- 1 - 如果当前数字对象大于指定的数值。
- -1 - 如果当前数字对象小于指定的数字值。

#### round()

此方法返回舍入到最接近整数的数字的值。可理解为四舍五入

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b5333d8cf87945be85178f12ee10fefa~tplv-k3u1fbpfcp-watermark.image)

#### toDouble()

整型转双精度浮点类型。

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/126700f859ed47faa9883185e7069690~tplv-k3u1fbpfcp-watermark.image)

#### toInt()

双精度浮点类型转整型。以裁剪方式，无四舍五入

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/564cc6a95f7c4542b29c8d0af06c4d35~tplv-k3u1fbpfcp-watermark.image)

#### toString()

此方法返回数字值的字符串表示形式

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a1277a40454f4e4db6e04fb1aec5536c~tplv-k3u1fbpfcp-watermark.image)

官方还有一些不是很常用的属性及方法，这里就没有多说，上面的例子大家以javascript的思想来理解就可以了。

## 字符串

在Dart中字符串有几种表现形式。

- 单行字符串使用单引号或双引号编写
- 多行字符串使用三引号编写
- 单引号包含双引号
- 双引号包含单引号
- 三引号包含双引号和单引号

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7cb4f17061c147e69f9b0ac1009b0e7e~tplv-k3u1fbpfcp-watermark.image)

输出：

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/47e0979357dc4955a41691ddc09d90d4~tplv-k3u1fbpfcp-watermark.image)

### 字符串拼接

#### 字符串拼接使用`+`.

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/be0123f923ac42e2bcc15133b29fe7ef~tplv-k3u1fbpfcp-watermark.image)

#### 相邻拼接

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f0386e295298477796fcb6a4bbbfe2fe~tplv-k3u1fbpfcp-watermark.image)

#### $拼接

如果拼接处为变量直接使用`$`

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/43b86c7c4d7e488398109d82fc137484~tplv-k3u1fbpfcp-watermark.image)

如果拼接处为表达式使用`${}`

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/47390d5d400143e6bfdd6404cb46230e~tplv-k3u1fbpfcp-watermark.image)

### 属性及方法

#### 索引运算符

String类型字符串可通过索引运算符访问代码但愿的字符串表示形式

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e9ccaf0dde6e4b30abf2045b67f12fb3~tplv-k3u1fbpfcp-watermark.image)

#### 字符串切割

使用substring切割字符串，返回切割索引范围内容

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/895984da91144d91a70b8b43afcc7c26~tplv-k3u1fbpfcp-watermark.image)

#### isEmpty

此字符串是否为空。

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5bcaa5f0c3964dcf9e100830f9b0bda7~tplv-k3u1fbpfcp-watermark.image)

#### isNotEmpty

此字符串是否不为空

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/dad9dfb867914e4a9c6f90eb607b3054~tplv-k3u1fbpfcp-watermark.image)

#### length

获取字符串长度

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c137832000b54ab9840a8334deafcd4c~tplv-k3u1fbpfcp-watermark.image)

#### trim()

去除字符串前后的空格并返回

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/143fe96d0d634e69b684b550ef5bec8d~tplv-k3u1fbpfcp-watermark.image)

#### compareTo()

比较两个字符串之间的关系

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8ac754f1b92b430588d3515614da73ad~tplv-k3u1fbpfcp-watermark.image)

关系对照表：

- 0 - 字符串相等时。
- 1 - 当第一个字符串大于第二个字符串时
- -1 - 当第一个字符串小于第二个字符串时

该顺序与两个字符串不同的第一个位置处的代码点的顺序相同。如果一个字符串是另一字符串的前缀，则较短的字符串将在较长的字符串之前排序。如果字符串具有完全相同的内容，则它们在排序方面是等效的。排序不检查Unicode等效性。比较是区分大小写的。

#### replaceAll()

用给定值替换与指定模式匹配的所有子字符串。

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/190ef0648922492d9376e39cf16e51f7~tplv-k3u1fbpfcp-watermark.image)

支持正则表达式

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3e3662bc84b94b6f970e09aa7eb6ec77~tplv-k3u1fbpfcp-watermark.image)

#### replaceRange()

replaceRange第一个参数是开始下标，第二个参数是结束下标，第三个参数是要替换的字符串。替换的字符串包含开始下标，不包含结束下标，并且开始下标的数字要>=0,小于等于结束下标，结束下标的值要小于等于字符串长度，否则会报错。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5cbb7e2599414248b7ce25660b5b058d~tplv-k3u1fbpfcp-watermark.image)

#### split()

用给定值替换与指定模式匹配的所有子字符串。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3a68b20df2f140a598bcd348c5180733~tplv-k3u1fbpfcp-watermark.image)

## END

第三节讲解，数值类型、字符串类型，这两个知识点中与javascript的区别还是较多的，需要大家使用的时候注意下。打算开两个分支文章，关于hashCode，关于IEEE 浮点类型原理。






