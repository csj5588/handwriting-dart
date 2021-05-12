## 循环

循环表示必须重复的一组指令

循环分为了两类

1.确定循环。迭代次数是确定/固定的循环称为确定循环 。
2.不确定循环。当循环中的迭代次数不确定或未知时，将使用不定循环

for

for 循环有三个部分：初始化(i = num)，所述条件(i> = 1)和最终个表达式(i--)。

```dart
main() {
  for (var i = 0; i < 10; i++) {
    print(i);
  }
}
```

for in // 用于循环对象的属性

在每次迭代中，来自对象的一个​​属性被分配给变量名称，并且此循环继续，直到对象的所有属性都用完为止。

```dart
main() {
  var obj = [1, 2];

  for (var prop in obj) {
    print(prop);
  }
}

```
不确定循环
while

```dart
main() {
  var a = 0;

  while(a < 10) {
    a++
  }
  print(a);
}

```

do while

```dart
main() {
  var a = 0;

  do {
    a++;
  }
  while(a < 10);
  print(a);
}

```

do ... while循环类似于while循环，只是do ... while循环不会在第一次循环执行时评估条件。但是，将对后续迭代评估条件。换句话说，代码块将在do ... while循环中至少执行一次。

break

该 break 语句用来作为控制了结构的。在循环中使用 break 会导致程序退出循环。以下是 break 语句的示例。

```dart
main() {
  var a = 0;

  for (var i = 0; i < 10; i++ ) {
    if (i == 2) {
      break;
    }
    a++;
  }
  print(a);
}
```

四种循环都有，这里举例for，while也可

continue

在 continue 语句跳过当前迭代的后续语句，并采取控制回到循环的开始。与 break 语句不同， continue 语句不会退出循环。它终止当前迭代并开始后续迭代。



```dart
var a = 0;

for (var i = 0; i < 10; i++ ) {
  if (i % 2 == 1) {
    continue;
    // 这里不会执行
  }
  a++;
}
print(a);
```

条件语句

if 

if ... else 语句在执行的代码块之前判断条件。

表达式或者值的内容返回Boolean，则执行代码块内语句

else ... if用于检测多个条件

switch

```dart
switch (表达式) {
  case n:
    代码块
    break;
  case n:
    代码块
    break;
  default:
    默认代码块
} 
```

以下规则适用于switch语句

switch中可以有任意数量的case语句。
case语句只能包含常量。它不能是变量或表达式。
variable_expression和常量表达式的数据类型必须匹配。
除非你在每个代码块之后放置一个中断，否则执行会流入下一个块。
case表达式必须是唯一的。
默认块是可选的。

Dart中switch/case语句使用 == 操作来比较整数、字符串或其他编译过程中的常量，从而实现分支的作用。switch/case语句的前后

操作数必须是相同类型的对数实例。每一个非空的case字句最后都必须跟上break语句。代码示例如下:

```
var a = 20;
var b = 2;
switch(a - b) {
  case 18:
  case 20:
    print('20');
    break;
  default: 
    print('end');
}
```

dart中default只可以放最下面

case后面必须是常量表达式
```dart
main() {
  const a = 20;
  const b = 2;
  var c = 18;
  switch(c) {
    case a - b:
      print('20');
      break;
    default: 
      print('end');
  }
}

```