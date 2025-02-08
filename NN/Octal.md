What is 4365 - 3412 when these values represent signed 12-bit octal numbers stored in sign-magnitude format? The result should be written in octal. Show your work.

[5 What is 4365 - 3412 when these v... [FREE SOLUTION] | Vaia](https://www.vaia.com/en-us/textbooks/computer-science/computer-organization-and-design-hardwaresoftware-interface-5th/arithmetic-for-computers/5-what-is-4365-3412-when-these-values-represent-signed-12-bi/)

## 1. Define sign-magnitude format

In the sign-magnitude format, the MSB is used to represent the sign of a number, and the remaining bits represent the magnitude of the number. Therefore, just add the sign bit to the left of the unsigned binary number. This representation is similar to the representation of signed decimal numbers.



## 2. Convert (4365)8 into a binary number

The first number is (4365)8= (100 011110 101)2

The number is in signed magnitude form and the first bit is 1, So the number is a negative number

Now, the actual value in negative decimal is (000 011110 101)2

(000 011110 101)2= (-245)10

The first number is (-245)10


## 3. Convert (3412)8 into a binary number

The second number is (3412)8= (011100 001010)2

The number is in signed magnitude form and the first bit is 0, So the number is a positive number

Now, the actual value in positive decimal is (011100 001010)2= (1802)10

Therefore,

-245-1802 = -2047

-2047 is negative, So the first bit of the result is 1 in binary conversion.

Then, it’s magnitude is (2047)10

Now, (2047)10= (11111111111)2

It is given in the question that the number is in 12-bit format and as we know the given number is the negative number, so we add 1 at MSB.


question 7
[Q7E Assume 185 and 122 are signed 8-... [FREE SOLUTION] | Vaia](https://www.vaia.com/en-us/textbooks/computer-science/computer-organization-and-design-hardwaresoftware-interface-5th/arithmetic-for-computers/q7e-assume-185-and-122-are-signed-8-bit-decimal-integers-sto/)
