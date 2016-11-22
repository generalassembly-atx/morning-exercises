# WDI Morning Exercises

## Miscellaneous Ideas


## Videos

- [You Should Learn to Program: Christian Genco at TEDxSMU](https://www.youtube.com/watch?v=xfBWk4nw440) This is a good morale booster for Week 7
- [This is Water Commencement Speech by David Foster Wallace](https://www.youtube.com/watch?v=MZjpihl2pfg) This is a good morale booster for Week 7


## CSS Challenges

- [CSS Button](http://codepen.io/mobify/pen/GtqKj)
- [CSS Form](http://codepen.io/bephf/pen/emzKMJ/)

## Code Challenges

#### Sum of Multiples
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23. Find the sum of all the multiples of 3 or 5 below 1000.

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

#### Largest Prime Factor 
The prime factors of 13195 are 5, 7, 13 and 29. What is the largest prime factor of the number 600851475143?

  In JS:
  ```js
  // = 6857
  function findPrimeFactors(value){
  	var factors = [];
  	for(var i=1; i< (Math.sqrt(value)); i++){
  		if (value%i===0){
  			if (isPrime(i)){
  				factors.push(i);
  			}
  		}
  	}
  	return factors.pop();
  }

  function isPrime(value) {
      for(var i = 2; i < value; i++) {
          if(value % i === 0) {
              return false;
          }
      }
      return value > 1;
  }

  findPrimeFactors(600851475143);
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

#### Largest Palindromic Number
A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99. Find the largest palindrome made from the product of two 3-digit numbers.

#### Caesar Cipher

Code War [Caesar Cipher](https://www.codewars.com/kata/caesar-cipher-helper/train/javascript) Unit 4
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
 
