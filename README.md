# C311 Functional Programming

[Fsharp Docs](https://fsharp.org/)

[F# For Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)

[F# Guide With Emphasis on Visual Studio Integrations](https://connelhooley.uk/blog/2017/04/10/f-sharp-guide)

[F# CheatSheet](http://dungpa.github.io/fsharp-cheatsheet/)

## Installation  

[Fsharp Install](https://fsharp.org/use/mac/)

[VS Code](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-vscode)

## Videos  

[Fsharp.org](https://fsharp.org/videos/1)  


**If Expressions**  

```fsharp  
module Helpers =
    let isConnel x =
        if x = "Connel" then
            "The value is Connel"
        else
            "The value is not Connel"
```  

**Functions**  

Commonly Known as Expressions 

```fsharp  
Let is SumEven num1 num2 =
    let sum = num1 + num2
        sum % 2 = 0 //default return value
``` 

**Immutability in F#**

objects can be made mutable with the `mutable` key word

*Example*  

```fsharp  
let mutableValue () = //returns the UNIT type
    let mutable x = 5 //creates a mutable variable and assigns '5'
        x <- 10 //assigns new values to mutable variables from 
        x   //returns x upon completion
```

**Unit-Type**  

```fsharp  
let return Unit () =  
    ()
```

described as an empty type. Returning nothing or disregarding the return value 

```fsharp   
let waitUntilEnter () = 
    ignore (Console.Readline())
```

*Ignore* ignores the return value of Readline and in this example above returns nothing

**Records**  

immutable *POCO* classes

```fsharp
open System

type Person = {
    name: string
    age: int
}

[<EntryPoint>]
let main argv = 
    let person1 = { name = "Connel"; age = 26 }
    let person2 = { name = "Hooley"; age = 26 }
    let person3 = { name = "Connel"; age = 26 }
    let isPerson1Person2 = person1 = person2
    let isPerson1Person3 = person1 = person3
    Console.WriteLine(isPerson1Person2) // prints false
    Console.WriteLine(isPerson1Person3) // prints true
    Console.WriteLine("Press enter to exit")
    let value = Console.ReadLine()
    0 // return an integer exit code
```

**Let Expression**  

Therefore this F# code:

```fsharp
let a = 5
let b = a * 2
let c = a + b
Console.WriteLine(c);
```

**Function Signatures**  

This example is a function that takes in another function as a parameter. The notion/type for this function is:  

`int -> (int -> bool) -> int` 

to run the function below

Parenthesis are used to indicate the nested function that is a parameter. Parenthesis are also used to indicate a function that is returned. Take the following F# function: 
 
```fsharp  
let doubleWhenTrue num predicate =
    if(predicate(num)) then
        num*2
    else
        num
```  

**Curring**  

This generic function type is pretty confusing and long, and this is a major reason why F# (and functional programming in general) leans heavily on type inference.

In F# all functions are curried by default. For example take the following F# function:
```f#
let addTwoNumbers num1 num2 =
    num1 + num2
```
The above function takes in two parameters and adds them together. In F# you can actually call this function with just one parameter. Since the function is curried it returns a function that takes in a single integer and returns an integer.

```f#
let addTen = addTwoNumbers 10
let twelve = addTen 2
let fifteen = addTen 5
```
Calling a function without all of its parameters is called a partial function application. Due to F#’s built in currying, it is not possible to overload a function in F#. 

If you want to prevent a function from being partially applied, you can group together the inputs in a tuple. Since a tuple is a single value you must give all of the items inside the tuple at the same time. For example take the following F# method:

```f#
let addTwoNumbersTuple (num1, num2)=
    num1 + num2
```    