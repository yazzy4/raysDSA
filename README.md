# raysDSA
 Ray Wenderlich DSA Review for upcoming job interviews and general practice

## Day 1 Big O! - Taking it back to the basics 
To Do: 
- Constant time 
- Linear time
- Quadratic time 
- Logarithimic time (what a word to try to remember how to spell amirite?)
- Quasilinear time (same)
- And the rest!

![](https://media.giphy.com/media/3orieMlrdm4bxzP3jy/giphy.gif)

#### Time complexity
Involves the measure of time used to run an algorithm as the input size increases

#### Constant Time - O(1)
Constant time has the same running time regardless of the size of the input

For example:

```swift
func checkFirst(names:[String]){
    if let first = names.first {
        print(first)
    } else {
        print("no names")
    }
}
```
This function creates a new variable named ``` first ``` and sets its value to check the first name in the array of strings. When it is called and takes an input of an array of strings, it will therefore call only the first element in the array, otherwise no name at all. In this case, no matter how many names are in the array its will always return the first element. Because the output doesn't change based on the size, this is called constant time or O(1)

#### Linear Time - O(n)
Linear time occurs when the input size increases at the same rate as the running time.

For example

```swift 
func printNames(names:[String]){
    for name in names {
        print(name)
    }
}
```
This function prints all the elements in the array and if another element is added to the that array the time complexity will my increased by the same amount of its input


#### Quadratic Time - On^2



#### Logarithimic Time - O(log n)

#### Quasilinear Time - O(n log n)


