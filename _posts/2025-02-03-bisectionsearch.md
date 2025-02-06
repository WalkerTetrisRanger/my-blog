---
layout: post
title: Bisection Search in Python
date: 2025-02-03 11:00:00 +1000
categories: python, MIT
---

#BISECTION SEARCHING - LECTURE 6 (MIT 600L)


Recap from lecture 5: 
-floating point numbers are hard for approximation.
- can't be represented as exact values in memory.
    + operations on these approxiamted floats introduce tiny areas.
    + errors are quickly magnified over the course of a few operations...
- guess and check: enumerates ints(integers) one at a time and checks if the solution is correct. 
- *approximation methods* enumerate using a float increment. 
    + checking a solution is not possible.
    + checking whether a solution yields a *value within epsilon* is possible.
    

###what is besection search?

apply it to ***problems with an inherent order*** to the range of possible answers. 
e.g. we know that the answer lies inside an interval between numbers...
    + guess ***midpoint*** of interval.
    + if not the answer, check if ***answer is greater than or less than*** midpoint. 
    + ***change*** interval (new interval between midpoint and boundary (high or low). 
    + repeat
    
This process ***cuts set of things to check in half*** at each step.
    - exhaustive searching reduces the number of objects to check by n-1 each step.
    - bisection search reduces them from N to N/2.
   
   
##Recall the approximation method code to find the square root  
  
```
# x = 54321
# epsilon = 0.001
# num_guesses = 0
# guess = 0.0
# increment = 0.00001   # try it with 0.00001
# while abs(guess**2 - x) >= epsilon and guess**2 <= x:
#     # abs(guess**2 - x) >= epsilon finds a "good enough" answer
#     # guess**2 <= x ensures we stop looking when the guess becomes unreasonable
#     guess += increment
#     num_guesses += 1
# print(f'num_guesses = {num_guesses}')

# # this "if" is for the case when we stopped the loop due to an unreasonable guess
# if abs(guess**2 - x) >= epsilon:
#     print(f'Failed on square root of {x}')
#     print(f'Last guess was {guess}')
#     print(f'Last guess squared is {guess*guess}')
# # this "else" is for the case when we stopped the loop due to being within epsilon of x
# else:
#     print(f'{guess} is close to square root of {x}')
```

##BISECTION ALGORITHM 

```
#####################
## EXAMPLE: fast square root using bisection search
#####################

x = 54321  # try 0.5
epsilon = 0.01
num_guesses = 0
low = 0.0
high = x
guess = (high + low)/2

while abs(guess**2 - x) >= epsilon:
    # uncomment to see each step's guess, high, and low 
    #print(f'low = {str(low)} high = {str(high)} guess = {str(guess)}')
    if guess**2 < x:
        low = guess
    else:
        high = guess
    guess = (high + low)/2.0
    num_guesses += 1
print(f'num_guesses = {str(num_guesses)}')
print(f'{str(guess)} is close to square root of {str(x)}')

```

On of the finger exercises was to write a bisection search that would find the cube root of any given number...

```
cube = 27
epsilon = 0.0000000000001
low = 0
high = cube
guess = (high+low)/2
num_guess = 0

while abs(guess**3 - cube) >= epsilon: 
    print(f'low = {low} high = {high} guess = {guess}')
    if guess**3 < cube:
        low = guess 
    else: 
        high = guess
    guess = (high+low)/2
    num_guess += 1
print(f'{guess} is close to cube root of {cube}')
print(f'guesses made:{num_guess}')
```

Initially I had an infinite loop and realised that I had made an error and was not bisecting the search results...realised by imbedding the print function within the while loop.  
Apparently there is another way to achieve the same results...

```
########################
## EXAMPLE: Newton-Raphson to find roots
######################
# epsilon = 0.01
# k = 24  # try 54321
# guess = k/2.0
# num_guesses = 0

# while abs(guess*guess - k) >= epsilon:
#     num_guesses += 1
#     guess = guess - (((guess**2) - k)/(2*guess))
# print(f'num_guesses = {str(num_guesses)}')
# print(f'Square root of {str(k)} is about {str(guess)}')
```


