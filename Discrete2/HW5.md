<h1 align="center"> Discrete Mathematics II - Homework #5 </h1>
<h2 align="center"> Justin Costenbader - jcost344@live.kutztown.edu </h2>
<h3 align="center"> November 21, 2023 </h3>
<p>
<br>
<br>
</p>

### 1. Use the definition of “ f(x) is O(g(x)) " to show that 2<sup>x</sup> + 17 is O(3<sup>x</sup>).

### 2. Show that (x<sup>2</sup>+1)/(x+1) is O(x).

### 3. Use a merge sort to sort 4, 3, 2, 5, 1, 8, 7, 6 into increasing order. Show all the steps used by the algorithm.

```mermaid
graph TD;
s1[4 3 2 5 1 8 7 6] --> s2[4 3 2 5]
s1 --> s3[1 8 7 6]

s2 --> s4[4 3]
s2 --> s5[2 5]
s3 --> s6[1 8]
s3 --> s7[7 6]

s4 --> s8[4]
s4 --> s9[3]
s5 --> s10[2]
s5 --> s11[5]
s6 --> s12[1]
s6 --> s13[8]
s7 --> s14[7]
s7 --> s15[6]

s8 --> m1[3 4]
s9 --> m1
s10 --> m2[2 5]
s11 --> m2
s12 --> m3[1 8]
s13 --> m3
s14 --> m4[6 7]
s15 --> m4

m1 --> m5[2 3 4 5]
m2 --> m5
m3 --> m6[1 6 7 8]
m4 --> m6

m5 --> m7[1 2 3 4 5 6 7 8]
m6 --> m7
```

### 4. Re-do problem 3 with a quick sort.
<p>
Five levels of recursion are required:
<br>  
1 2 3 (4) 5 8 7 6 ,
<br>
(1) 2 3 [4] (5) 8 7 6 ,
<br>
[1] (2) 3 [4] [5] 6 7 (8) ,
<br>
[1] [2] (3) [4] [5] (6) 7 [8] ,
<br>
[1] [2] [3] [4] [5] [6] (7) [8]
</p>
