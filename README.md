**Program for CRC**

CRC : Cyclic Redundancy Check

A cyclic redundancy check (CRC) is an error-detecting code commonly used in digital networks and storage devices to detect accidental changes to digital data. Blocks of data entering these systems get a short check value attached, based on the remainder of a polynomial division of their contents.

To implement the algorithm for CRC error detection, the user is asked to provide a number representing how many bits will be contained in the messages we should check. We count  how many messages will be passed so that we can more reliably results. The messages we pass are determined by the variable N which is a fixed variable that does not change throughout the  program. We can test with many different N. 

These messages should start with a "1", because if they don't start with an "1", it will skip over all the zeros that are  at the beginning of the message. Then through the rand() function, we create random numbers with 0 and 1 so that we have a binary message.  

The bit table contains the message we want to send to the receiver  and check if it will be sent with an error in it. 

In order to be able to then divide the number that  is in the bit table , we place n-k zeros at the end of the number of Bit so as to obtain the 2n-k D shown below.
$$ T= 2^(n-k) *D + F %%
