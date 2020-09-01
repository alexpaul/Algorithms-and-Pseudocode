# Algorithms and Pseudocode

## Algorithms 

**Algorithms** are a series of steps involved in solving a function or a part of a program. The efficiency of a chosen algorithm is calculated using [Big O notation](https://github.com/alexpaul/Big-O-Notation), namely runtime and space complexity. 

**Data Structures** is the construct you choose to use to store the data of your algorithm. Example will you be using an array to store the ingredients for your awesome cake algorithm below or use a Set.  

#### Example: How to Make a Cake 

In the example below for making a cake, the algorithm would be a series of steps as listed. 

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

1. Create an endpoint URL String to the photo Web API.  
2. Create a URL using the endpoint URL String.
3. Use the URLSesson class to make the network request. 
4. Check and handle any errors returned from teh respsonse.  
5. Use JSONDecoder to parse the received Data to the Swift model e.g Photo.
6. Return the Photo to the caller.


## Pseudocode

**Pseudcode** is a non-code way of explaining in "English" your thought process towards solving a problem. We use pseudocode, especially in interviews to document to the interviewer our clearly defined methodology in solving and getting to a solution for a given problem. The more defined and clear the pseudocode the easier it will be to implement your solution in code. Let's go through an example below: 

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
* Discuss the data structure you will use and any tradeoffs it make have. 
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

All Ints appear twice in an array, but one element appears only once. Write a function to find the outlier.

_Sample Input: [4,0,7,8,3,0,4,3,8]_  

_Sample Output: 7_  

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 
Input: array of Int 
Outpur: Int

create a frequency dictionary to store number and the count of time it appears
for each number in the array
 store the number as the key in the frequency dictionary and increment the count of times it appears
search the dictionary for the key that has a count of 1
return the key
</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
func outlier(_ arr: [Int]) -> Int? {
  var freqDict = [Int: Int]()
  for num in arr {
    if let count = freqDict[num] {
      freqDict[num] = count + 1
    } else {
      freqDict[num] = 1
    }
  }
  for (key, value) in freqDict {
    if value == 1 {
      return key
    }
  }
  return nil
}
```

</details> 

</br> 

#### Challenge 4

Write a function that returns whether an Array of Ints contains any numbers divisible by 13

_Sample Input: Input: [4, 1, 13, 89, 3]_  
_Sample Output: true_   

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 
Input: array of In t
Output: Bool 

for each element in the array
 check if the current number is divisible by 13
   if true, return true
</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
func isDivibleBy13(_ arr: [Int]) -> Bool {
  for num in arr {
    if num % 13 == 0 {
      return true
    }
  }
  return false
}
```

</details> 

</br> 

#### Challenge 5

Write a function that reverses a String without using built-in reverse methods (i.e don't write ~.reversed()")

_Sample Input: "swift rocks"_  
_Sample Output: "skcor tfiws"_  

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 
Input: String 
Output: String 

declare and initialize a new empty String 
for each character in the input String 
  append the current character to the front of the new String 
return new reversed String 
</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
func reverseString(_ inputString: String) -> String {
  var newString = ""
  for char in inputString {
    newString = String(char) + newString
  }
  return newString
}
```

</details> 

</br> 

#### Challenge 6 

Here we have a LeetCode problem that involves more content to a problem. In pseudocoding and coming up with a solution, do the following: 

1. Read through the question and make your own notes in your IDE as needed, e.g Xcode or [Repl.it](https://repl.it/~). 
2. Check the **Note** section for clarification questions. 
3. Pseudocode an algorithm for your proposed solution. 
4. Convert your pseudocode to a working solution. 

Every email consists of a local name and a domain name, separated by the @ sign.

For example, in `alice@leetcode.com`, `alice` is the local name, and `leetcode.com` is the domain name.

Besides lowercase letters, these emails may contain `'.'`s or `'+'`s.

If you add periods (`'.'`) between some characters in the **local name** part of an email address, mail sent there will 
be forwarded to the same address without dots in the local name.  For example, `"alice.z@leetcode.com"` and
`"alicez@leetcode.com"` forward to the same email address.  (Note that this rule does not apply for domain names.)

If you add a plus (`'+'`) in the **local name**, everything after the first plus sign will be **ignored**. This allows 
certain emails to be filtered, for example `m.y+name@email.com` will be forwarded to `my@email.com`. 
(Again, this rule does not apply for domain names.)

It is possible to use both of these rules at the same time.

Given a list of `emails`, we send one email to each address in the list.  How many different addresses 
actually receive mails? 

 
**Example 1:**

<pre>
Input: ["test.email+alex@leetcode.com","test.e.mail+bob.cathy@leetcode.com","testemail+david@lee.tcode.com"]
Output: 2
Explanation: "testemail@leetcode.com" and "testemail@lee.tcode.com" actually receive mails
</pre>

**Note:**

* `1 <= emails[i].length <= 100`
* `1 <= emails.length <= 100`
* Each `emails[i]` contains exactly one `'@'` character.
* All local and domain names are non-empty.
* Local names do not start with a `'+'` character.

[LeetCode - Unique Email Addresses](https://leetcode.com/problems/unique-email-addresses/)

<details> 
  <summary>Pseudocode Solution</summary> 
 
<pre> 
Pseudocode

Input: array of String
Output: Int

declare and initialize a Set, uniqueEmails variable that will hold unique emails
for each email in emails
 separate the email by the "@" into a local and domain name
 use a helper function that returns the parsed local name
 create a new email using the parsed local name and the domain name
 insert this new email to the unique Set collection
return the unique emails count
</pre> 
  
</details> 


<details> 
  <summary>Code Solution</summary> 
 
```swift 
func uniqueEmailAddresses(_ emails: [String]) -> Int {
  var uniqueEmails: Set<String> = []
  for email in emails {
    let localNameAndDomainName = email.components(separatedBy: "@")
    guard let localName = localNameAndDomainName.first,
      let domainName = localNameAndDomainName.last else { return 0 }
    let  modifiedLocalName = parseLocalName(localName)
    let newEmail = "\(modifiedLocalName)@\(domainName)"
    uniqueEmails.insert(newEmail)
  }  
  return uniqueEmails.count
}

func parseLocalName(_ localName: String) -> String {
  var modifiedName = ""
  for char in localName {
    if char == "+" {
      return modifiedName
    }
    if char == "." {
      continue
    }
    modifiedName.append(char)
  }
  return modifiedName
}
```

</details> 

</br> 

## Resources 

1. [HackerRank - Big O](https://www.youtube.com/watch?v=v4cd1O4zkGw&list=LL&index=26&t=17s)
2. [HackerRank - Solving Algorithms](https://www.youtube.com/watch?v=GKgAVjJxh9w&list=LL&index=27&t=0s)
3. [How to make a cake](https://www.bhg.com/recipes/how-to/bake/how-to-make-a-cake/)
