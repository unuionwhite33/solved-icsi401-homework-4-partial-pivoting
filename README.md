Download Link: https://assignmentchef.com/product/solved-icsi401-homework-4-partial-pivoting
<br>
<h1>4.1       Partial pivoting</h1>

In this problem, you will review partial pivoting and the reasoning behind it.

<ol>

 <li>Circle the best explanation for the use of partial pivoting from the choices below.

  <ul>

   <li>Partial pivoting is used in Gaussian elimination to mitigate the effects of rounding errors in the matrix entries, resulting in an algorithm that is usually backward stable.</li>

   <li>Partial pivoting is not used in Gaussian elimination at all, but is instead used to solve linear systems via Cramer’s rule.</li>

   <li>Partial pivoting is used to transform the input to Gaussian elimination so as to speed up the solution of linear systems.</li>

  </ul></li>

 <li>Show the steps of Gaussian elimination with partial pivoting for the following matrix:</li>

</ol>

<table width="348">

 <tbody>

  <tr>

   <td width="56">10−52−1</td>

   <td width="32">1−31</td>

   <td width="230"></td>

   <td width="30">(4.1)</td>

  </tr>

 </tbody>

</table>

Make sure that you clearly indicate in each step what operation you are performing (e.g., which rows are swapped, which multiples of rows are added to which other rows) and the result of that operation. You should end up with an upper triangular matrix.

<h1>4.2        Least squares and curve fitting</h1>

This problem will give you practice in using least squares to fit polynomials to data. Consider the following dataset in Matlab, consisting of pairs of points (<em>x,y</em>):

4-1

4-2                                                   Homework 4: ICSI 401 – Numerical Methods

<ul>

 <li>= [-3, -2, -1, 0, 1, 2, 3]’;</li>

 <li>= [-12.529999999999999, -3.02, 0.49, 1.00, 1.51, 5.02, 14.529999999999999]’;</li>

</ul>

Suppose that you want to find a least squares fit of a degree-3 polynomial to this data. I.e., you want to determine coefficients <em>c</em><sub>0</sub><em>,c</em><sub>1</sub><em>,c</em><sub>2</sub><em>,c</em><sub>3 </sub>such that <em>c</em><sub>3</sub><em>x</em><sup>3 </sup>+ <em>c</em><sub>2</sub><em>x</em><sup>2 </sup>+ <em>c</em><sub>1</sub><em>x </em>+ <em>c</em><sub>0 </sub>is a least-squares fit to the data. We will collect the coefficients into a vector <em>~c</em><sub>∗ </sub>= [<em>c</em><sub>0</sub><em>,c</em><sub>1</sub><em>,c</em><sub>2</sub><em>,c</em><sub>3</sub>]<em><sup>T</sup></em>.

<ol>

 <li>Using Matlab, compute the Vandermonde matrix <em>A </em>associated with this problem and explain how you got it. Remember that least squares requires us to solve</li>

</ol>

<em>~c</em><sub>∗ </sub>= argmin<em>.                                                               </em>(4.2)

<strong>Hint: </strong>In Matlab, if you have some number of column vectors <em>a,b,c… </em>of the same length, then you can put them into a matrix as follows:

A = [a , b , c];

Furthermore, you can generate a column vector of all ones with a given length <em>l </em>by writing

ones(l)

Finally, given a vector <em>x</em>, you can raise each of its elements to a given power <em>a </em>by writing x.^a

<ol start="2">

 <li>In Matlab, use the <em>A </em>that you computed and the <strong>normal equations </strong>approach to the least squares problem to compute the vector of coefficients <em>~c</em>.</li>

 <li>In Matlab, use the <em>norm </em>function to compute the the error .</li>

</ol>

<strong>For this problem, you are expected to turn in all Matlab code that you’ve written, and clearly indicate your final answers.</strong>

<h1>4.3          Eigenthings and the power method</h1>

<ol>

 <li>Using Matlab, use the power method to calculate unit eigenvectors corresponding to the dominant two eigenvalues of the matrix</li>

</ol>

<table width="342">

 <tbody>

  <tr>

   <td width="45"> 62−1</td>

   <td width="21">2 5 1</td>

   <td width="247"></td>

   <td width="30">(4.3)</td>

  </tr>

 </tbody>

</table>

In particular, you should run the power method for 50 iterations.

As usual, include your Matlab code and output. Clearly indicate the two eigenvectors that are your final answer.

