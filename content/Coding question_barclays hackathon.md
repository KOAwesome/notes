**Implement the following Function:**

def differenceofSum(n. m)

The function accepts two integers n, m as arguments Find the sum of all numbers in range from 1 to m(both inclusive) that are not divisible by n. Return difference between sum of integers not divisible by n with sum of numbers divisible by n.

**Assumption:**

- n>0 and m>0
- Sum lies between integral range

**Example**

**Input  
**n:4  
m:20  
**Output  
**90

**Explanation**

- Sum of numbers divisible by 4 are 4 + 8 + 12 + 16 + 20 = 60
- Sum of numbers not divisible by 4 are 1 +2 + 3 + 5 + 6 + 7 + 9 + 10 + 11 + 13 + 14 + 15 + 17 + 18 + 19 = 150
- Difference 150 – 60 = 90

**Sample Input  
**n:3  
m:10  
**Sample Output  
**19

  

  

**Question 2 : Elements of Matrix**

**Problem Statement** 

You are required to input the size of the matrix then the elements of matrix, then you have to divide the main matrix in two sub matrices (even and odd) in such a way that element at 0 index will be considered as even and element at 1st index will be considered as odd and so on. then you have sort the even and odd matrices in ascending order then print the sum of second largest number from both the matrices

**Example**

- **enter the size of array** : 5
- **enter element at 0 index** : 3
- **enter element at 1 index :** 4
- **enter element at 2 index** : 1
- **enter element at 3 index :** 7
- **enter element at 4 index** : 9

Sorted even array : 1 3 9  
Sorted odd array : 4 7

7

  

**Problem Statement  :**

Semester exams are going on for university students. Examiners noticed that a group of people are trying to cheat. They marked students of that group as ‘1’ and students of another group ( who are not cheating ) as ‘0’ 

We can reduce cheating by not allowing students from group 1 to sit together, means no two students from group 1 can sit together. Seatings are marked using above conditions. Your task is to give the seating placement of nth possibility Possibility order from 1 to 10 is given below

**[1  10  100  101  1000  1001  1010  10000  10001  10010]**

**Sample input :**

3 → number of test cases

4

6

9

**Sample output :**

101

1001

10001

**Explanation :**

4th possibility is 101 

6th possibility is 1001

9th possibility is 10001

  

  

**Problem Statement  :**

Sahil watches TV all day and gets bored. He started playing this dumb game of identifying minimum number of inputs needed to reach a channel. As his cousin, you have to help him, but you live far from his house. So you decide to write a code that will ask Sahil for some inputs and give outputs respectively.

**Here are the problems you need to keep in mind :**

- There are 13 buttons on his remote: 10 buttons for the numbers (0-9) to form integers denoting respective channel index, “Up channel” button and “ Down channel” button for going i +1th channel and i-1th channel from i respectively, and a “Last viewed” button to see what’s the last channel before it.
- The number buttons allow you to jump directly to a specific channel (Ex: to go to channel 172 by typing 1,7,2).
- If the channel which you are in is ith and that is the max channel index possible, by Up channel, you will reach the first channel possible. Same goes for the down channel button. You can go to the highest channel possible if you go down from the lowest channel possible.
- Sahil can get from one channel to the next in one of the two ways.
- Sahil’s parents have set some parental control on some channels on Aniruth’s television. The “Up Channel “ and “Down buttons” buttons skip these channels as these channels are not viewable.
- Given a list of channels to view, the lowest channel, the highest channel, and a list of blocked channels, your program should return the minimum number of clicks necessary to get through all the shows that Anirudh would like to match.

**Input Format :**

- First line is the lowest Channel
- Second-line is the highest Channel
- Followed by a number of blocked channels B,  
    and the next B lines contain the actual blocked channels.
- Followed by the number of Channels to view V, and the next V lines contain the actual channels to view.

**Constraints :**

- The lowest channel on the television will be greater than 0. and less than or equal to 10,000.
- The highest channel on the television will be greater than or equal to the lowest channel. and less than or equal to 10.000.
- The list of channels that are blocked on Anirudh’s television. All the channels in this list will be valid channels (greater than or equal to lowest channel, less than or equal 1 to highest channel). Duplicates may be Ignored. The blocked list can be a maximum of 40 channels.
- The sequence that Sahil must view contains between 1 and 50 elements. inclusive. All channels in this sequence are not in the blocked list and are between lowest channel and highest channel. Inclusive.

**Sample Input 0:**  
1  
20  
2  
18  
19  
5  
15  
14  
17  
11  
17  
**Sample output 0:**  
8