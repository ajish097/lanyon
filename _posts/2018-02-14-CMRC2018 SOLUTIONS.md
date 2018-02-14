---
layout: post
comments: true
title: CMRC2018 SOLUTIONS
link: https://www.codechef.com/CMRC2018
---

## [Reverse Case](https://www.codechef.com/problems/REVCASE)

[Author - Aadith Menon](https://github.com/adithm)

PROBLEM: Given a string S, convert all the uppercase letters to lowercase and all lowercase letters to uppercase.

SOLUTION:
We check if the ith character is lowercase and if it is, we convert it to upper case as shown

if (S[i] >= 'a' && S[i] <= 'z') {
  S[i] = toupper(S[i]);
}

Here, we used a built in C function 'toupper' to convert the character to upper case. We can also do this
manually by observing the ASCII values of upper and lower case characters. 
ASCII value for 'A' is 65 and for 'a' is 97. The difference is 32. So if we subtract 32 from lowercase
characters, we'll convert them to uppercase as show

S[i] = S[i] - 32;

The same concept can be applied to convert uppercase characters to lowercase.

if (S[i] >= 'A' && S[i] <= 'Z') {
  S[i] = tolower(S[i]);
  // or S[i] = S[i] + 32;
}

The complete solution in C++ is given below

<script src="https://gist.github.com/ajish097/2e87276cf0db680e5fbdfaf393dbc515.js"></script>


<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />

## [Large Products](https://www.codechef.com/problems/ANUPROD)

[Author - Aadith Menon](https://github.com/adithm)

PROBLEM: Given N positive integers, print the product of all the numbers Modulo 10^9+7.

SOLUTION: Let us first understant why a naive solution might not work. 
We might be tempted to simply multiply all the numbers and then finally compute the modulo. i.e

// let's assume the N positive integers are stored in array inp[], and mod stores 10^9+7;
long long ans = 1, mod = 1000000007;
for (int i = 0; i < N; i++) {
  ans = ans * inp[i];
} 
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
  (inp[0] * inp[1] * inp[2] * ... * inp[N - 1]) % mod = (((inp[0] * inp[1]) % mod * inp[2]) % mod ... * inp[N - 1]) % mod

long long ans = 1;
for (int i = 0; i < N; i++) {
  ans = (ans * inp[i]) % mod;
}

The complete solution in C++ is given below

<script src="https://gist.github.com/ajish097/c0ee30b066d3f9d5762bed04e9cc8945.js"></script>

<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />