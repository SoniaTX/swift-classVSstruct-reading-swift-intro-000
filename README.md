# Classes & Structs Quiz

![](http://i.imgur.com/zWBjkea.jpg)  

> Success is not final, failure is not fatal: it is the courage to continue that counts. -[Winston Churchill](https://en.wikipedia.org/wiki/Winston_Churchill)

## Overview

This quiz will give you practice working with both classes and structs. 

## Quiz Time!

In the last few lessons, you've learned a lot about classes and structs in Swift. Now, challenge yourself with a brief quiz to test everything you've learned.




### Question 1

Given this class that represents a giant:

```swift
class Giant {
    var name: String
    var weight: Double
    let homePlanet: String

    init(name: String, weight: Double, homePlanet: String) {
        self.name = name
        self.weight = weight
        self.homePlanet = homePlanet
    }
}
```

And this code that instantiates an instance of `Giant`:

```swift
let fred = Giant(name: "Fred", weight: 340.0, homePlanet: "Earth")
```

Will these three lines of code run? If not, why not?

```swift
fred.name = "Brick"
fred.weight = 999.2
fred.homePlanet = "Mars"

\\\ No, one of these three lines cannot run because it cannot assign to "homePlanet" which is a "let" constant. In order to work, you have to change let to var to make it mutable. 
```





### Question 2

Can you fix the class definition above so that it _does_ work?

\\\ Yes, in order to work, you have to change let to var to make it mutable. 





### Question 3

Take a look at this struct that represents an alien:

```swift
struct Alien {
    var name: String
    var height: Double
    var homePlanet: String
}
```

And this line of code that instantiates an `Alien`:

```swift
let bilbo = Alien(name: "Bilbo", height: 1.67, homePlanet: "Venus")
```
Will these three lines of code run? If so, why not?

```swift
bilbo.name = "Jake"
bilbo.height = 1.42
bilbo.homePlanet = "Saturn"

\\\ No, because these three lines of code cannot run due to compiler error. All cannot assign to "bilbo" which is a "let" constant. 





### Question 4

Can you change the declaration of `bilbo` so that the above three lines of code _do_ work?

\\\ Yes, you have to change the declaration of 'bilbo' from "let bilbo" to "var bilbo" to make it mutable. 
    I print all of these three codes to double check and it is working successfully.  
    print(bilbo.name)
    print(bilbo.height)
    print(bilbo.homePlanet)





### Question 5

Consider this bit of code that uses the `Giant` class:

```swift
let edgar = Giant(name: "Edgar", weight: 520.0, homePlanet: "Earth")
let jason = edgar
jason.name = "Jason"
```

What will the value of `edgar.name` be after those three lines of code are run? What will the value of `jason.name` be? Why?

The value of `edgar.name` will be Jason. Furthermore, the value of `jason.name` will be Jason. Both have same values because jason is equal to edgar. 







### Question 6

Given this bit of code that uses the `Alien` struct:

```swift
var charles = Alien(name: "Charles", height: 2.25, homePlanet: "Pluto")
var charlesFromJupiter = charles
charlesFromJupiter.homePlanet = "Jupiter"
```

What will the value of `charles.homePlanet` be after the above code run? What about the value of `charlesFromJupiter.homePlanet`? Why?


\\\\The value of `charles.homePlanet will be Pluto. Moreover, the value of `charlesFromJupiter.homePlanet` will be Jupiter. Both have different values because charlesFromJupiter.homePlanet is "Jupiter" , on other hand, homeplant is "Pluto". 







### Question 7

Here's a struct that represents a bank account:

```swift
struct BankAccount {
    var owner: String
    var balance: Double

    func deposit(_ amount: Double) {
        balance += amount
    }

    func withdraw(_ amount: Double) {
        balance -= amount
    }
}
```

Does this code work? Why or why not?

\\\ This code does not work due to compiler error because, left side of mutating operator ( eg. func deposit and func withdraw) isn't mutable: "self" is immutable. 





### Question 8

Can you fix the `BankAccount` struct so it _does_ work?

\\\Yes, I can fix the BankAccount struct by adding mutating method to two functions to make them mutable. 





### Question 9

Given this bit of code (which incorporates any fixes you made in Question 8):

```swift
var joeAccount = BankAccount(owner: "Joe", balance: 100.0)
var joeOtherAccount = joeAccount
joeAccount.withdraw(50.0)
```

What will the value of `joeAccount.balance` be after the above code runs? What about the value of `joeOtherAccount.balance`? Why?

\\\ The value of `joeAccount.balance` is 50.0 and the value of `joeOtherAccount.balance`is 100.0.
    Both have different values because 50.0 is withdraw from joeAccount which has balance of 100.0. joeAccount has same balance as joeOtherAccount. 





### Question 10

Here's a class that can track songs in a music library:

```swift
class MusicLibrary {
    var tracks: [String]

    init() {
        tracks = []
    }

    func add(track: String) {
        tracks.append(track)
    }
}
```

Given this bit of code that uses `MusicLibrary`:

```swift
let library1 = MusicLibrary()
library1.add(track: "Michelle")
library1.add(track: "Voodoo Child")
let library2 = library1
library2.add(track: "Come As You Are")
```

After this code runs, what are the contents of `library1.tracks`? What about the contents of `library2.tracks`? Why?

\\\ The contents of library1.tracks` are ["Michelle", "Voodoo Child", "Come As You Are"]. Also, the contents of 
 library2.tracks` are same as library1.tracks, because both library2 and library1 are same. 



<a href='https://learn.co/lessons/ClassesVsStructs' data-visibility='hidden'>View this lesson on Learn.co</a>