<strong>Hint: </strong>Think about how you might check your answer to make sure it’s accurate. You know that an eigenvector <em>v </em>must satisfy <em>Av </em>= <em>λv </em>for some <em>λ</em>, so one idea is to compute <em>w </em>= <em>Av </em>and make sure that <em>w</em><sub>1</sub><em>/v</em><sub>1 </sub>= <em>w</em><sub>2</sub><em>/v</em><sub>2 </sub>= <em>w</em><sub>3</sub><em>/v</em><sub>3</sub>.

Homework 4: ICSI 401 – Numerical Methods                                                   4-3

<h1>4.4         Polynomial interpolation, Chebyshev points</h1>

<ol>

 <li>In general, if we are given points (<em>x</em><sub>0</sub><em>,y</em><sub>0</sub>)<em>,…,</em>(<em>x<sub>n</sub>,y<sub>n</sub></em>), what is the minimum number <em>d </em>such that a unique polynomial with degree 6 <em>d </em>and passing through these points is guaranteed to exist?</li>

 <li>Let <em>x</em><sub>0 </sub>= −1<em>,x</em><sub>1 </sub>= 1<em>,x</em><sub>2 </sub>= 2, and let <em>y</em><sub>0 </sub>= 1<em>,y</em><sub>1 </sub>= 2<em>,y</em><sub>2 </sub>= 3. Write down the Lagrange interpolating polynomial that passes through the points (<em>x</em><sub>0</sub><em>,y</em><sub>0</sub>)<em>,</em>(<em>x</em><sub>1</sub><em>,y</em><sub>1</sub>)<em>,</em>(<em>x</em><sub>2</sub><em>,y</em><sub>2</sub>).</li>

 <li>For the points in the previous problem, fill in the following divided difference table:</li>

</ol>

<table width="205">

 <tbody>

  <tr>

   <td width="47"><em>f</em>[<em>x</em><sub>0</sub>] <em>f</em>[<em>x</em><sub>1</sub>]</td>

   <td width="68"><em>f</em>[<em>x</em><sub>0</sub><em>,x</em><sub>1</sub>]</td>

   <td width="90"> </td>

  </tr>

  <tr>

   <td width="47"><em>f</em>[<em>x</em><sub>2</sub>]</td>

   <td width="68"><em>f</em>[<em>x</em><sub>1</sub><em>,x</em><sub>2</sub>]</td>

   <td width="90"><em>f</em>[<em>x</em><sub>0</sub><em>,x</em><sub>1</sub><em>,x</em><sub>2</sub>]</td>

  </tr>

 </tbody>

</table>

In other words, what is expected is that you compute <em>f</em>[<em>x</em><sub>0</sub>]<em>,f</em>[<em>x</em><sub>1</sub>]<em>,f</em>[<em>x</em><sub>0</sub><em>,x</em><sub>1</sub>], etc.

<strong>Hint: </strong>Remember that the point of divided differences is that they can be computed recursively. See the textbook for the definition and more information.

<ol start="4">

 <li>Using the divided difference table above, write down the Newton interpolating polynomial for these points.</li>

</ol>

<strong>Hint: </strong>Your answer should be of the form <em>a</em><sub>0 </sub>+ <em>a</em><sub>1</sub>(<em>x </em>− <em>x</em><sub>0</sub>) + <em>a</em><sub>2</sub>(<em>x </em>− <em>x</em><sub>0</sub>)(<em>x </em>− <em>x</em><sub>1</sub>). So what you need to do is calculate <em>a</em><sub>0</sub><em>,a</em><sub>1</sub><em>,a</em><sub>2 </sub>from the divided differences table.

Also, note that the polynomial that you get from Newton interpolation should be the same as the polynomial that you get from Lagrange interpolation. So you can check your answer by plugging in some points into each polynomial and making sure that you get the same result from each.

<h1>4.5       Piecewise polynomial interpolation</h1>

<ol>

 <li>Do Exercise 8.8.9 in the book (on piecewise polynomial interpolation).</li>

</ol>

<strong>Hint: </strong>The constraints that <em>P</em>(<em>x</em>) and <em>P</em><sup>0</sup>(<em>x</em>) be continuous at <em>x </em>= 1 mean that we must have <em>P</em><sub>1</sub>(1) = <em>P</em><sub>2</sub>(1) and (1). This is because, intuitively, continuous functions are those functions that don’t have any gaps or jumps.