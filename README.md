Download Link: https://assignmentchef.com/product/solved-csc3320-lab-8
<br>
<span class="kksr-muted">Rate this product</span>

Purpose: Learn how to use debugger in gdb to debug a program in Unix.

Part 1:

You are given a C program “q1.c” as below. But since there are no enough comments in the program, it is hard to find out the feature of the function foo. So let us trace the execution of the program and find out what foo does. Please follow the steps below and answer the questions accordingly.

<pre> #include &lt;stdio.h&gt;</pre>

<pre> int foo(int num) {</pre>

<pre>     int rev_num = 0;     while (num &gt; 0)     {</pre>

<pre>         rev_num = rev_num*10 + num%10;</pre>

<pre>         num = num/10;     }</pre>

<pre>     return rev_num; }</pre>

<pre> /* Driver program to test foo */ int main() {</pre>

<pre>     int num = 1125;     printf("Result is %d", foo(num));     return 0;</pre>

}

1) Compile “q1.c” with –g option so that we can debug the executable using gdb. $gcc -o q1 -g q1.c

2) Lauch gdb for “q1”. $gdb q1

3) List the source code of “q1.c” from line 1.

(gdb)list 1

4) Set a breakpoint at the line of statement “while (num &gt; 0)”.

Question: Write your command.

1

4) Run the program until the first breakpoint.

Question: Write your command.5) Use display to show the value of rev_num and num at each time when

program stops.

<pre>(gdb)display rev_num(gdb)display num</pre>

6) Run the while loop step by step using command n multiple times. (gdb)n

Question: check the value of rev_num and num after each iteration and fill in the table below.

1st iteration2nd iteration3rd iteration4th iteration num 112

rev_num 5

7) When the program terminates, quit gdb using command q. (gdb)q

8) Question: Now can you tell what the function foo does?

Part 2:

You are given a C program “q2.c” as below. This program is used to calculate the

average word length for a sentence (a string in a single line):

<pre>Enter a sentence: It was deja vu all over again.Average word length: 3.4</pre>

For simplicity, the program considers a punctuation mark to be part of the word to which it is attached. And it displays the average word length to one decimal place.

1 3

5 6 7

9

2 4

8

<pre>#include &lt;stdio.h&gt;int main() {</pre>

<pre>    int letters;    int words;    char character;</pre>

<pre>    printf("Enter a Sentence: ");</pre>

2

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<pre>10111213141516171819202122232425</pre>

<pre>while((character=getchar()) != 
){        if(character != ' '){</pre>

<pre>            if(!space){                words++;                space=1;</pre>

}

<pre>            letters++;      }else</pre>

space = 0; }

<pre>    printf("Average word length : %.1f", letters/words);</pre>

return 0; }

However, there are multiple errors in the given C program. Please correct complier errors and use gdb to debug the program and find out the errors.