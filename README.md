Problem Description  
Determine which of the 26 characters consisting of a-z has the most characters
Input: Line 1 is the number of groups of test data n, each group of test data occupies 1 line, is a 26-character group by a-z
a string of data between each set of test data, each line of data does not exceed 1000 characters and is not empty
Output: n lines, one output per line corresponds to one input. One line of output includes the most frequently occurring character and the occurrence of that character
The number of times is a space in the middle. If multiple characters appear the same number and the most, then the output ascii code is the smallest
That one character.  

Input sample  
2  
Abbccc  
Adfadffasdf  

Output sample  
c 3  
f 4  

problem analysis  
Each time a string is read, the string is treated as a character array, and each letter of the array element is determined in turn. Count how many times each letter appears in the string and find the most occurrences. Here are three things to note:
(1) When entering a string, you can enter a string at a time like a normal variable. Scanf function via a space or
The carriage return character determines the end of a string. When a general array is input, only one array element can be input at a time.
Prime.
(2) A string is a character array that can be accessed by subscripts as if it were an element of a general array. When the scanf function enters a string, it does not return the length of the input string. Can use string
The handler strlen function calculates how many characters are included in the string.
(3) In the input string, there may be multiple characters appearing the same number of times and the most. At this point, output the character with the smallest ascii code.
  
solution  
Choosing the right data structure is the key to keeping the code simple, easy to read, and efficient. The maximum length of the input string is 1000 characters. To store such a string requires a character array str of length 1001, where the last element of the array stores the end of the string '\0'. Defines a special integer array sum of length 26, recorded in an input string, and the number of occurrences of each letter. The number of occurrences of the letter c is recorded in the array element sum[c-'a'].  

Common mistakes  
(1) Define the length of the array str as 1000 instead of 1001, ignoring the end of the string, adding an extra flag character '\0' indicating the end of the string. Pay special attention when dealing with strings: When storing a string of length N, the length of the character array used must be greater than or equal to N+1.  
(2) Lines 15~17 of the program determine which character has the most occurrences in the input string. In the problem description, when multiple characters are required to appear the same number of times and the maximum number of characters, the minimum character of the ascii code must be output. Often in the programming, the 17th line judgment condition sum[i]>sum[max] is replaced by sum[i]sum[max], which will result in an error: multiple characters appear the same number of times and the most , max indicates that it will be the largest character of the ascii code.
