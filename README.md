Download Link: https://assignmentchef.com/product/solved-fit2004-assignment-1-2
<br>
<h1>Learning Outcomes</h1>

This assignment achieves the Learning Outcomes of:

<ul>

 <li>1) Analyse general problem solving strategies and algorithmic paradigms, and apply them to solving new problems;</li>

 <li>2) Prove correctness of programs, analyse their space and time complexities;</li>

 <li>4) Develop and implement algorithms to solve computational problems.</li>

</ul>

In addition, you will develop the following employability skills:

<ul>

 <li>Text comprehension</li>

 <li>Designing test cases</li>

 <li>Ability to follow specifications precisely</li>

</ul>

<h1>Assignment timeline</h1>

In order to be successful in this assessment, the following steps are provided as a suggestion. This is an approach which will be useful to you both in future units, and in industry.

<h2>Planning</h2>

<ol>

 <li>Read the assignment specification as soon as possible and write out a list of questions you have about it.</li>

 <li>Clarify these questions. You can go to a consultation, talk to your tutor, discuss the tasks with friends or ask in the forums.</li>

 <li>As soon as possible, start thinking about the problems in the assignment.

  <ul>

   <li>It is strongly recommended that you do not write code until you have a solid feeling for how the problem works and how you will solve it.</li>

  </ul></li>

 <li>Writing down small examples and solving them by hand is an excellent tool for coming to a better understanding of the problem.

  <ul>

   <li>As you are doing this, you will also get a feel for the kinds of edge cases your code will have to deal with.</li>

  </ul></li>

 <li>Write down a high level description of the algorithm you will use.</li>

 <li>Determine the complexity of your algorithm idea, ensuring it meets the requirements.</li>

</ol>

<h2>Implementing</h2>

<ol>

 <li>Think of test cases that you can use to check if your algorithm works.

  <ul>

   <li>Use the edge cases you found during the previous phase to inspire your test cases.</li>

   <li>It is also a good idea to generate large random test cases.</li>

   <li>Sharing test cases is allowed, as it is not helping solve the assignment.</li>

  </ul></li>

 <li>Code up your algorithm, (remember decomposition and comments) and test it on the tests you have thought of.</li>

 <li>Try to break your code. Think of what kinds of inputs you could be presented with which your code might not be able to handle.

  <ul>

   <li>Large inputs</li>

   <li>Small inputs</li>

   <li>Inputs with strange properties</li>

   <li>What if everything is the same?</li>

   <li>What if everything is different?</li>

   <li>..</li>

  </ul></li>

</ol>

<h2>Before submission</h2>

<ul>

 <li>Make sure that the input/output format of your code matches the specification.</li>

 <li>Make sure your filenames match the specification.</li>

 <li>Make sure your functions are named correctly and take the correct inputs.</li>

 <li>Make sure you zip your files correctly</li>

</ul>

<h1>Documentation</h1>

For this assignment (and all assignments in this unit) you are required to document and comment your code appropriately. This documentation/commenting must consist of (but is not limited to)

<ul>

 <li>For each function, high level description of that function. This should be a one or two sentence explanation of what this function does. One good way of presenting this information is by specifying what the input to the function is, and what output the function produces (if appropriate)</li>

 <li>For each function, the Big-O complexity of that function, in terms of the input. Make sure you specify what the variables involved in your complexity refer to. Remember that the complexity of a function includes the complexity of any function calls it makes.</li>

 <li>Within functions, comments where appropriate. Generally speaking, you would comment complicated lines of code (which you should try to minimise) or a large block of code which performs a clear and distinct task (often blocks like this are good candidates to be their own functions!).</li>

</ul>

<h1>1            Sorting with radix sort</h1>

In this task you will be implementing radix sort. You will write a function radix_sort(num_list, b) which takes as input a list of numbers to be sorted, and a base. You need to sort those numbers using radix sort in the base specified by the second parameter.

<h2>1.1        Input</h2>

The first input to this task is a list containing positive integers. They will be in the range [1<em>,</em>2<sup>64 </sup>− 1]. The second input is an integer in the range [2<em>,</em>inf), which is the base you need to use in your radix sort.

Example:

b = 10, num_list contains the following:

[18446744073709551615,

18446744073709551614, 1,

11111111111111111111,

2111111111111111111, 311111111111111111]

<h2>1.2        Output</h2>

radix_sort will return a list of integers, sorted in ascending order. This list will contain the same integers as the input list. radix_sort should not modify the input list.

Example:

Calling radix_sort on the above example would return the list

