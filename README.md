# WDI Morning Exercises

## Miscellaneous Ideas

- Blog Post presentations
 - Blog example 1 - http://nishacodes.tumblr.com/
- Portfolio Work Day
- Moronic Monday
- Homework Review
- UX Lesson from a UXDI Instructor

## Videos

- [You Should Learn to Program: Christian Genco at TEDxSMU](https://www.youtube.com/watch?v=xfBWk4nw440) _This is a good morale booster for Week 7_
- [This is Water Commencement Speech by David Foster Wallace](https://www.youtube.com/watch?v=MZjpihl2pfg) _This is a good morale booster for Week 7_


## CSS Challenges

- [CSS Button](http://codepen.io/mobify/pen/GtqKj)
- [CSS Form](http://codepen.io/bephf/pen/emzKMJ/)

## Code Challenges

### FizzBuzz

https://github.com/generalassembly-atx/fizzbuzz

### Email Code Challenge 

This was a code challenge from a real company. You can't email the recruiter until you solve all the issues to reveal the email address. 

_Good for Unit 4_

http://codepen.io/anon/pen/YwxgvW?editors=001

---

### Merry Christmas - Nested Loops

_Good for Unit 4_

**Part One:** Write a function to turn a string into an array of letters. 
Example: "Merry Christmas" should become [ 'M', 'e', 'r', 'r', 'y', 'C', 'h', 'r', 'i', 's', 't', 'm', 'a', 's' ]. 

```js
str = 'Merry Christmas'

function stringToArray(string) {
	var array = string.split('');
	return array;
}

var arr = stringToArray(str);
console.log(arr);
```

**Part Two:** Return the first unique letter in the string "Merry Christmas"?

```js
for (i=0; i < arr.length; i++){
    for (j=i++; j < arr.length; j++) {
        if (arr[j] == arr[i]){
            break;
        } else {
            console.log(arr[i]);
        }
    }
}
```

---

### Sum of Multiples
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23. Find the sum of all the multiples of 3 or 5 below 1000.

_Good for Unit 3 or 4_

  In JS:
  ```js
  // = 233168
  function naturalSum(num){
      var sum = 0;
      for(var i=1; i < num; i++) {
          if (i%3===0 || i%5===0) {
             sum += i;
          }
      }
      return sum;	
  }

  naturalSum(1000);
  ```

  In Ruby:
  ```ruby
  (1..999).to_a.map do |i|
    (i % 3 === 0 || i % 5 === 0) ? i : 0
  end.inject(0) { |sum, i| sum + i }
  ```
--- 

### Largest Prime Factor 

The prime factors of 13195 are 5, 7, 13 and 29. What is the largest prime factor of the number 600851475143?

_Good for Unit 4_

  In JS:
  ```js
  // = 6857
  function largestPrimeFactor(num) {
  var result, arr=[];
  
  if(isPrime(num)) {
    result = num;
  } else {
    for(var i=2; i<Math.sqrt(num); i++) {
      if(isPrime(i) && num % i === 0) {
        arr.push(i);
        if(isPrime(num/i)) {
          arr.push(num/i);
        }
      }
    }
    result = Math.max.apply(Math, arr);
  }
    
  return result;  
}
  ```

  In Ruby:
  ```ruby
  require 'prime'
  factors = []
  Prime.each(Math.sqrt(600851475143)) do |prime|
    factors << prime if number % prime == 0
  end
  factors.last
  ```
---

### Largest Palindromic Number
A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99. Find the largest palindrome made from the product of two 3-digit numbers.

_Good for Unit 4_

---
### Caesar Cipher

Code War [Caesar Cipher](https://www.codewars.com/kata/caesar-cipher-helper/train/javascript)

_Good for Unit 4_

  ```js
    // Partial Solution
    var CaesarCipher = function (shift) {
    // lower case: 97-122
    // upper case: 65-90

    this.encode = function(str){
      var new_str = '';
      for (var i = 0; i < str.length; i ++) {
        if (str[i].match(/[a-z]/i)){
          var code = str.charCodeAt(i);
          var new_code = code + shift;
          new_str += (String.fromCharCode(new_code))
        }
      };
      return new_str.toUpperCase();
    }
    this.decode = function(str){
      var new_str = '';
      for (var i = 0; i < str.length; i ++) {
        if (str[i].match(/[a-z]/i)){
          var code = str.toUpperCase().charCodeAt(i);
          var new_code = code - shift;
          new_str += (String.fromCharCode(new_code))
        }
      };
      return new_str;
    }

  };
  ```
 ---

 
