---
layout: default
title: Haskell recursion
excerpt: One of the beautiful things about Haskell is recursion.
---
As a functional programing language, Haskell uses functions instead of loops, AKA recursion. If you have not read my [old posts](http://theuniverseisahypersphere.blogspot.com/), recursion is calling a function inside of itself to get a loop like effect. In many programing languages, recursion is more memory intensive and less efficient than using loops, but it creates elegant solutions for challenging problems. Being a mathematics oriented language, it makes sense that Haskell would orient itself around recursion. Normally when implementing a recursive algorithm, you have a base case, in which a specific value is returned and a general case that will return a function call on a modified input. Here is code that computes the nth Fibonacci number written in Haskell:

	fib 1 = 1
	fib 2 = 1
	fib x = fib (x-1) + fib (x-2)

As you can see, this function is broken up into three parts, one that tells Haskell what to return when fib is called with the argument 1, another for argument 2, and then what to do if any other input is received. Recursion can also be coded using a case switch system, which will return different arguments depending on the value of a variable. Here is code that recursively calculates factorials written with a switch case:

	factorial x =
		case x of
		  	1->1
		  	_-> x * factorial (x-1)

When Haskell reads a function like my fib function that has multiple definitions depending on input (much like a piecewise function in math), it turns it into a case function like my factorial one. Spiting up the function by input is generally easier to read, but it is good to know that you can also get the same result using a switch case. This week, I also got my first introduction to lambda functions, which are functions that can easily be passed as arguments into higher order functions. For example, if I wanted to get the first 100 squares, I could type:

	map (\x -> x*x) [1..100]

Map is a higher order function that applies a function to every element in a list. The result is the first 100 squares. This has many useful applications, and I am only beginning to look into them. I look forward to updating you on my progress next week!
