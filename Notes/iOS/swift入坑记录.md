<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Swift 入坑记录](#swift-%E5%85%A5%E5%9D%91%E8%AE%B0%E5%BD%95)
  - [资料](#%E8%B5%84%E6%96%99)
    - [Swift 语言](#swift-%E8%AF%AD%E8%A8%80)
    - [开发 iOS](#%E5%BC%80%E5%8F%91-ios)
    - [推荐网站](#%E6%8E%A8%E8%8D%90%E7%BD%91%E7%AB%99)
  - [基础](#%E5%9F%BA%E7%A1%80)
    - [元组](#%E5%85%83%E7%BB%84)
    - [可选项展开](#%E5%8F%AF%E9%80%89%E9%A1%B9%E5%B1%95%E5%BC%80)
    - [区间`...`](#%E5%8C%BA%E9%97%B4)
    - [字符串](#%E5%AD%97%E7%AC%A6%E4%B8%B2)
    - [函数](#%E5%87%BD%E6%95%B0)
      - [使用可变参数`...`](#%E4%BD%BF%E7%94%A8%E5%8F%AF%E5%8F%98%E5%8F%82%E6%95%B0)
      - [默认参数](#%E9%BB%98%E8%AE%A4%E5%8F%82%E6%95%B0)
  - [集合](#%E9%9B%86%E5%90%88)
    - [数组](#%E6%95%B0%E7%BB%84)
    - [集合](#%E9%9B%86%E5%90%88-1)
    - [字典](#%E5%AD%97%E5%85%B8)
  - [控制流](#%E6%8E%A7%E5%88%B6%E6%B5%81)
    - [`for..in`](#forin)
    - [`switch`](#switch)
      - [区间匹配](#%E5%8C%BA%E9%97%B4%E5%8C%B9%E9%85%8D)
      - [结合元组](#%E7%BB%93%E5%90%88%E5%85%83%E7%BB%84)
      - [值绑定](#%E5%80%BC%E7%BB%91%E5%AE%9A)
      - [where](#where)
    - [`guard`](#guard)
  - [闭包`closures`](#%E9%97%AD%E5%8C%85closures)
    - [闭包表达式](#%E9%97%AD%E5%8C%85%E8%A1%A8%E8%BE%BE%E5%BC%8F)
    - [尾随闭包](#%E5%B0%BE%E9%9A%8F%E9%97%AD%E5%8C%85)
    - [自动闭包`@autoclosure`](#%E8%87%AA%E5%8A%A8%E9%97%AD%E5%8C%85autoclosure)
  - [类和结构体`struct/class`](#%E7%B1%BB%E5%92%8C%E7%BB%93%E6%9E%84%E4%BD%93structclass)
    - [延迟存储属性`lazy`](#%E5%BB%B6%E8%BF%9F%E5%AD%98%E5%82%A8%E5%B1%9E%E6%80%A7lazy)
    - [计算属性`get/set`](#%E8%AE%A1%E7%AE%97%E5%B1%9E%E6%80%A7getset)
    - [只读属性](#%E5%8F%AA%E8%AF%BB%E5%B1%9E%E6%80%A7)
    - [属性观察者`willSet/didSet`](#%E5%B1%9E%E6%80%A7%E8%A7%82%E5%AF%9F%E8%80%85willsetdidset)
    - [类型属性`static`](#%E7%B1%BB%E5%9E%8B%E5%B1%9E%E6%80%A7static)
    - [实例方法/类型方法](#%E5%AE%9E%E4%BE%8B%E6%96%B9%E6%B3%95%E7%B1%BB%E5%9E%8B%E6%96%B9%E6%B3%95)
    - [下标`subscript`](#%E4%B8%8B%E6%A0%87subscript)
    - [类的继承](#%E7%B1%BB%E7%9A%84%E7%BB%A7%E6%89%BF)
    - [初始化`init`](#%E5%88%9D%E5%A7%8B%E5%8C%96init)
    - [反初始化`deinit`](#%E5%8F%8D%E5%88%9D%E5%A7%8B%E5%8C%96deinit)
  - [枚举`enum`](#%E6%9E%9A%E4%B8%BEenum)
  - [可选链](#%E5%8F%AF%E9%80%89%E9%93%BE)
  - [协议`protocol`](#%E5%8D%8F%E8%AE%AEprotocol)
    - [初始化器要求](#%E5%88%9D%E5%A7%8B%E5%8C%96%E5%99%A8%E8%A6%81%E6%B1%82)
    - [将协议作为类型](#%E5%B0%86%E5%8D%8F%E8%AE%AE%E4%BD%9C%E4%B8%BA%E7%B1%BB%E5%9E%8B)
    - [委托`delegate`](#%E5%A7%94%E6%89%98delegate)
  - [扩展`extension`](#%E6%89%A9%E5%B1%95extension)
  - [错误处理](#%E9%94%99%E8%AF%AF%E5%A4%84%E7%90%86)
  - [值类型和引用类型](#%E5%80%BC%E7%B1%BB%E5%9E%8B%E5%92%8C%E5%BC%95%E7%94%A8%E7%B1%BB%E5%9E%8B)
  - [内存管理](#%E5%86%85%E5%AD%98%E7%AE%A1%E7%90%86)
    - [引用计数](#%E5%BC%95%E7%94%A8%E8%AE%A1%E6%95%B0)
    - [引用循环](#%E5%BC%95%E7%94%A8%E5%BE%AA%E7%8E%AF)
      - [对象相互引用](#%E5%AF%B9%E8%B1%A1%E7%9B%B8%E4%BA%92%E5%BC%95%E7%94%A8)
      - [闭包](#%E9%97%AD%E5%8C%85)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Swift 入坑记录

> 仅记录一些个人觉得作为 Swift 初学者需要注意的，或者容易遗忘的知识点

### 资料

#### Swift 语言

- [Swift 中文文档](https://www.cnswift.org/)
- [中文版 Apple 官方 Swift 教程《The Swift Programming Language》](https://swiftgg.gitbook.io/swift/)
- [Swift 官方文档](https://docs.swift.org/swift-book/)
- [速览：Guide Tour - Playground](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.playground.zip)
- [速览：Standard Library - Playground](https://developer.apple.com/sample-code/swift/downloads/Standard-Library.zip)
- [其他官方资源](https://developer.apple.com/swift/resources/)
- [Swift Algorithm Club](https://github.com/raywenderlich/swift-algorithm-club)
- [Swift 编码规范](https://github.com/Artwalk/swift-style-guide/blob/master/README_CN.md)

#### 开发 iOS

- [Developing iOS 11 Apps with Swift](https://www.bilibili.com/video/av16339375)
- [Developing iOS 11 Apps with Swift 字幕翻译](https://github.com/ApolloZhu/Developing-iOS-11-Apps-with-Swift)
- [iOS 各组件入门](https://www.ioscreator.com/)
- How To Make a Gesture-Driven To-Do List App Like Clear in Swift
  - [Part 1/2](https://www.raywenderlich.com/77974/making-a-gesture-driven-to-do-list-app-like-clear-in-swift-part-1)
  - [Part 2/2](https://www.raywenderlich.com/77975/making-a-gesture-driven-to-do-list-app-like-clear-in-swift-part-2)
- Core Graphics Tutorial
  - [Part 1/3](https://www.raywenderlich.com/162315/core-graphics-tutorial-part-1-getting-started)
  - [Part 2/3](https://www.raywenderlich.com/162313/core-graphics-tutorial-part-2-gradients-contexts)
  - [Part 3/3](https://www.raywenderlich.com/167352/core-graphics-tutorial-part-3-patterns-playgrounds)

基础 UI 和布局

- [UIView Fundamentals](https://www.weheartswift.com/uiview-fundamentals/)
- [Bezier Paths and Gesture Recognizers](https://www.weheartswift.com/bezier-paths-gesture-recognizers/)
- [Auto Layout 101](https://www.weheartswift.com/auto-layout-101/)

#### 推荐网站

- [raywenderlich](https://www.raywenderlich.com)

### 基础

> **Swift 中所有的基本类型——整数、浮点数、布尔量、字符串、数组和字典，都是值类型，并且都以结构体的形式在后台实现**
>
> **Swift 中所有的结构体和枚举都是值类型，这意味着你所创建的任何结构体和枚举实例，和实例作为属性所包含的任意值类型，在代码传递中总是被拷贝的**
>
> **Swift 中的类是引用类型**

Double代表 64 位的浮点数，Float 代表 32 位的浮点数。
如果没有指明，Swift 在推断浮点值的时候始终会选择 Double

- [What is the difference between Int and Int32 in Swift?](https://stackoverflow.com/questions/27440100/what-is-the-difference-between-int-and-int32-in-swift)

#### 元组

元组内的值可以是任何类型，而且可以不必是同一类型
元组可解构，并且可以利用数字索引、命名索引来访问其中的元素

```Swift
let exampleTuple = (1, "1")
let (num, str) = exampleTuple
// exampleTuple.0 -> 1
// exampleTuple.1 -> "1"

let exampleTuple2 = (num: 1, str: "1")
exampleTuple2.num // 1
exampleTuple2.str // "1"
```

拥有同样数量的元组可以进行比较（元组内元素数 < 7）：

```Swift
(1, "zebra") < (2, "apple")   // true because 1 is less than 2
```

#### 可选项展开

```Swift
var number: Int? = 1

// 强制展开
if number != nil {
  print("number is \(number!)")
}

// 绑定展开
if let num = number {
  print("number is \(num)")
}

// 利用合并空值运算符展开
let defaultNumber: Int = 0
let num = number ?? defaultNumber

// 隐式展开
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // requires an exclamation mark

let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // no need for an exclamation mark
```

#### 区间`...`

```Swift
// 闭区间
1...5

// 左闭右开
1..<5

// 单侧区间
1... // 可无限遍历
...1 // 起点位置，故不可遍历

for index in 1... {
  print(index)
  if index > 10 {
    break
  }
}
```

#### 字符串

```Swift
var str: String = String()
str.isEmpty // 检查字符串是否是空

String(repeating: str, count: 20) // 字符串的 repeat 操作

/* 遍历字符串中的每一个 Character */
for character in str {
  print(character)
}

/* 将字符串转换为数组 */
Array(str)

/* 获取字符串长度（Character 数量） */
str.count

/* 字符串索引
使用 startIndex 属性来访问 String 中第一个 Character 的位置
endIndex 属性就是 String 中最后一个字符后的位置
使用 index(before:) 和 index(after:) 方法来访问给定索引的前后
注意，string.startIndex, string.endIndex. string.index(..) 返回的是 String.index 类型，
不能直接使用 string[int] 来获取某个位置上的 Character
*/
let greeting = "Guten Tag!"
greeting[greeting.startIndex] // G
greeting[greeting.index(before: greeting.endIndex)] // !
greeting[greeting.index(after: greeting.startIndex)] // u
let index = greeting.index(greeting.startIndex, offsetBy: 7)
greeting[index] // a
greeting[greeting.startIndex..<greeting.endIndex] // Guten Tag!
greeting[greeting.startIndex...greeting.endIndex] // ERROR


/* indices 属性可获取字符串中独立字符的索引范围 Range */
for index in greeting.characters.indices {
  print("\(greeting[index]) ", terminator: "")
}
// Prints "G u t e n   T a g ! "
for index in greeting.indices {}


/* 字符串修改
在特定位置插入字符 insert(_:at:)
在特定位置插入字符串 insert(contentsOf:at:)
*/
var welcome = "hello"
welcome.insert("!", at: welcome.endIndex) // 注意，只能插入 Character
// welcome now equals "hello!"

welcome.insert(contentsOf:" there".characters, at: welcome.index(before: welcome.endIndex))
// welcome now equals "hello there!"

/* 子字符串
从字符串中截取得到的子字符串，其类型位 Substring，而不是 String
每一个子字符串都有一块内存区域用来保存组成子字符串的字符。
字符串与子字符串的不同之处在于，作为性能上的优化，子字符串可以重用一部分用来保存原字符串的内存，或者是用来保存其他子字符串的内存。
*/

/* 前缀和后缀
检查字符串是否拥有特定的字符串前缀：hasPrefix(_:)
检查字符串是否拥有特定的字符串后缀：hasSuffix(_:)
*/
```

```Swift
// 字符串的索引不能超过其自身范围
string.index(string.startIndex, offsetBy: -1) // Error!
string.index(string.endIndex, offsetBy: 1) // Error!

// 字符串通过索引范围获取到的类型为 SubString
let subStr = string[string.startIndex..<string.endIndex]
type(of: subStr)  // SubString

let strIndex = string.startIndex
strIndex.encodedOffset // 将 Index 转为 Int
```

#### 函数

##### 使用可变参数`...`

```Swift
func add(_ nums: Int...) -> Int {
  return nums.reduce(0, {(x, y) in x + y})
}

add(1,2,3,4,5) // 15
```

##### 默认参数

```Swift
func someFunction(parameterWithDefault: Int = 12) {
  // In the function body, if no arguments are passed to the function
  // call, the value of parameterWithDefault is 12.
}
someFunction(parameterWithDefault: 6) // parameterWithDefault is 6
someFunction() // parameterWithDefault is 12
```

### 集合

Swift 中有三种集合：数组 Array，集合 Set，字典 Dictionary

注意，和 JavaScript 中不同的是，如何把集合复制给一个常量，则再也不能改变其中的元素，因为它们都是值引用的。

```Swift
// 初始化
var array: Array<String>()
// 等价 var array: [String]()
var arr = Array(repeating: "a", count: 3) // ["a", "a", "a"]

var set = Set<String>()
var dictionary = Dictionary<String, Int>()
// 等价 var dictionary = [String: Int]()
```

#### 数组

```Swift
// 数组常用 API
arr.count
arr.isEmpty
arr.append()
arr.insert(_:at:)
arr.remove(at:)
arr.removeLast() // 直接删除最后一位

for value in arr {}
for (index, value) in arr.enumerated() {}

// 交互两个位置上的值
var numbers = [1,2,3,4,5]
numbers.swapAt(0,1)
numbers // [2, 1, 3, 4, 5]

// 获取范围索引
numbers[0..<4]

// 组合成为 String
// 只有当数组元素为 String/Character 类型时，才能直接转换为 String
// -> How do I convert a Swift Array to a String?
// -> https://stackoverflow.com/questions/25827033/how-do-i-convert-a-swift-array-to-a-string

let charArr: [Character] = ["a", "b"]
String(charArr) // "ab"

let intArr: [Int] = [1, 2]
var int2StrArr = intArr.flatMap { String($0) }
print(int2StrArr) // ["1", "2"]
String(int2StrArr) // "12"

// 查找第一个符合条件的值
arr.first(where:)
```

#### 集合

为了能让类型储存在合集当中，它必须是可哈希的 —— 即类型必须提供计算它自身哈希值的方法。
哈希值是 Int 值且所有的对比起来相等的对象都相同，比如`a == b`，它遵循`a.hashValue == b.hashValue`。

```Swift
// 集合常用 API
set.count
set.isEmpty
set.insert(_:)
set.remove(_:)
set.contains(_:)

for value in set {}
// Set类型是无序的。要以特定的顺序遍历合集的值，使用 sorted()方法，
// 它把合集的元素作为使用 < 运算符排序了的数组返回。
for value in set.sorted() {}

// 集合的合集操作
// 略

// 可以 filter
let set: Set = [1,2,3,4,5]
let filteredSet = set.filter { $0 % 2 == 0 }
type(of: filteredSet) // Set<Int>.Type
filteredSet // {2, 4}
```

#### 字典

```Swift
// 常用 API
dict.count
dict.isEmpty
dict.updateValue(_:forKey:) // 更新之后返回 Optional 类型的旧的值（如果失败则是 nil）
dict.removeValue(forKey:) // 移除后返回 Optional 类型的 value 的值
dict[key, default: defaultValue] // 取值时提供默认值

for (key, value) in dict {}
for key in dict.keys {}
for value in dict.values {}

let names = ["Cagney", "Lacey", "Bensen"]
let dict = Dictionary(uniqueKeysWithValues: zip(1..., names)) // [2: "Lacey", 3: "Bensen", 1: "Cagney"]
dict[2] // Lacey

// 字典合并
var dictionary = ["a": 1, "b": 2]

// Keeping existing value for key "a":
dictionary.merge(["a": 3, "c": 4]) { (current, _) in current }
// ["b": 2, "a": 1, "c": 4]

// Taking the new value for key "a":
dictionary.merge(["a": 5, "d": 6]) { (_, new) in new }
// ["b": 2, "a": 5, "c": 4, "d": 6]

// 可以在获取值时提供默认值
dict[4, default: "(unknown)"]

// 还可以进行 filter 和 map
let filtered = dict.filter {
  $0.key % 2 == 0
}
type(of: filtered) // Dictionary<Int, String>.Type

let mapped = dict.mapValues { value in
  value.uppercased()
}
mapped // 返回一个新的字典
```

注意：Swift 的`Dictionary`类型是无序的。要以特定的顺序遍历字典的键或值，使用键或值的`sorted()`方法。

### 控制流

```Swift
while condition {
  code
}

repeat {
  code
} while condition

if condition1 {
  code1
} else if condition2 {
  code2
} else {
  code3
}

// 每一个 case 的函数体必须包含至少一个可执行的语句
switch value {
  case value 1:
    respond to value 1
  case value 2, value 3:
    respond to value 2 or 3
  default:
    otherwise, do something else
}

// 使用 stride 进行遍历
// stride(from:to:by:)
let minuteInterval = 5
for tickMark in stride(from: 0, to: minutes, by: minuteInterval) {
  // render the tick mark every 5 minutes (0, 5, 10, 15 ... 45, 50, 55)
}
```

#### `for..in`

```Swift
// for _ in what where condition {}
for i in 0...10 where i % 2 == 0 {
  print(i)
}

// for (i1, i2...) in zip(sequence1, sequence2..) {}
let numbers = [1, 2, 3]
let letters = ["a", "b", "c"]
for (number, letter) in zip(numbers, letters) {
  print("number: \(number), letter: \(letter)")
}
```

#### `switch`

Swift 里的`switch`语句不会默认从每个情况的末尾贯穿到下一个情况里，整个`switch`语句会在匹配到第一个`switch`情况执行完毕之后退出，不再需要显式的`break`语句

##### 区间匹配

```Swift
let num = 10
switch num {
  case 1..<5:
    print("1 <= num < 5")
  case 5...:
    print("num >= 5")
}
```

##### 结合元组

```Swift
// 使用下划线 _ 可以匹配所有可能的值
let point = (1, 2)
// 会有限匹配到 (_, 2)，然后退出 switch 语句
switch point {
  case (_, 2):
    print("1")
  case (1, _):
    print("2")
  default:
    print("default")
}
```

##### 值绑定

```Swift
let anotherPoint = (2, 0)
switch anotherPoint {
  case (let x, 0):
    print("on the x-axis with an x value of \(x)")
  case (0, let y):
    print("on the y-axis with a y value of \(y)")
  case let (x, y):
    print("somewhere else at (\(x), \(y))")
}
// prints "on the x-axis with an x value of 2"
```

##### where

```Swift
// 使用 where 分句来检查额外的情况
let yetAnotherPoint = (1, -1)
switch yetAnotherPoint {
  case let (x, y) where x == y:
    print("(\(x), \(y)) is on the line x == y")
  case let (x, y) where x == -y:
    print("(\(x), \(y)) is on the line x == -y")
  case let (x, y):
    print("(\(x), \(y)) is just some arbitrary point")
}
prints "(1, -1) is on the line x == -y"
```

#### `guard`

`guard`语句和`if`类似，但是不会产生多层的嵌套。如果`guard`条件满足，则代码会继续正常向下执行

```Swift
func greeting(person: [String:String]) {
  guard let name = person["name"] else {
    return
  }
  print("Hello \(name)!")
}
```

### 闭包`closures`

> **闭包是引用类型**

#### 闭包表达式

```Swift
// 闭包表达式
{(parameters) -> (return type) in
  statements
}

// 例
reversedNames = names.sorted(by: { (s1: String, s2: String) -> Bool in return s1 > s2 } )
// 简写 -> 从语境中推断类型
reversedNames = names.sorted(by: { s1, s2 in return s1 > s2 } )
// 简写 -> 从单表达式闭包隐式返回
// sorted(by:) 方法的第二个实际参数的函数类型已经明确必须通过闭包返回一个 Bool 值。
// 因为闭包的结构包涵返回 Bool 值的单一表达式 (s1 > s2)，因此没有歧义，并且 return 关键字能够被省略
reversedNames = names.sorted(by: { s1, s2 in s1 > s2 } )
```

#### 尾随闭包

当闭包表达式比较长时，可通过尾随闭包来提高代码可读性

```Swift
reversedNames = names.sorted() {
  (s1: String, s2: String) -> Bool in return s1 > s2
}

// 如果闭包表达式作为函数的唯一实际参数传入，又使用了尾随闭包的语法，则可以省略函数名后边的圆括号
reversedNames = names.sorted { $0 > $1 }
```

#### 自动闭包`@autoclosure`

- [How to use Swift @autoclosure](https://stackoverflow.com/questions/24102617/how-to-use-swift-autoclosure)

使用`@autoclosure`后，在使用匿名函数时，可以省略`{}`

```Swift
func f(pred: () -> Bool) {
  if pred() {
    print("It's true")
  }
}

// 普通调用
f(pred: {2 > 1}) // "It's true"

// 将原函数修改为支持自动闭包
func f(pred: @autoclosure () -> Bool) {
  if pred() {
    print("It's true")
  }
}
// 调用
f(pred: 2 > 1)
```

### 类和结构体`struct/class`

类和结构体非常类型，但有如下不同：

- 类可继承，结构体不能继承
- 类是引用类型，结构体是值类型
- 反初始化器允许一个类实例释放任何其所被分配的资源
- 引用计数允许不止一个对类实例的引用；结构体在代码中通过复制来传递，并且并不会使用引用计数
- 所有的结构体都有一个自动生成的成员初始化器，类需要手动创建，或者使用默认初始化
- **结构体是值类型，默认情况下，值类型属性不能被自身的实例方法修改**
- 类的实例可以使用`===`比较符来判断其引用是否相等

```Swift
class TestClass {
  // 将属性默认初始化
  var name: String = "ecmadao"
  var age: Int = 25
}
var testClass
testClass = TestClass() // OK
testClass = TestClass(name: "27") // ERROR

struct TestStruct {
  // 将属性默认初始化
  var name: String = "ecmadao"
  var age: Int = 25
}
var testStruct
testStruct = TestStruct() // OK
testStruct = TestStruct(name: "27") // OK

// 类是引用类型，结构体是值类型
let testClass2 = TestClass() // OK
testClass2.name = "27" // OK

let testStruct2 = TestStruct() // OK
testStruct2.name = "27" // ERROR
```

#### 延迟存储属性`lazy`

一个属性的初始值可能依赖于某些外部因素，而这些外部因素的值只有在实例的初始化完成后才能得到。此时可以使用延迟储存属性

```Swift
class Example {
  var arr: [String] = ["1", "2", "3"]

  // arr 只有在初始化之后也能够获取到，因此必须使用延迟储存属性
  lazy arrLength: Int = arr.count
}
```

#### 计算属性`get/set`

```Swift
class ExampleArea {
  var width: Int = 9
  var height: Int = 1

  var info: (width: Int, height: Int) {
    get {
      return (width, height)
    }
    set(newArea) {
      width = newArea.width
      height = newArea.height
    }
  }
}

let exampleArea = ExampleArea()
exampleArea.info // (width 9, height 1)
exampleArea.info = (width: 10, height: 100)
```

#### 只读属性

```Swift
class ExampleArea {
  var width: Int = 9
  var height: Int = 1

  // 计算属性去除 setter，并简写
  var info: (width: Int, height: Int) {
    return (width, height)
  }
}

let exampleArea = ExampleArea()
exampleArea.info // (width 9, height 1)
exampleArea.info = (width: 10, height: 100) // ERROR
```

#### 属性观察者`willSet/didSet`

属性观察者会观察并对属性值的变化做出回应。当属性的值被设置时，属性观察者都会被调用，即使这个值与该属性当前的值相同。

- `willSet`会在该值被存储之前被调用
- `didSet`会在一个新值被存储后被调用

```Swift
class Counter {
  var count: Int = 0 {
    willSet {
      print("Will set: \(newValue)")
    }
    didSet {
      print("Set done. Old value is \(oldValue)")
    }
  }
}

let counter = Counter()
counter.count += 1
// Will set: 1
// Set done. Old value is 0
```

#### 类型属性`static`

使用`static`定义类型属性。类型属性只能被类/结构体直接调用，而不能被其实例调用

```Swift
struct Example {
  static var name: String = "27"
}
Example.name // OK
```

#### 实例方法/类型方法

```Swift
class ExampleClass {
  var name: String = "123"
  var count: Int = 0

  // 实例方法
  func counting() {
    count += 1
  }

  // 类型方法
  static func getName() {
    return name
  }
}

struct ExampleStruct {
  var count: Int = 0

  // ERROR: mark method 'mutating' to make 'self' mutable
  // 结构体的值类型属性不能被自身的实例方法修改，需要使用 mutating 关键字
  func counting() {
    count += 1
  }

  // 变异方法
  mutating func counting() {
    count += 1
  }
}
```

#### 下标`subscript`

类、结构体和枚举可以定义下标，它可以作为访问集合、列表或序列成员元素的快捷方式

```Swift
// 类似于计算属性，通过 subscript 关键字定义
subscript(index: Int) -> Int {
  get {
    // return an appropriate subscript value here
  }
  set(newValue) {
    // perform a suitable setting action here
  }
}

// Example
struct Matrix {
  let rows: Int, columns: Int
  var grid: [Double]

  init(rows: Int, columns: Int) {
    self.rows = rows
    self.columns = columns
    grid = Array(repeating: 0.0, count: rows * columns)
  }

  func indexIsValid(row: Int, column: Int) -> Bool {
    return row >= 0 && row < rows && column >= 0 && column < columns
  }

  subscript(row: Int, column: Int) -> Double {
    get {
      assert(indexIsValid(row: row, column: column), "Index out of range")
      return grid[(row * columns) + column]
    }
    set {
      assert(indexIsValid(row: row, column: column), "Index out of range")
      grid[(row * columns) + column] = newValue
    }
  }
}

var matrix = Matrix(rows: 2, columns: 2)
matrix[0, 1] = 1.5
```

#### 类的继承

```Swift
class SuperClass {
  var someProperty: Int = 0

  func someMethod() {}

  // 通过 fianl 可以禁止重写
  fianl func methodCanNotOverride() -> Int {
    return 1
  }
}

class SubClass: SuperClass {
  // 重写
  override func someMethod() {
    // 可通过 super.someMethod() 调用父类方法
  }

  // ERROR
  override func methodCanNotOverride() {}
}
```

#### 初始化`init`

当你给一个存储属性分配默认值，或者在一个初始化器里设置它的初始值的时候，属性的值就会被直接设置，*不会调用任何属性监听器*。

```Swift
class ExampleClass {
  var name = String() {
    didSet {
      print("name setted")
    }
  }
  var age: Int = 0
  // 可选属性类型，如果没有赋值，在初始化的时候会自动设置为 nil
  var gender: String?

  // 可以设置多个初始化
  init(name: String, age: Int) {
    self.name = name
    self.age = age
  }
  init(name: String) {
    self.name = name
  }
  init(age: Int) {
    self.age = age
  }
}

let exampleClass = ExampleClass(name: "27") // 初始化时不会触发属性监听
exampleClass.gender // nil

// convenience
// 类在初始化的时候，还没有值的属性必须明确的传入 init 函数中进行赋值
// 或者可以通过 convenience 关键字定义一个便捷方法
// What is the difference between convenience init vs init in swift, explicit examples better
// -> https://stackoverflow.com/questions/40093484/what-is-the-difference-between-convenience-init-vs-init-in-swift-explicit-examp
class Example {
  var name: String
  var age: Int
  var gender: String

  init(name: String, age: String, gender: String) {
    self.name = name
    self.age = age
    self.gender = gender
  }

  convenience init(name: String) {
    self.init(name, age: 1, gender: "male")
  }
}
```

```Swift
// 可失败的初始化器
struct Animal {
  let species: String
  init?(species: String) {
    if species.isEmpty { return nil }
    self.species = species
  }
}

var animal = Animal(species: "") // nil
```

```Swift
// 通过闭包和函数来设置属性的默认值

class SomeClass {
  // 闭包花括号的结尾跟一个没有参数的圆括号
  // 即表明，在初始化的时候，立即执行闭包
  let someProperty: SomeType = {
    // create a default value for someProperty inside this closure
    // someValue must be of the same type as SomeType
    return someValue
  }()
}
```

#### 反初始化`deinit`

在类实例被释放的时候，反初始化器就会立即被调用。反初始化器不接收任何形式参数，并且不需要写圆括号。

- 反初始化器只在类类型中有效，每个类当中只能有一个反初始化器
- 反初始化器会在实例被释放之前自动被调用
- 不能自行调用反初始化器
- 父类的反初始化器可以被子类继承，并且子类的反初始化器实现结束之后父类的反初始化器会被调用
- 不论子类有没有反初始化器，父类的反初始化器总会被调用

```Swift
class Example {
  deinit {
    // 清理工作
  }
}
```

### 枚举`enum`

枚举为一组相关值定义了一个通用类型

```Swift
/*
通过 enum 关键字来定义枚举
case 后跟随的是枚举的成员
*/
enum CompassPoint {
  case north
  case south
  case east
  case west
}

var directionToHead = CompassPoint.west
// 初始化之后，可以直接通过 . 语法来改变枚举成员
directionToHead = .south

// switch 语句可以用来遍历枚举值
switch directionToHead {
  case .north:
    print("Is north")
  case .south:
    print("Is south")
  case .east:
    print("Is east")
  default:
    print("Others")
}
```

注意，当判断一个枚举成员时，`switch`语句要么覆盖了所有的枚举成员，要么提供一个`default`判断。
要求覆盖所有枚举成员是因为这样可以保证枚举成员不会意外的被漏掉。

```Swift
// 枚举成员可以用**相同类型**的默认值预先填充（称为原始值）
enum AlarmClock: String {
  case morning = "08:00"
  case noon = "12:00"
  case night = "21:00"
}

// 在没有显示赋值时，枚举会给各枚举成员隐式的分配相同类型的原始值
enum CompassPoint: Int {
  case north = 1
  case south // 将会被赋予 2 的原始值
  case east // rawValue -> 3
  case west // rawValue -> 4
}
// 通过 rawValue 属性来访问原始值
var directionToHead = CompassPoint.west // "west"
directionToHead.rawValue // 4

// 从原始值来初始化
// 继续利用上面的 CompassPoint 枚举，第一个 north 的原始值是 1，从它之后，各个枚举成员的原始值会被隐式赋予，并逐个增加 1

// 指定初始化原始值是 3 的枚举成员。
// 需要注意的是，当传入的 rawValue 在枚举中不存在时，会返回 nil，因此，通过这种方式，返回的是 Optional 类型的值
directionToHead = CompassPoint(rawValue: 3)! // 强制展开
directionToHead == CompassPoint.west // true

if let direction = CompassPoint(rawValue: 3) {}

// will print ERROR
if let direction = CompassPoint(rawValue: 10) {
  // do something
} else {
  print("ERROR")
}

// 枚举内的各枚举成员可以是不同类型，此时枚举本身定义时不能指定返回的类型
enum Barcode {
  case upc(Int, Int, Int, Int)
  case qrCode(String)
}
var barcode = Barcode.qrCode("100")

switch productBarcode {
case .upc(let numberSystem, let manufacturer, let product, let check):
    print("UPC: \(numberSystem), \(manufacturer), \(product), \(check).")
case .qrCode(let productCode):
    print("QR code: \(productCode).")
}
// Prints "QR code: 100."


// 但是，在没有指定枚举返回的类型时，不能直接给枚举成员赋值
enum Rank {
  // error: enum case cannot have a raw value if the enum does not have a raw type
  case ace = 1
  case face(String)
  case numeric(pipsCount: Int)
}

// 在枚举内可以定义方法
enum WeekDay: String {
  case Monday
  case Tuesday
  func day() -> String { return self.rawValue }
}
print(WeekDay.Monday.day()) // prints Monday
```

### 可选链

可选链是一个调用和查询可选属性、方法和下标的过程，当多个可选属性连续的出现时使用尤为方便，可以避免强制展开带来的错误、太多的 if 嵌套，并在某一环节展开失败时自动返回 nil

```Swift
class A {
  var b: B?
}

class B {
  var c: Int = 1
}

var example = A()
if let c = example.b?.c {
  print("c = \(c)")
} else {
  print("has no c")
}
// has no c
```

### 协议`protocol`

协议要求所有遵循该协议的类型提供特定名字和类型的实例属性或类型属

```Swift
/*
SomeProtocol 要求，所有采纳该协议的类或结构体，都必须实现：
1. 名为 mustBeSettable 的可读写属性
2. 名为 doesNotNeedToBeSettable 的可读属性（是否可写无要求）
3. 名为 someTypeMethod 的方法，并且返回指定的类型
4. 名为 someTypeProperty 的可读写的类型属性
*/
protocol SomeProtocol {
  var mustBeSettable: Int { get set }
  var doesNotNeedToBeSettable: Int { get }
  var func someTypeMethod() -> someType
  static var someTypeProperty: Int { get set }
}

// 结构体采纳多个协议
struct SomeStructure: FirstProtocol, AnotherProtocol {
  // structure definition goes here
}
// 类继承某父类，并采纳多个协议（继承先写在前面）
class SomeClass: SomeSuperclass, FirstProtocol, AnotherProtocol {
  // class definition goes here
}

// 通过添加 AnyObject 关键字到协议的继承列表，你就可以限制协议只能被类类型采纳（并且不是结构体或者枚举）
protocol SomeClassOnlyProtocol: AnyObject, SomeInheritedProtocol {
  // class-only protocol definition goes here
}
```

#### 初始化器要求

协议可以要求遵循协议的类型实现合法的初始化器

```Swift
protocol SomeProtocol {
  init(someParameter: Int)
}

// 在实现协议要求的初始化器时，必须使用 require 关键字
class SomeClass: SomeProtocol {
  required init(someParameter: Int) {
    // initializer implementation goes here
  }
}

// 如果一个子类重写了父类指定的初始化器，而父类遵循了协议实现了初始化器要求，
// 那么就要为这个初始化器的实现添加 required 和 override 两个修饰符
class SomeSubClass: SomeClass, SomeProtocol {
  // "required" from SomeProtocol conformance; "override" from SomeSuperClass
  required override init(someParameter: Int) {
    // initializer implementation goes here
  }
}
```

#### 将协议作为类型

由于协议也是个类型，因此协议可以：

1. 在函数、方法或者初始化器里作为形式参数类型或者返回类型
2. 作为常量、变量或者属性的类型
3. 作为数组、字典或者其他存储器的元素的类型

```Swift
protocol SomeProtocol {
  init(someParameter: Int)
}

class SomeClass {
  // 要求属性必须是采纳了 SomeProtocol 协议的实例
  var someTypeProperty: SomeProtocol?
}

class SomeClassExample: SomeProtocol {
  required init(someParameter: Int) {}
  var someTypeProperty: Int = 100
}
let example: SomeProtocol = SomeClassExample(someParameter: 1) // OK
example.someTypeProperty // ERROR, 因为 example 是 SomeProtocol 类型的 Protocol，并没有把 SomeClassExample 独有的 someTypeProperty 传递过去
```

#### 委托`delegate`

委托是利用协议实现的一种设计模式，可戳：

- [Delegate vs Protocol](https://stackoverflow.com/questions/6361958/delegate-vs-protocol)
- [Difference between protocol and delegates?](https://stackoverflow.com/questions/5431413/difference-between-protocol-and-delegates)
- [Quick Guide to Swift Delegates](https://useyourloaf.com/blog/quick-guide-to-swift-delegates/)

### 扩展`extension`

```Swift
extension SomeType {
  // new functionality to add to SomeType goes here
}
```

扩展可以使已有的类型遵循一个或多个协议。在这种情况下，协议名的书写方式与类或结构体完全一样

extension SomeType: SomeProtocol, AnotherProtocol {
  // implementation of protocol requirements goes here
}

```Swift
// 扩展 Dictionary，增加一个只读属性，在字典只有一个键值对的时候获取其键
// 可以通过 self 获取到自身
extension Dictionary {
  var oneAndOnlyKey: Key? {
    get {
      if self.count >= 2 {
        return nil
      }
      return self.keys.first
    }
  }
}
```

### 错误处理

```Swift
// 定义一个可能会抛出错误的方法
func exampleFunc() throws -> String {}

// do-catch
do {
  try expression
  statements
} catch pattern 1 {
  statements
} catch pattern 2 where condition {
  statements
}

do {
  try exampleFunc()
} catch let err {
  print(err)
}

// try? 语句，把结果转为可选项
// 如果错误抛出，则返回 nil，否则正常运行
let result = try? exampleFunc() // result 的类型应该是 Option(String)

// try! 语句，强制展开
// 如果有错，则抛出异常
let result = try! exampleFunc()
```

定义`defer`语句，可以在代码离开当前代码块前执行预定义的内容，可用于抛出错误时进行清理工作

```Swift
// 预先在 defer 中定义了 close，因此当 processFile 函数执行完毕之后，
// 不论是否有错误抛出，都会执行 close 操作
func processFile(filename: String) throws {
  if exists(filename) {
    let file = open(filename)
    defer {
      close(file)
    }
    while let line = try file.readline() {
      // Work with the file.
    }
    // close(file) is called here, at the end of the scope.
  }
}
```

更多资料：

- [Magical Error Handling in Swift](https://www.raywenderlich.com/130197/magical-error-handling-swift)
- [Generate your own Error code in swift 3](https://stackoverflow.com/questions/40671991/generate-your-own-error-code-in-swift-3)

### 值类型和引用类型

- [Reference vs Value Types in Swift: Part 1/2](https://www.raywenderlich.com/112027/reference-value-types-in-swift-part-1)
- [Reference vs Value Types in Swift: Part 2/2](https://www.raywenderlich.com/112029/reference-value-types-in-swift-part-2)

在 Swift 中，大部分类型都是值传递，例如`String`，`Array`，`Set`，`Dictionary`，`struct`；而类`class`则是引用传递。
什么时候使用值传递、引用传递，官方给出的建议如下：

如下情况时使用值传递：

- 想要利用`==`来比较实例对象
- 想要让复制的对象有自己独立的状态
- 会在多线程使用时

而如下情况则可以使用引用传递：

- 想要利用`==`来比较实例对象的指针
- 想创建可以被多个地方共享状态的对象

当面临复杂情况，比如值传递、引用传递的对象相互嵌套时：

```Swift
class Person {
  var name: String
  init(name: String) {
    self.name = name
  }
}

// 在值传递的结构体中加入引用传递的属性
struct Bill {
  let amount: Float
  // 引用传递
  let billedTo: Person

  init(amount: Float, billedTo: Person) {
    self.amount = amount
    // Create a new Person reference from the parameter
    self.billedTo = Person(name: billedTo.name)
  }
}
extension Bill: Equatable { }
func ==(lhs: Bill, rhs: Bill) -> Bool {
  return lhs.amount == rhs.amount && lhs.billedTo === rhs.billedTo
}

let billPayer = Person(name: "Robert")

var bill1 = Bill(amount: 1, billedTo: billPayer)
var bill2 = bill1

// 虽然 bill2 是新复制出的值传递数据，但它 billedTo 属性和 bill1 的 billedTo 属性引用的还是同一个对象
bill1.billedTo.name = "ecmadao"
bill1.billedTo.name // ecmadao
bill2.billedTo.name // ecmadao
bill1 == bill2 // true
```

可以通过自带的`isKnownUniquelyReferenced`方法来检查对象是否只有唯一的引用：

```Swift
// isKnownUniquelyReferenced(&object: T)
var billPayer = Person(name: "Robert")
isKnownUniquelyReferenced(&billPayer) // true

var billPayer2 = billPayer
isKnownUniquelyReferenced(&billPayer) // false
isKnownUniquelyReferenced(&billPayer2) // false
```

### 内存管理

#### 引用计数

- [自动引用计数](https://www.cnswift.org/automatic-reference-counting)

#### 引用循环

##### 对象相互引用

当对象相互引用时会造成引用循环。当它们相互强引用时，就会使得涉及的对象无法释放，将一直占用内存

```Swift
class A {
  var b: B?

  deinit() {
    print("deinit of A")
  }
}

class B {
  var a: A?

  deinit() {
    print("deinit of B")
  }
}

var a: A? = A()
var b: B? = B()
a.b = b
b.a = a

// 当手动释放内存时，可以发现 deinit 不会被调用，即对象并没有被消除
a = nil
b = nil
```

为了避免这种情况，应该使用弱引用`weak`

```Swift
class A {
  weak var b: B?
}

class B {
  weak var a: A?
}
```

##### 闭包

在闭包中引用到的对象也可能会造成内存无法释放

```Swift
class ClosureExample {
  let name: String = "example"

  lazy var example: () -> String = {
    return "name: \(self.name)"
  }

  deinit {
    print("deinit of ClosureExample")
  }
}

var closureExample: ClosureExample? = ClosureExample()
print(closureExample!.example()) // name: example

closureExample = nil // 没有打印 deinit
```

类`ClosureExample`具有其强引用`example`闭包，而`example`闭包强引用了`self`，也就是该类自己，因此造成了强引用循环，使得内存无法被释放。但在这种情况下无法直接通过`weak`来转换为弱引用，因为`weak`只能作用在**引用类型**上，而不能作用于值类型，否则报错：`'weak' may only be applied to class and class-bound protocol types, not '() -> String'`

- [Why can the keyword “weak” only be applied to class and class-bound protocol types](https://stackoverflow.com/questions/38841127/why-can-the-keyword-weak-only-be-applied-to-class-and-class-bound-protocol-typ)

想要断开闭包内的引用循环，需要在闭包内加入一个声明，表示在销毁的时候不保留`self`对象：

```Swift
class ClosureExample {
  lazy var example: () -> String = {
    [unowned self] in
    return "name: \(self.name)"
  }
}
```
