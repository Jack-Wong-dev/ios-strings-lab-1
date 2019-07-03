# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)

```
swift
//Solution 

var answer = String()
for i in 1...10{
    answer += " \(i)"  //Classic Concatenation
  //answer.append(" \(i)")      //Using append
}
print(answer)
```


***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

```
swift
var someRange = 5...51
var evenString = String()

for i in someRange where i % 2 == 0{
evenString.append(" \(i)")
}; print(evenString)
```



***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

```
swift
var someRange = 1...60
var str_Four = String()

for i in someRange where i % 10 == 4{
str_Four.append(" \(i)")
}; print(str_Four)
```
***
## Question 4

Print each character in the string `"Hello world!"`
```
var hello = "Hello world!"

for char in hello{
print(char)
};print(hello)
```
***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

```
swift

let myStringSeven = "Hello world!"

let last_Char = myStringSeven.suffix(1)
print(last_Char)

```



***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.

``` 
swift 
//using switch statements
var str = "Hello World"
var answerIfOdd = String()
var indexCounter = 0
var length = str.count

switch (length % 2 == 0) {

case true:

print(str)

case false:
for char in str{
if(indexCounter % 2 != 0 ){answerIfOdd.append(char)}
indexCounter += 1
}
print(answerIfOdd)
}
```
```
swift
//using if statements instead
var str = "Hello World"
var answerIfOdd = String()
var indexCounter = 0

if str.count % 2 == 0{
print(str)
}else{
for char in str{
if(indexCounter % 2 != 0 ){answerIfOdd.append(char)}
indexCounter += 1
}
}; print(answerIfOdd)

```




***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

```
let c : Character = "a"
let str : String = "a"

//c == str ? print("Same") : print("Can't compare")
```

***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.

```
swift

var ay = "\u{00C1}"
var by = "\u{0041}\u{0301}"
ay == by ? print("True") : print("False")

var c = "\u{1E31}"
var d = "\u{006B}\u{0301}"
c == d ? print("True") : print("False")

var e = "\u{1E77}"
var f = "\u{0075}\u{032D}"
e == f ? print("True") : print("False")

var g = "\u{1E53}"
var h = "\u{006F}\u{0304}\u{0301}"
g == h ? print("True") : print("False")

var a = "\u{00C4}"
var b = "\u{0041}\u{308}"
a == b ? print("True") : print("False")

````


***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`

```
swift
var hello = "\u{0048}\u{0065}\u{006c}\u{006c}\u{006f}\u{0020}\u{0057}\u{006f}\u{0072}\u{006c}\u{0064}"

print(hello)
```



***
## Question 10

**Using only Unicode**, print out your name.

```
swift
var myName = "\u{004a}\u{0061}\u{0063}\u{006b}\u{0020}\u{0057}\u{006f}\u{006e}\u{0067}"
print(myName)
```

***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.

```
swift
var helloWorldChinese = "\u{4E16}\u{754C}\u{4F60}\u{597D}\u{21}"
print(helloWorldChinese)  //世界你好!
```

***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -
```

```
swift
let row = String(repeating: "\u{0020}\u{0020}\u{002D}\u{0020}", count: 10)
print(row)


for _ in 1...4{
let lols = String(repeating: "\u{007C}\u{0020}\u{2698}\u{0020}", count:10) + "\u{007C}"
print(lols)
}

print(row)
```

***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜
```
```
swift
let whiteRook = "\u{2656}"
let whiteKnight = "\u{2658}"
let whiteBishop = "\u{2657}"
let whiteQueen = "\u{2655}"
let whiteKing = "\u{2654}"
let whitePawn = "\u{2659}"

let blackRook = "\u{265C}"
let blackKnight = "\u{265E}"
let blackBishop = "\u{265D}"
let blackKing = "\u{265A}"
let blackQueen = "\u{265B}"
let blackPawn = "\u{265F}"

var rowWhitePawns = String(repeating: whitePawn, count: 8)
//print(rowWhitePawns)
var rowBlackPawns = String(repeating: blackPawn, count: 8)
//print(rowBlackPawns)
var whitePieces = whiteRook+whiteKnight+whiteBishop+whiteQueen+whiteKing+whiteBishop+whiteKnight+whiteRook
//print(whitePieces)
var blackPieces = blackRook+blackKnight+blackBishop+blackKing+blackQueen+blackBishop+blackKnight+blackRook
//print(blackPieces)

var chessBoard = """
\(whitePieces)
\(rowWhitePawns)




\(rowBlackPawns)
\(blackPieces)
"""

print(chessBoard)

```

***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with \*"

var replacedString = String()

for i in aString{
if(i == "e"){
replacedString.append("*")
}else{
replacedString.append(i)
}
};print(replacedString)
 ```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = ""

for i in aString{
reverse = "\(i)"+reverse
}; print(reverse)

```

Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

***
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"

// Your code here
```

Example 1:
Input:
`var aString = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`var aString = "Hello"`

Output:
`false`


```
swift
let aString = "anutforajaroftuna"

var reverse = ""

for i in aString{
reverse = "\(i)"+reverse
}
if reverse == aString{print("True")}
else{print("False")}
```


***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

var toArray = problem.components(separatedBy: " ")

for word in toArray{ print(word)}

```

Example:
Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"

//var problem = "find the longest word in the problem description wubbalubbadubdub"
let toArray = problem.components(separatedBy: " ")
var longestWord = String()

for word in toArray{
if (word.count > longestWord.count) {longestWord = word}
}; print(longestWord)
```

Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.



***
## Question 19

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"

var vowelCounter = 0
var consonantsCounter = 0

for char in input.lowercased(){

if vowels.contains(char) {vowelCounter += 1}
else if consonants.contains(char){consonantsCounter += 1}
}
var tuple = (vowelCounter,consonantsCounter)
print("There are \(tuple.0) vowels and \(tuple.1) consonants")
```

***
## Question 20

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

```
let testStr = "How are you doing this Monday?"
let toArray = testStr.components(separatedBy: " ")
let pattern =  "[^a-zA-Z0-9]"

//print(toArray[toArray.count-1].count) //prints size of last word

(toArray[toArray.count-1].range(of: pattern, options:.regularExpression) == nil) ? print("No last Word") : print(toArray[toArray.count-1].count)

//uses regex to check if the last element is alphanumeric
```

***
