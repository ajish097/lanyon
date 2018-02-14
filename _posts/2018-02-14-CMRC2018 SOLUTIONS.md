---
layout: post
comments: true
title: CMRC2018 SOLUTIONS
link: https://www.codechef.com/CMRC2018
---

[Reverse Case](https://www.codechef.com/problems/REVCASE)

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