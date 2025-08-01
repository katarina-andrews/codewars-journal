# Codewars Journal
A collection of some challenges I've completed and how I've learned from them. 


### Challenge 1: Highest and Lowest (7kyu)
- **Link:** https://www.codewars.com/kata/554b4ac871d6813a03000035
- **Description:** In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.
- **My Solution:**
  ```js
  function highAndLow(numbers){
  let nums = numbers.split(" "); 
     const high = Math.max(...nums);
    const low = Math.min(...nums);
    return `${high} ${low}`
    }

**What I Learned:** I mostly knew how to do it but I did learn that I had to convert the string to an array first.

**Other Notes:** I know I was doing it right but it kept failing and I could't figure out why. Then I realized I didn't read the directions that well and kept putting a comma between `${high} ${low}`


### Challenge 2: Vowel Count (7kyu)
- **Link:** https://www.codewars.com/kata/54ff3102c1bad923760001f3
- **Description:** Return the number (count) of vowels in the given string.
- **My Solution:**
  ```js
  function getCount(str) {
  const vowels = str.match(/[aeiou]/gi)
  return vowels ? vowels.length : 0;
  }

**What I Learned:** I learned that I needed to use the match method and had to us g in order to find all occurrences instead of stopping after the first match. The i technically wasn't needed because in the instructions it states that the input sting wil only consists of lower case letters.

**Other Notes:** At first just had return str.match(/[aeiou]/gi).length but it only passed 4/6 tests. Then realized I needed to account for input strings with no vowels. 


### Challenge 3: Is a number prime? (6kyu)
- **Link:** https://www.codewars.com/kata/5262119038c0985a5b00029f
- **Description:** Define a function that takes an integer argument and returns a logical value true or false depending on if the integer is a prime.
- **My Solution:**
  ```js
  function isPrime(num) {
    if (num <= 1) return false;
    if (num === 2) return true;
    if (num % 2 === 0) return false;

    const sqrt = Math.sqrt(num);
    for (let i = 3; i <= sqrt; i += 2) {
        if (num % i === 0) {
            return false;
        }
    }
    return true;
    }

**What I Learned:** I learned how important performance and optimization is. I should always keep in mind that I may be dealing with a large amount of data. 

**Other Notes:** The first version I had passed the test but didn't pass on submit because it took too long so I had to figure out a way to make it faster. In the directions it did note that "the most trivial solutions might time out." This solution skips over even numbers and takes a a sqrt of a number and checks only if its divisible by the odd numbers less than or equal to the sqrt. 

Examples: 

```
Math.sqrt(67) ~ 8.19
67 % 3 = 1
67 % 5 = 2
67 % 7 = 4
67 is prime

Math.sqrt(121) ~ 11
121 % 3 = 1
121 % 5 = 1
121 % 7 = 2
121 % 9 = 4
121 % 11 = 0
121 is not prime
```


### Challenge 4: Create Phone Number (6kyu)
- **Link:** https://www.codewars.com/kata/525f50e3b73515a6db000b83
- **Description:** Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.
- **My Solution:**
  ```js
  function createPhoneNumber(numbers){
  const joinArr = numbers.join("");
  return joinArr.replace(/^(\d{3})(\d{3})(\d{4})$/, "($1) $2-$3");
  }

**What I Learned:** I learned that I needed to use a replacement string when using the replace method unless it won't do anything. 

**Other Notes:** It kept failing because I was putting quotes around the regex. 


### Challenge 5: Reversed Strings (8kyu)
- **Link:** https://www.codewars.com/kata/5168bb5dfe9a00b126000018
- **Description:** Complete the solution so that it reverses the string passed into it.
- **My Solution:**
  ```js
  function solution(str){
  return str.split("").reverse().join("");
  }

**What I Learned:** Pretty straight forward. I used these string methods to keep it simple. 


### Challenge 6: List Filtering (7kyu)
- **Link:** https://www.codewars.com/kata/53dbd5315a3c69eed20002dd
- **Description:** In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.
- **My Solution:**
  ```js
  function filter_list(l) {
  const filteredList = l.filter(element => typeof element !== "string");
  return filteredList;
  }

**What I Learned:** Pretty straight forward. I know I had to use an array method and I reacquainted myself with the typeof operator.


### Challenge 7: Find the unique number (6kyu)
- **Link:** https://www.codewars.com/kata/585d7d5adb20cf33cb000235
- **Description:** There is an array with some numbers. All numbers are equal except for one. Try to find it!
- **My Solution:**
  ```js
  function findUniq(arr) {
  return arr.find(
    (num) =>
        arr.indexOf(num) === arr.lastIndexOf(num));
  }

**What I Learned:** I learned more about array methods and how to implement them properly. 

**Other Notes:** Finding a number which first occurrence and last occurrence is the same index.