Description:
This project has two parts, calc.c and format.c , and they were both aimed to help understand the C language and its funcitonality. Calc.c is a program that adds, subtracts, and multiplies two numbers in different bases (binary, octal, hexadecimal, decimal), then outputs the result in any base. Format.c is a program that prints the decimal values of bit sequences representing integer and floating point data types. 

Input format: calc <op> <number1> <number2> <output base>
op: The operation to be performed ( "+", "-" or "*" )
number 1/number 2: Numbers that can fit inside a "long". Each number is in format: (-) d/b/o/x # where a "-" indicates a negative number, the second character indicates the base, and # is the sequence of digits. 
output base: is in format: d/b/o/x . This argument can be one of four strings: “b” for binary, “o” for octal, “d” for decimal, and “x” for hexadecimal. 

Algorithm:
First, I check the command line and its arguments to make sure the proper number of arguments, proper operator, and proper output is entered. I copy the two whole strings and put them all in lower case for future use with the hexadecimal functions. Then, I send both strings to a function to check for validity of it being a proper type of number and for it actually being the type of number indicated. If it is an invalid number or the number and type do not match up, an appropriate error will appear. I also malloc space and initialize the type of the number after it has been verified at this point. I then put both strings into their own longs because a long is able to contain more digits and have more usability than an int and I also wanted to become familiar with using a long in the process. I then convert this number, regardless of its type, into a decimal. I do all operations of the numbers while it is in decimal form. Once i get the sum, product, or difference as a decimal value, I check if the result is negative or not then check what the output type should be and convert it into that type. Since the "-" sign must come before the type indicator in the output, if the number is a negative number, I negate it into a positive integer and output the answer with the negative sign in front inside of right in front of the number. I created a total of six conversion functions to convert between the 4 different bases. All octal, binary, and hexadecimal were the auxilliary bases while I functioned my whole program around using the decimal base. I had simple add, multiply, and subtract functions that took in decimal values and created the proper product, sum, or difference. My string converter function took a string and converted into type long. This function had the most problems because memory shortages occurred when testing larger numbers since not all the characters could be properly placed inside a long. Thus, there is a limit of what I perceived as 19 digits that can be placed safely inside the long. If more digits are given, the string converter may not convert properly. If I were to have instead used a string and to store the numbers, and done all operations not through the "+/-" operators but with operations on the ascii values of the corresponding digits, then I would have been able to handle arbitrarily large numbers. My functions for oct and binary, both to and from decimal, work similarly because they all use while loops to convert the dec/oct/binary value. However, the two hexadecimal functions are more time consuming because at the very least they both have nested for loops running through the length fo the numbers given. The decimal to hex value is even longer because I have to store them into a string. I treated hex values differently from the other three values because it could have characters in the number and letters cannot be stored in a long. So, throughout my program there were many times where I had to branch away from what the other three bases were doing to handle the hex values properly. 


