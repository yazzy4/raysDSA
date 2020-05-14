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
func checkFirst(names:[String]) {
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
func printNames(names:[String]) {
    for name in names {
        print(name)
    }
}
```
This function prints all the elements in the array and if another element is added to the that array the time complexity will my increased by the same amount of its input


#### Quadratic Time - On^2
Quadratic time refers to an algorithm that takes time proportional to the square of its input size. Like inception...

For example:
```swift
func printMoreNames(names: [String]) {
    for _ in names{
        for name in names {
            print(name)
        }
    }
}
```
This function is simlar to the former, but with a nested loop. This means that the function prints out names in the array for every name in the array. In other words, if you had an array with 10 elements, it would print 10 elements for each of those elements. **Inception.....** but also just really time consuming and space consuming algorithm.


#### Logarithimic Time - O(log n)
Logariththmic time is where we begin to deviate for the patterns set by contant and linear time. In the previous time complexities, there have been examples of the function considering each element in the array. Writing a function in logarithmic times means that a subset of data is already assumed. In other words if we were trying to find out if an array comntains a middle element or a certain number, half of the work is already done. Nice when that works out right?

For example:

```swift
let numbers = [2, 4, 6, 17, 19, 22, 87, 91, 104]

func naiveContains(value: Int, in array: [Int]) -> Bool{
    for element in array {
        if element == value {
            return true
        }
    }
    return false
}
```
In this function, a for loop is used to check every element in the already sorted array. Only after each value is checked is the number we are searching for confirmed to be true or false. This gives a run time of O(n). In total, it runs 9 times.


```swift
func middleElement(value: Int, in array: [Int]) -> Bool{
    guard !array.isEmpty else {return false}
    let middleIndex = array.count / 2

    if value <= array[middleIndex] {
    for index in 0...middleIndex {
        if array[index] == value {
            return true
            }
        }
    } else {
        for index in middleIndex..<array.count {
            if array[index] == value {
                return true
            }
        }
    }
    return false
}
```
While this function seems more involved than the first, it actually cuts the run time in half. The function takes in a ```value ```of ints and that is the value that will used to determine if the value does exist in the other parameter of the function ```array``` 

Next, so as to not waste any runtime at all, we then ```guard``` against the array to determine that it is not empty. It's not so on we go to set a variable ```middleIndex``` that divides the array in two and presumably at the middle index. The first algorithim checks the middle value to how in compares to the desired value. If the middle value is greater than the desired value, the algorithim won't bother checking the right side of the array because it is sorted and the values on the right are higher

On the other side, if the middle value is smaller than the desired value its won't check the the left side of the array because the values are smaller. It is only checking half the array at a given time.



## Day 2 Stacks - Pancakes, plates and more!

To Do: 
- Implement a stack 
- Reverse an array using a stack 
- Balance parentheses 

**Stack Operations**

The main goal of builing a stack enforce how you access your data. When thinking of building stacks it is not dissimilar building a stack of pancakes. It's all not dissimilar to eating said stack of pancakes in that, if you are fixing a plate for yourself you'll likely grab one from the top.

![](https://media.giphy.com/media/3o7btPYDFhb7rNANqw/giphy.gif)
