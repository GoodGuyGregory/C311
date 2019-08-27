# C311 Functional Programming

[Fsharp Docs](https://fsharp.org/)

[F# Guide With Emphasis on Visual Studio Integrations](https://connelhooley.uk/blog/2017/04/10/f-sharp-guide)

## Installation  

[Fsharp Install](https://fsharp.org/use/mac/)

[VS Code](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-vscode)

## Videos  

[Fsharp.org](https://fsharp.org/videos/1)  

**Records**  

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

**If Expressions**