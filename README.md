# Ofu

The  Ofu Programming Language.

What is Ofu? A Programming Language I want to make in 2 years. Well,maybe I finally turn this project to a `Toy Language`.And only for me.

Why you want to design the Ofu? Cause it's Coooool!!!

### Program Language might be use

`Python`

`C/C++`

`Objective Caml` (Still learning).



### Basic Knowledge

1. Lexer

2. Parser(Context-Free-Grammar)

   ```c
   int main(){
       int x = 0;//'int' 'x' '=' '0' ';'
       return x;//'return' 'x' ';'
   }
   ```

   

3. Checker

   -Name Checker.

   -Type rich programming.

   Scouse code is Abstract Syntax Tree. & Intermediate Representation. AST & IR

4.  Execution

   ​	-Compile :  Physical Machine

   ​			x86, arm, risc-v, mips, loongarch

   ​	-Interpreter

   ​			- Runtime

   			- Virtual Machine, VM  like Java

## design Ofu

1. Cooool Features
2. Not too useless (Works well at lest~)
3. Meaning



Features：

- Quick Interpreter (Python )
- Generate C code
  - ​	source code to come c 

How to Quick ? Lexer,run on AST. 

Parser Combinator is need.

Checker : By hand writing.

AST,IR is Intermediate, Core of the implementation of a language.

Generate C code  cover features of C.





## Ofu

I want Ofu is EZ to learning.

```c
int a, *b, **c;
```

I really don't like this 'thing'  in language . Yes ,Pointer!

#### Let's talk about pointer.

In C, you need to obey the `definition,use same to declaration `rule.

but in this case.

```c
typedef int(__stdcall*f[10])(int(*a)(int, int));
```

this rule is the worst to the code reader.

Turn this code to the Haskell code. It could be 

```haskell
Haskell:
f :: [(int->int->int)->int]
```

Haskell don't have the `definition,use same to declaration`rule,so it solved this big problem in C,Also in Rust. 

I know in Rust and C++,smart pointer is very great creation.

Like this 

```rust
use std::rc::Rc;
fn main() {
    let x = Rc::new("hello");
    println!("{:?}", x.chars());
}
```

In Rc. It's don't have chars() method. But we still can use chars(). Cause,Rc implement the Deref.

```rust
#[stable(feature = "rust1", since = "1.0.0")]
impl<T: ?Sized> Deref for Rc<T> {
    type Target = T;

    #[inline(always)]
    fn deref(&self) -> &T {
        &self.inner().value
    }
}
```

Like this 

```rust
#[lang = "deref"]
#[doc(alias = "*")]
#[doc(alias = "&*")]
#[stable(feature = "rust1", since = "1.0.0")]
pub trait Deref {
    /// The resulting type after dereferencing.
    #[stable(feature = "rust1", since = "1.0.0")]
    type Target: ?Sized;

    /// Dereferences the value.
    #[must_use]
    #[stable(feature = "rust1", since = "1.0.0")]
    fn deref(&self) -> &Self::Target;
}

#[lang = "deref_mut"]
#[doc(alias = "*")]
#[stable(feature = "rust1", since = "1.0.0")]
pub trait DerefMut: Deref {
    /// Mutably dereferences the value.
    #[stable(feature = "rust1", since = "1.0.0")]
    fn deref_mut(&mut self) -> &mut Self::Target;
}
```

Still learning this part.

A simple pointer error in C#

```c#
class PointBox
{
    public int Number { get; set; }
    public Point Point { get; set; }
}

var box = new PointBox() { Number = 1, Point = new Point { x = 1, y = 2 } };
box.Number += 3;//pass
box.Point.x = 5;//cann't pass
```

`Cannot modify the return value of 'box.Point.x' because it is not a variable`

The basically reason is the  struct different to class,so **Value Type** is different to **Reference Type**.

In C#,struct is value type,is to say it's not a pointer,and it can not inheritance from parent etc.

Maybe too difficult. I still learning this part in C#.  

So let's talk some thing about keyword 'const' . At lest ,const is inconvenience to me.

I use const to show some filed what the value don't want be change.  But sometimes we don't now the function will to do what. So we use the const at the function declaration.

so what is const use for? What the difference in next 3 lines?

```c++
int Add(const int a, const int b);
```



```c++
const int Add(const int a, const int b);
```



```c++
int Add(int a, int b);
```

For me const& and const* usually  to  decorate variable filed.

So in C++ use the const to decorate a type is not a good design for me.

## Next design step

AST design first.

Then Checker.



