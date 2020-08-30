# Algorithms and Pseudocode

## Algorithms 

**Algorithms** are actions and steps or directions involved in solving a function or a part of a program. The efficiency of a chosen algorithm is calculated using Big O notation, namely runtime and space complexity. 

#### Example: How to Make a Cake 

In the example below for making a cake, the algorithm wouuld be a series of steps as listed. 

Step 1: Choose a Recipe  
Step 2: Choose the Right Baking Pans  
Step 3: Allow Ingredients to Reach Room Temperature  
Step 4: Prep the Pans  
Step 5: Preheat the Oven  
Step 6: Stir Together Dry Ingredients  
Step 7: Combine the butter and sugar  
Step 8: Add Eggs One at a Time  
Step 9: Alternate Adding Dry and Wet Ingredients  
Step 10: Pour Batter Into Pans and Bake  
Step 11: Check Cake for Doneness  
Step 12: Cool the Cake  
Step 13: Assemble the Cake  
Step 14: Add the First Coat of Frosting  
Step 15: Frost and Decorate  

#### Example: Search for a Photo from Pixabay 

In this example if we are to describe to someone the algorithm to search a photo in a photo search application, the algorithm would be similar to the steps below. 

1. Step 1 Write an API Client class 
2. Setp 2 Write a function within that class
3. Step 3 Add the following to the function's body
4. Step 4 Add the endpoint needed to query the Web API 
5. Step 5 Create a URL using the endpoint URL 
6. Step 6 Use the URLSesson class to make the network request 
7. Step 7 Check and handle any errors  
8. Step 8 Use JSONDecoder to parse the received Data to the Swift model e.g Photo 
9. Step 9 Return the Photo to the caller


## Pseudocode

**Pseudcode** is a non-code way of explaining in "English" your thought process towards solving a problem. We use pseudocode, especially in interviews to show the interviewer our clearly defined methodology in solving and getting to a solution for a given problem. The more defined and clear the pseudocode the easier it will be to implement your solution in code. Let's go through an example below: 

#### Example: Write a function to find the largest value in an array 

_Example Input: [4, 1, -89, 23]_   
_Example Output: 23_  

Pseudocode

<pre> 
Input: array of Int
Output: return an Int

guard to retrieve the first value of the array, make sure it's mutable and define it as largest 
for each element in the array of Ints 
check if the current number is greater than the largest variable
  if it is assign the current number to the largest variable
return largest
</pre> 

Some clarification questions can be:
1. Can the array be empty? 
2. Can I return nil if the array is empty?

<details>
  <summary>Now that we have written the pseudocode, let's convert it to compilable Swift code.</summary>
  
```swift 
func findLargest(_ arr: [Int]) -> Int? {
  guard var largest = arr.first else {
    return nil
  }
  for currentNum in arr {
    if currentNum > largest {
      largest = currentNum
    }
  }
  return largest
}
```
  
</details> 

## Challenge

Write pseudocode for the following questions and convert your pseudocode to compilable code. 

Reminder as you work through the challenges practice doing the following: 

* Discuss clarification questions with your peer. 
* Discuss runtime and space complexity of your solution. 

</br> 

#### Challenge 1 

Write a function that returns how many vowels are in a String

_Sample Input: "Hello there! How's it going?"_

_Sample Output: 8_

<details> 
  <summary>Pseudocode Solution</summary> 
  
<pre> 
Input: String 
Output: Int 

exmaple: "alex" => 2 

declare and initialize a constant Set vowels that has the vowels "aeiou"
declare and initialize a vowel counter
for each Character in the String 
  check if the current Character is contained in the Set, vowels 
    if true, increment the vowel counter variable by one 
return the vowel counter 
</pre>
  
</details> 


<details> 
  <summary>Code Solution</summary> 
  
```swift 
func countVowels(_ inputString: String) -> Int {
  let vowels: Set<Character> = Set("aeiou")
  var vowelCounter = 0
  for char in inputString {
    if vowels.contains(char) {
      vowelCounter += 1
    }
  }
  return vowelCounter
}

countVowels("Hello there! How's it going?") // 8
```
  
</details> 

</br> 

#### Challenge 2

Write a function that returns the product of an array of Ints with any zeros taken out

_Sample Input: [4,0,8,3,0]_

_Sample Output: 96_


<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 
Input: array on Int 
Output: Int 

define and initialize a product variable to 1 
for each element in the input array 
  check if the current element is not zero 
    if true, add to product 
return product

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
func productIgnoreZeros(_ arr: [Int]) -> Int {
  var product = 1
  for num in arr {
    if num != 0 {
      product *= num
    }
  }
  return product
}

productIgnoreZeros([4, 0, 8, 3, 0]) // 96
```

</details> 

</br> 

#### Challenge 3


<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 4

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 5

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 6 

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 7

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 8


<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 9


<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

#### Challenge 10


<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 

</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
```

</details> 

</br> 

## Resources 

1. [How to make a cake](https://www.bhg.com/recipes/how-to/bake/how-to-make-a-cake/)
