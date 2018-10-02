---
layout: post
comments: true
title: CMRC2018 SOLUTIONS
link: https://www.codechef.com/CMRC2018
---

## [Reverse Case](https://www.codechef.com/problems/REVCASE)

PROBLEM: Given a string S, convert all the uppercase letters to lowercase and all lowercase letters to uppercase.

SOLUTION:
We check if the ith character is lowercase and if it is, we convert it to upper case as shown

```C
if (S[i] >= 'a' && S[i] <= 'z') {
  S[i] = toupper(S[i]);
}
```

Here, we used a built in C function 'toupper' to convert the character to upper case. We can also do this
manually by observing the ASCII values of upper and lower case characters. 
ASCII value for 'A' is 65 and for 'a' is 97. The difference is 32. So if we subtract 32 from lowercase
characters, we'll convert them to uppercase as show

```C
S[i] = S[i] - 32;
```

The same concept can be applied to convert uppercase characters to lowercase.

```C
if (S[i] >= 'A' && S[i] <= 'Z') {
  S[i] = tolower(S[i]);
  // or S[i] = S[i] + 32;
}
```

The complete solution in C++ is given below

<script src="https://gist.github.com/ajish097/2e87276cf0db680e5fbdfaf393dbc515.js"></script>


<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />

## [Large Products](https://www.codechef.com/problems/ANUPROD)

PROBLEM: Given N positive integers, print the product of all the numbers Modulo 10^9+7.

SOLUTION: Let us first understand why a naive solution might not work. 
We might be tempted to simply multiply all the numbers and then finally compute the modulo. i.e

// let's assume the N positive integers are stored in array inp[], and mod stores 10^9+7;

```C
long long ans = 1, mod = 1000000007;
for (int i = 0; i < N; i++) {
  ans = ans * inp[i];
}
```

ans = ans % mod;

However, looking at the constraints of the question confirms that this doesn't work.
It is mentioned that N can go upto 10^3 and every integer can also go upto 10^3
So, in the worst case, the product of all N numbers can go upto (10^3)^(10^3) = 10^3000
This is too large. 

We must use the the multiplication property of modular arithmetic:
  (A * B) % C = (A % C * B % C) % C
The proof for this can be found here:
  https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/modular-multiplication

So applying this concept on inp[],

```
(inp[0] * inp[1] * inp[2] * ... * inp[N - 1]) % mod = (((inp[0] * inp[1]) % mod * inp[2]) % mod ... * inp[N - 1]) % mod
```
```C
long long ans = 1;
for (int i = 0; i < N; i++) {
  ans = (ans * inp[i]) % mod;
}
```

The complete solution in C++ is given below

<script src="https://gist.github.com/ajish097/c0ee30b066d3f9d5762bed04e9cc8945.js"></script>

<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />

## [Baga and Prime Numbers](https://www.codechef.com/CMRC2018/problems/BAGAPRIM)

[Author - Ajish](https://github.com/ajish097)

PROBLEM: Given l and r. Print the number of prime numbers between them.

SOLUTION: The naive approach would be to calculate if each number is prime by dividing it by [2 to sqrt(number)] and checking if there are more than factor of that number.

Let's optimize it by using an algorithm known as [Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes). 
Let's initilize an array of size 10^6 as 0. The idea is to eliminate all the factors of every number from 2-sqrt(10^6) by making index of each factor as 1 in the array. Please refer to this links for more info [link1](https://www.youtube.com/watch?v=eKp56OLhoQs) [link2](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)

Now, we can iterate from l-r and check if the array value is 0. If it is the case, we can say that the number is prime.

The complete solution in C++ is given below

<script src="https://gist.github.com/ajish097/9ba830e9254e319b99878306d032f5f8.js"></script>

<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />

## [Treasure Hunt](https://www.codechef.com/CMRC2018/problems/THC1)

[Author - Ajish](https://github.com/ajish097)

PROBLEM: Print YES if num divisible by 8 else print NO.

SOLUTION: The problem in this question is the inability of C++ to handle large numbers. Therefore, we can use divisibility of 8 which states that a number if divisible by 8 if the last 3 digits are divisible by 8.

The complete solution in C++ is given below

<script src="https://gist.github.com/ajish097/f93b2e0241245d0528a9d4ed459a4609.js"></script>

Or you could use python which can handle large numbers easily. 

```python
#author - Ajish
from sys import stdin as inp  
for i in range(int(inp.readline())):
  num = int(inp.readline())
  if(num%8==0):
    print("YES")
  else:
    print("NO")
```

<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />

## [Chef and Game with Sequence](https://www.codechef.comproblems/L56GAME)

[Author - Ajish](https://github.com/ajish097)

PROBLEM: Print the minimum size of the given array based on given condition in the problem

SOLUTION:
We can just add all the elements and check if the sum is even or odd. If it is even print 1 else 2.

The complete code in c++ is given below

<script src="https://gist.github.com/ajish097/55ee214cd0147f93d21073dfdaca9aa1.js"></script>

<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />
