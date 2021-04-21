# Words-From-Phone-Digits
Print all possible words from phone digits

Before the advent of QWERTY keyboards, texts and numbers were placed on the same key. For example, 2 has “ABC” if we wanted to write anything starting with ‘A’ we need to type key 2 once. If we wanted to type ‘B’, press key 2 twice and thrice for typing ‘C’.

 1    ABC   DEF
       2     3
     
GHI   JKL   MNO
 4     5     6
 
PQRS  TUV  WXYZ
 *     0     #

Given a keypad as shown in the diagram, and an n digit number, list all words which are possible by pressing these numbers.
Example: 
 

Input number: 234
Output:
adg adh adi aeg aeh aei afg afh 
afi bdg bdh bdi beg beh bei bfg 
bfh bfi cdg cdh cdi ceg ceh cei 
cfg cfh cfi
Explanation: All possible words which can be 
formed are (Alphabetical order):
adg adh adi aeg aeh aei afg afh 
afi bdg bdh bdi beg beh bei bfg 
bfh bfi cdg cdh cdi ceg ceh cei 
cfg cfh cfi
If 2 is pressed then the alphabet
can be a, b, c, 
Similarly, for 3, it can be 
d, e, f, and for 4 can be g, h, i. 

Input number: 5
Output: j k l
Explanation: All possible words which can be 
formed are (Alphabetical order):
j, k, l, only these three alphabets 
can be written with j, k, l. 
Recommended: Please solve it on “PRACTICE” first, before moving on to the solution.
Approach: It can be observed that each digit can represent 3 to 4 different alphabets (apart from 0 and 1). So the idea is to form a recursive function. Then map the number with its string of probable alphabets, i.e 2 with “abc”, 3 with “def” etc. Now the recursive function will try all the alphabets, mapped to the current digit in alphabetic order, and again call the recursive function for the next digit and will pass on the current output string.
Example: 

If the number is 23,

Then for 2, the alphabets are a, b, c
So 3 recursive function will be called 
with output string as a, b, c respectively 
and for 3 there are 3 alphabets d, e, f
So, the output will be ad, ae and af for 
the recursive function with output string.
Similarly, for b and c, the output will be: 
bd, be, bf and cd, ce, cf respectively.

Algorithm:  

  * Map the number with its string of probable alphabets, i.e 2 with “abc”, 3 with “def” etc.
  * Create a recursive function which takes the following parameters, output string, number array, current index, and length of number array
  * If the current index is equal to the length of the number array then print the output string.
  * Extract the string at digit[current_index] from the Map, where the digit is the input number array.
  * Run a loop to traverse the string from start to end
  * For every index again call the recursive function with the output string concatenated with the ith character of the string and the current_index + 1.
