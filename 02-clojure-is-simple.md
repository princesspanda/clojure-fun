# Goals
* To show example of how certain things are simpler in Clojure
* To get you to LOVE parentheses

## What do you mean by 'simple'?
* Really good support for data structures (lists, vectors, maps, sets)
* The ability to bend the language to meet the domain (more about multimethods and protocols much later)

----
**Example:** Write a function that will take an array of integers, and return an array of the even numbers in the given array.

In Javascript:
````
var nums = [1, 42, 99, 56, 37, 100, 101];
var result = [];

for (num in nums) {
  if (num %2 == 0) {
    result.push(num);
  }
}
````

In Ruby:
````
nums = [1, 42, 99, 56, 37, 100, 101]
nums.select { |num| num.even? }
````

In Clojure:
````
(filter even? [1 42 99 56 37 100 101])
````

----
**Example:** Assume you have a variable ````a```` that stores an integer.  How would you increment it by one? 

In Java:
````
a++
++a
a += 1
a + 1
````

In Clojure:
````
(inc a)
````

---
## Much parentheses.  Such headache.  WOW.

All Clojure code is made up of expressions, which evaluate to values.  These are all expressions:

````
"o hai"
(+ 1 2)
(max 1 2 3)
(println "I heart pandas")
````

Rules for evaluation:
* Lists, or anything in parentheses ````()````, are calls.  The first element in the list (+, max, println) is the operator, and the remaining elements are parameters.  The first position is what we call *function position*
* Symbols (+, max, or println) evaluate to a named value in the current scope (more on this later)
* Anything else evaluates to the literal values they describe ("o hai" is just a string literal).

When you see something like this, your first reaction might be "Oy ve, these parentheses make my head hurt"
````
Prefix: (+ (- (+ (+ 1 (/ (* 2 3) 4)) 5) (/ (* 6 7) 8)) 9)
````

But when you think about it, it's easier to parse than this:
````
Infix:  1 + 2 * 3 / 4 + 5 - 6 * 7 / 8 + 9
````

The infix version is difficult to parse because you have to remember order of operations ([Please Excuse My Dear Aunt Sally](http://www.mathsisfun.com/operation-order-pemdas.html)