[1,

311111111111111111,

2111111111111111111,

11111111111111111111,

18446744073709551614,

18446744073709551615]

Note that the output would be the same regardless of the base used, 10 is used here as an example.

<h2>1.3         Complexity</h2>

radix_sort must run in <em>O</em>((<em>N </em>+ <em>b</em>)<em>M</em>) time, where

<ul>

 <li><em>N </em>is the total number of integers in the input list</li>

 <li><em>b </em>is the base</li>

 <li><em>M </em>is the number of digits in the largest number in the input list, when represented in base b</li>

</ul>

<h1>2         Analysis</h1>

Since your function from task 1 allows you to vary the base used for radix sort, you will now test the effect that varying the base has on the run time of your algorithm. You will write a function time_radix_sort() which will create a list of numbers, and then call radix_sort on this list with different bases and record the times. Use this line of code (and the random module) to create your test data: test_data = [random.randint(1,(2**64)-1) for _ in range(100000)]

You should test your function for an appropriate range of bases. (it is up to you to think about what range of bases might be appropriate, but you should test a large range of values, and at least 5 different values)

In task2.pdf, discuss the results of this test. This documents must include

<ul>

 <li>An explanation of why you chose the bases that you did</li>

 <li>A graph showing the times obtained, along with the bases</li>

 <li>A written explanation of why you obtained the times that you did. Justify the times using your understanding of radix sort.</li>

</ul>

Remember to not include the creation of the test data in your timing. You should only be timing the running of your function from task 1.

2.1        Input

The function time_radix_sort() has no input.

<h2>2.2        Output</h2>

time_radix_sort() will produce a list of tuples as output. Each tuple will correspond to the time for one base, and will have two elements. The first element will be the base used, and the second will be the time in seconds.

Example:

Suppose that the bases tested were 2, 3 and 4 (note, this is not a good set of bases to test).

The return value of time_radix_sort() might (times may vary) be

[(2, 5.323850631713867),

(3, 3.4008474349975586),

(4, 2.6056511402130127)]

2.3         Complexity

There is no complexity requirement for this function.

<h1>3           Finding rotations</h1>

<h2>Background</h2>

This task is about rotations of strings. A left rotation of a string is when we take the leftmost character and place it on the right end of the string. For example, left rotating abcd gives us bcda. We can also rotate more than once. For example, left rotating abcd twice gives us cdab. We call this a “2-rotation”, and in general, when we rotate a number <em>p </em>places to the left, we call that an “<em>p</em>-rotation”.

<table width="138">

 <tbody>

  <tr>

   <td width="89">-1-rotation</td>

   <td width="49">dabc</td>

  </tr>

  <tr>

   <td width="89">original</td>

   <td width="49">abcd</td>

  </tr>

  <tr>

   <td width="89">1-rotation</td>

   <td width="49">bcda</td>

  </tr>

  <tr>

   <td width="89">2-rotation</td>

   <td width="49">cdab</td>

  </tr>

  <tr>

   <td width="89">3-rotation</td>

   <td width="49">dabc</td>

  </tr>

  <tr>

   <td width="89">4-rotation</td>

   <td width="49">abcd</td>

  </tr>

  <tr>

   <td width="89">5-rotation</td>

   <td width="49">bcda</td>

  </tr>

 </tbody>

</table>

In this task, you will be given a list of strings and a rotation size <em>p</em>. You need to find all the strings in the list whose <em>p</em>-rotations also appear in the list. To do this you will write a function find_rotations(string_list, p)

<h2>3.1        Input</h2>

The first input to this task, string_list is a list of strings. Each string in this list is unique. Strings in this list will only contain lowercase alphabet characters (a-z). p is the number of left-rotations. Negative p values correspond to right rotations.

Example:

p = 1, string_list contains

[“aaa”,

“abc”,

“cab”,

“acb”, “wxyz”,

“yzwx”]

<h2>3.2        Output</h2>

find_rotations will return a list of all string in string_list whose p-rotations also exist in string_list

Example:

Calling find_rotations on the above example would return

[“aaa”, “cab”]

To see why, first lets rotate all the strings one place left

aaa bca abc cba xyzw zwxy

The two rotated strings which appear in the original list are “aaa” and “cab”, so these are the two elements in the solution.

<h2>3.3         Complexity</h2>

find_rotations must run in <em>O</em>(<em>NM</em>), where

<ul>

 <li><em>N </em>is the number of strings in the input list</li>

 <li><em>M </em>is the maximum number of letters in a word, among all words in the input list</li>

</ul>