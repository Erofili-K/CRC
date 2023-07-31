**Program for CRC**

CRC : Cyclic Redundancy Check

A cyclic redundancy check (CRC) is an error-detecting code commonly used in digital networks and storage devices to detect accidental changes to digital data. Blocks of data entering these systems get a short check value attached, based on the remainder of a polynomial division of their contents.

To implement the algorithm for CRC error detection, the user is asked to provide a number representing how many bits will be contained in the messages we should check. We count  how many messages will be passed so that we can more reliably results. The messages we pass are determined by the variable N which is a fixed variable that does not change throughout the  program. We can test with many different N. 

These messages should start with a "1", because if they don't start with an "1", it will skip over all the zeros that are  at the beginning of the message. Then through the rand() function, we create random numbers with 0 and 1 so that we have a binary message.  

The bit table contains the message we want to send to the receiver  and check if it will be sent with an error in it. 

In order to be able to then divide the number that  is in the bit table , we place n-k zeros at the end of the number of Bit so as to obtain the 2n-k D shown below.

 T= 2^(n-k) *D + F  

T is the sequence of n bits to be transmitted from the transmitter to the  receiver, and helps us find the CRC and whether errors have occurred in the message. We then create the table P , which denotes the predefined  number of n-k+1 bits by which the sequence T should be divisible.

P = 110101 by  daufault in this project.

Since we have these two numbers ( P and the message of the bit table with the  zeros we added at the end) we can do the division to find 
the CRC. We find the CRC through division in the way shown in the code. Once we find the CRC, then we add it to the end of the original message of the  bit table (in the p positions before we had zeros at the end) and thus create the  Transmitted message.

Then the transmission of the transmitted message (message and CRC) must pass through a noise channel with Bit Error Rate (BER) and get the  "corrupted" message to the receiver. We copy the transmitted message to a new table (temp2) and this will be passed as an argument to the function I constructed for the  ber (function : Noisemess). As ber I take the one in the pronunciation of the task,  which is 10^-3 (0.001). This means that the probability of changing a bit of the message  is 0.001. With rand() we randomly take a number from 0-1000 and pass it as  argument to the function, and the last argument is the size of the message.

The Noisemess function randomly chooses a number between 0-1000 and if it manages to "pick" the same number as the argument we passed( see: ber) then it goes to the bit of the transmitted message and changes it. If it is 0 it becomes 1 and if it is  is 1, it becomes 0.
 
Once it is done with the message it returns to main again and the tep2 table contains  the corrupted message. Next we need to check if there are indeed changes between the  transmitted message (bit table) and the corrupted message (table temp2). We get a variable count that will count whether a message has been changes. If count remains 0 , then it has not been altered. At the end it adds the count to a 
 totalcount variable that counts the counts from all messages. Ο This count is for all messages that have been altered. We then redo the division to find how many error messages will  theCRC will detect. This time we take the temp2 table containing the  corrupted message and P If the result of the division is 0 then either or not  an alteration has occurred or the CRC has not detected it. We check whether it has detected  error and if it has found one then add 1 to the variable c2 which counts  how many error messages the crc detects. Finally we display the percentages.

 
