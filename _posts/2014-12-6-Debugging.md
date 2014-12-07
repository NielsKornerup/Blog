---
layout: default
title: Debugging
excerpt: I give a simple guide to debugging.
---

Debugging can be the most tedious part of coding. You finally finish writing your program, and it seems like it is working, but all of a sudden, it breaks somewhere or gets trapped in some loop. You look back at your code, and cannot figure out what went wrong. If you received an error message with a line number, then you might know where to start looking, but that will not necessarily tell you what went wrong. Today, I will briefly discuss some tricks that can be useful when debugging.

Step one: Figure out where your code is breaking. 
If you cannot use line numbers to figure out where your code went wrong, add print statements at different points in your code. To differentiate between the statements, print different numbers. After this, rerun your code, and look to see what number was last printed to the console. You now know that your code broke between this print statement and the next one. If necessary, repeat this process until you can pinpoint the location that your code is breaking. Once you know where your code is breaking, move on to step two. If you receive an error statement saying what type of error you have and what line it is on, continue to step five. If your code only breaks with some inputs or under certain conditions, move to step ten.

Step two: Try and find out what is causing the error.
If knowing the line number is not enough to figure out your problem, you will need to find out its cause. Try printing out all variables that are used in the broken line in the line before it. If you are having problems with an infinite loop, print out the value of the variable that defines the stop condition on each iteration. If you cannot figure out why your loop is not ending, move to step five. If any of your values are null or NaN (or equivalents), then they could be causing your error. If this is the case, move to step three. If all of your variables are defined, move to step four. If all else fails, move to step six.

Step three: Finding where a value becomes undefined
Print out the value of that variable at different points in your code, labeling each so that you can find which statement each print is coming from, and use a similar method to step one to find out where that variable becomes undefined. Once you find this point, it should be fairly obvious to see why the variable became undefined (you did something like object.mass instead of object.traits.mass). Now that you have found this error, fix it and try again. If you cannot figure out why this is making your variable undefined, try step four with this line.

Step four: Finding what is wrong with a statement.
If you can pinpoint the statement that is giving you trouble, try to understand how the statement works. If it is a function from a library, then look up the library and make sure you are implementing it correctly. If it is a function somewhere else in your code, try using print statements to debug that function, starting with step two, or, if you prefer, use step six on this function.

Step five: Look online for solutions.
Lots of people write code, and odds are, someone else has had the same problem as you. Looking up the error that your code gave you on a website such as [Stack Overflow](https://stackoverflow.com/). If your error statement is not specific enough to help you find what you are looking for, look to the line in your code and see if you can come up with a better description of your problem after gaining a basic understanding of the error. Anyway, odds are someone else has had this problem, and another person has already helped them figure out how to fix it. If you can't find anything that matches your situation, move to step seven.

Step six: [Rubber duck debugging](https://en.wikipedia.org/wiki/Rubber_duck_debugging).
At this point, you have no clue what is going wrong, or even where to begin debugging. This trick also works if the problems with your code are deeper than a single line. Get an object or a friend that you can talk to, and, starting at the beginning, explain your code to them. If you are doing this with another person, allow them to make suggestions, as your error could be something simple that you are over looking. Explaining your code will help you review it, and can shed light onto logical errors. If this fails, but you have a basic understanding of your problem, move to step five. Otherwise, move to step seven.

Step seven: Ask the Internet for help.
The Internet may be filled with trolls, but it is also filled with intelligent minds that enjoy helping others with their problems. Using a site such as [Stack Overflow](https://stackoverflow.com/), ask people to help you with your problem. Before you do this, try to look around and see if you can find an answer for yourself. Provide all the information that you know, as well as the code that you think is broken. As a general guideline, be kind to people who respond to your question, as odds are they are trying to help you. If someone solves your problem for you, it would be polite to then look to see if they have any problems that you can help them with to return the favor. If you are not comfortable with asking people on the Internet, ask someone you know to help you. If you cannot get anyone else's help, try step eight.

Step eight: Refactor your code.
If your code is difficult to read, try renaming variables to be more logical. Often times, refactoring code can cause you to fix otherwise unnoticeable errors, such as misspelling a variable name. Also, clearing up your code can make it easier to pinpoint errors. Clean code is also easier for others to understand, making it easier for others to give you help. If this still fails to solve your problem, move to step nine.

Step nine: Rewrite your code.
If all else fails, delete the non working code, and rewrite it, making sure in each line that you introduce no potential bugs. This may be time consuming, but it will solve around 95% of debugging problems. If you can't pinpoint what code is problematic, you might want to rewrite all of your code from scratch. When rewriting your code, also take this time to make it more dynamic and efficient, improving scalability and runtime. Also, replace convoluted functions with simpler solutions, as simple solutions are often better, and tend to be easier to debug. As you complete each section of your code, run it to test for errors.

Step ten: Create a system to test for variables.
Whether you create an object that you can move with wasd to test collision detection, or add a line of code that allows you to tinker with variables at key points, forcing inputs can be a useful way to discover what situations cause your code to behave in undesirable ways. The ability to isolate a single variable or to test certain situations can help you figure out what works and what does not work, and thus the situation that causes your code to break. Once you have this figured out, it should be much easier to fix the error, as you know exactly what to look for in your code. If necessary, move to step six to help you figure out why that input is giving you an error.

The above guide to debugging is only a suggestion, and was written by me at 11:00 at night, and thus should be taken with a grain of salt. While the ideas I present are generally helpful, they are by no means the only or the best way to approach debugging. Actual debugging can often times uses a debugger, and tends to be a more dynamic process. Next time, I plan to tell you how I debugged the errors within my collision detection in my natural selection simulator.
