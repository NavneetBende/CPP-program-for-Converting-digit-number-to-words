# CPP-program-for-Converting-digit-number-to-words

Converting digit/number to words in C++
Here, in this page we will discuss the program for Digit/number to words in C++ .The conversion of numbers in words is just a conversion of numeric values to the English format of reading numbers. This code supports the conversion of numbers from 0 – 9999 in English format. Digits have different places when read from its ones place to above.

Digit/number to words in C++
Different places for numbers are:-
Single digits:- Ones
Two Digits:-Tens
Three Digits:- Hundreds
Four Digits:- Thousands
Algorithm
 Taking input as a string from the user.
 Check the length of the input.
 if the length is zero print ’empty’ and if the length is greater than 4 print ‘give a string of specific length’
 if length id between 1 – 4, Create arrays for different values.
 Checking the length of the string.
 According to the place of the digit, we will show the output.
Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

 
void
numToWords (string num)
{
  
 
int length_of_string = num.size ();
  
 
if (length_of_string == 0)
    {
      
cout << "String is Empty";
      return;
    }
  if (length_of_string > 4)
    {
      
cout << "Please enter the string with supported length";
      
return;
    
}
  
 
string ones_digits[] =
  {
  "zero", "one", "two", "three", "four", "five", "six", "seven", "eight",
      "nine"};
  
 
string tens_digits[] =
  {
  "", "ten", "eleven", "twelve", "thirteen", "fourteen", "fifteen",
      "sixteen", "seventeen", "eighteen", "nineteen"};
  
 
string multiple_of_ten[] =
  {
  "", "", "twenty", "thirty", "forty", "fifty", "sixty", "seventy",
      "eighty", "ninety"};
  
 
string power_of_ten[] =
  {
  "hundred", "thousand"};
  
 
cout << num << ":\n";
  
 
if (length_of_string == 1)
    {
      
cout << ones_digits[num[0] - '0'];
      
	//return;
    }
  
 
int x = 0;
  
 
while (x < num.size ())
    {
      if (length_of_string >= 3)
	{
	  
if (num[x] - 48 != 0)
	    {
	      
cout << ones_digits[num[x] - 48] << "\n";
	      
cout << power_of_ten[length_of_string - 3] << "\n";
	      
length_of_string--;
	    
}
	
}
      
      else
	{
	  
if (num[x] - 48 == 1)
	    {
	      
int sum = (num[x] - 48 + num[x] - 48);
	      
cout << tens_digits[sum];
	      
		// return;
	    }
	  
 
	  else if (num[x] - 48 == 2 and num[x + 1] - 48 == 0)
	    {
	      
cout << "twenty";	//
	      return;
	    }
	  else
	    {
	      int i = num[x] - 48;
	      if (i > 0)
		{
		  
cout << multiple_of_ten[i] << " ";
		
}
	      
	      else
		{
		  
cout << " ";
		
}
	      
x += 1;
	      
if (num[x] - 48 != 0)
		{
		  
cout << ones_digits[num[x] - 48];
		
}
	    
 
}
	
 
}
      
 
x++;
    
}

 
}


 
int
main ()
{
  
 
numToWords ("1121");
  
return 0;

 
}
Output:
1121 : one thousand one hundred twenty one
