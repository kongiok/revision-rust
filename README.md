# Rust Revision.  #

> 不逼自己，你都不知道自己這麼優秀。

藉由**高見龍**老師的協助，讓我能在Rust這條路上走的更遠。

##  Why Rust? ##

- 潮啊

*請原諒我目光短淺*

##  Fundamentals of Rust  ##

### Macro ###

```rust
  println!("Hello World");
```

- 帶有驚嘆號`!`的是巨集，不是函式

## Types ##

###  Numbers ###

```rust
let my_age:u8 = 21;
```

- **i32/u32** : i代表integer，u代表unsigned integer，unsigned integer不需要有一個位元放正負號。 
- **f32/f64** : 浮點數。

### String  ###

```rust
let something = "something";
```

- 單引號 : 是char型態。
- 雙引號 : 字串。

### Array ###

```rust
let list: [u8, 3] = [1,2,3];
```
- 要先定義**“多少內容”**
- 再定義“內容”
- 同型別 == 快速
```rust
println!("{}",list[1]);   // 2
```

**補充: list vs. array**
- array 必須放一樣型態
- list 並沒要求

### Tuple ###
```rust
let a_tuple: (bool, i8, char) = (true, 7, 'K');
println!("{}", a_tuple.2);  // k
```
- 可放不同型別的內容

### Variables & Constant ###
```rust
const CONSTANT: i8 = 8;
let variable: i8 = 7;
```
**常數**: 必須大寫& 必須指定型別。
**變數**: snake case 但沒那麼要求指定型別。


### Function  ###
```rust
fn is_a_function(i: i32, j: i32) -> i32 {
  i+j
}
fn is_a_null_return(i:i32, j:i32) -> () {
  println!("Not return.");
}
```
- `->`: 要求回傳的型別。
- `()`: Unit，在Rust中不回傳時的標記。

### Stack & Heap  ###
// 待補

### Ownership ###

- GC Pulse: 因Garbage Collector引起的延遲。
- Reference Count: 給予標記，如果到0就free他。

```rust
let a = 1;
a = 2;  // 跑不動。
```
為了減少Side Effect，變數預設是不能更動的。

如果要更動他，我們就要: 
```rust
let mut a = 1;
a = 2;
```

**Move——東西是你的了！**:

你制定了變數，而且你調用了這個變數。
這個時候，變數便不屬於你自己的了。

```rust
let a = 2;
let b = a;
println!("A = {}",a); //  Panic!
```

**Borrow——等會記得還我喔！**:
