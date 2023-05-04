Download Link: https://assignmentchef.com/product/solved-cs70-homework6
<br>
<ul>

 <li>Polynomial Practice</li>

 <li>If <em>f </em>and <em>g </em>are non-zero real polynomials, how many roots do the following polynomials have at least? How many can they have at most? (Your answer may depend on the degrees of <em>f </em>and <em>g</em>.)

  <ul>

   <li><em>f </em>+<em>g</em></li>

   <li><em>f </em><em>g</em></li>

   <li><em>f</em><em>/g</em>, assuming that <em>f</em><em>/g </em>is a polynomial</li>

  </ul></li>

 <li>Now let <em>f </em>and <em>g </em>be polynomials over GF(<em>p</em>).

  <ul>

   <li>If <em>f </em><em>g </em>= 0, is it true that either <em>f </em>= 0 or <em>g </em>= 0?</li>

   <li>If deg <em>f </em>≥ <em>p</em>, show that there exists a polynomial <em>h </em>with deg<em>h </em><em>&lt; p </em>such that <em>f</em>(<em>x</em>)= <em>h</em>(<em>x</em>) for all <em>x </em>∈ {0<em>,</em>1<em>,…,p</em>−1}.</li>

   <li>How many <em>f </em>of degree <em>exactly d </em><em>&lt; p </em>are there such that <em>f</em>(0)= <em>a </em>for some fixed <em>a </em>∈ {0<em>,</em>1<em>,…,p</em>−1}?</li>

  </ul></li>

 <li>Find a polynomial <em>f </em>over GF(5) that satisfies <em>f</em>(0)= 1<em>, f</em>(2)= 2<em>, f</em>(4)= How many such polynomials are there?</li>

</ul>

<h1>2          The CRT and Lagrange Interpolation</h1>

Let <em>n</em><sub>1</sub><em>,…n<sub>k </sub></em>be pairwise coprime, i.e. <em>n<sub>i </sub></em>and <em>n<sub>j </sub></em>are coprime for all <em>i </em>6= <em>j</em>. The Chinese Remainder Theorem (CRT) tells us that there exist solutions to the following system of congruences:

<table width="371">

 <tbody>

  <tr>

   <td width="352"><em>x </em>≡ <em>a</em><sub>1 </sub>(mod <em>n</em><sub>1</sub>)</td>

   <td width="19">(1)</td>

  </tr>

  <tr>

   <td width="352"><em>x </em>≡ <em>a</em><sub>2 </sub>(mod <em>n</em><sub>2</sub>)</td>

   <td width="19">(2)</td>

  </tr>

  <tr>

   <td width="352">…</td>

   <td width="19">.(<sup>.</sup>.)</td>

  </tr>

  <tr>

   <td width="352"><em>x </em>≡ <em>a<sub>k </sub></em>(mod <em>n<sub>k</sub></em>)</td>

   <td width="19">(<em>k</em>)</td>

  </tr>

 </tbody>

</table>

and all solutions are equivalent (mod <em>n</em><sub>1</sub><em>n</em><sub>2 </sub>···<em>n<sub>k</sub></em>). For this problem, parts (a)-(c) will walk us through a proof of the Chinese Remainder Theorem. We will then use the CRT to revisit Lagrange interpolation.

<ul>

 <li>We start by proving the <em>k </em>= 2 case: Prove that we can always find an integer <em>x</em><sub>1 </sub>that solves (1) and (2) with <em>a</em><sub>1 </sub>= 1<em>,a</em><sub>2 </sub>= Similarly, prove that we can always find an integer <em>x</em><sub>2 </sub>that solves (1) and (2) with <em>a</em><sub>1 </sub>= 0<em>,a</em><sub>2 </sub>= 1.</li>

 <li>Use part (a) to prove that we can always find at least one solution to (1) and (2) for any <em>a</em><sub>1</sub><em>,a</em><sub>2</sub>. Furthermore, prove that all possible solutions are equivalent (mod <em>n</em><sub>1</sub><em>n</em><sub>2</sub>).</li>

 <li>Now we can tackle the case of arbitrary <em>k</em>: Use part (b) to prove that there exists a solution <em>x </em>to (1)-(<em>k</em>) and that this solution is unique (mod <em>n</em><sub>1</sub><em>n</em><sub>2 </sub>··<em>n<sub>k</sub></em>).</li>

 <li>For two polynomials <em>p</em>(<em>x</em>) and <em>q</em>(<em>x</em>), mimic the definition of <em>a </em>mod <em>b </em>for integers to define <em>p</em>(<em>x</em>) mod <em>q</em>(<em>x</em>). Use your definition to find <em>p</em>(<em>x</em>) mod (<em>x</em>−1).</li>

 <li>Define the polynomials <em>x</em>−<em>a </em>and <em>x</em>−<em>b </em>to be coprime if they have no common divisor of degree 1. Assuming that the CRT still holds when replacing <em>x</em><em>,a<sub>i </sub></em>and <em>n<sub>i </sub></em>with polynomials (using the definition of coprime polynomials just given), show that the system of congruences</li>

</ul>

<em>p</em>(<em>x</em>) ≡ <em>y</em><sub>1 </sub>(mod (<em>x</em>−<em>x</em><sub>1</sub>))   (1’) <em>p</em>(<em>x</em>) ≡ <em>y</em><sub>2 </sub>(mod (<em>x</em>−<em>x</em><sub>2</sub>))     (2’)

…                                                                                   (…)

<em>p</em>(<em>x</em>) ≡ <em>y<sub>k </sub></em>(mod (<em>x</em>−<em>x<sub>k</sub></em>))                                                   (k’)

has a unique solution (mod (<em>x</em>−<em>x</em><sub>1</sub>)···(<em>x</em>−<em>x<sub>k</sub></em>)) whenever the <em>x<sub>i </sub></em>are pairwise distinct. What is the connection to Lagrange interpolation?

<h1>3          Old secrets, new secrets</h1>

In order to share a secret number <em>s</em>, Alice distributed the values (1<em>,p</em>(1))<em>,</em>(2<em>,p</em>(2))<em>,…,</em>(<em>n</em>+1<em>,p</em>(<em>n</em>+1)) of a degree <em>n </em>polynomial <em>p </em>with her friends Bob<sub>1</sub><em>,…,</em>Bob<em><sub>n</sub></em><sub>+1</sub>. As usual, she chose <em>p </em>such that <em>p</em>(0)= <em>s</em>. Bob<sub>1 </sub>through Bob<em><sub>n</sub></em><sub>+1 </sub>now gather to jointly discover the secret. Suppose that for some reason Bob<sub>1 </sub>already knows <em>s</em>, and wants to play a joke on Bob<sub>2</sub><em>,…,</em>Bob<em><sub>n</sub></em><sub>+1</sub>, making them believe that the secret is in fact some fixed <em>s</em><sup>0 </sup>6= <em>s</em>. How can he achieve this?

<h1>4          Berlekamp-Welch for General Errors</h1>

Suppose that Hector wants to send you a length <em>n </em>= 3 message, <em>m</em><sub>0</sub><em>,m</em><sub>1</sub><em>,m</em><sub>2</sub>, with the possibility for <em>k </em>= 1 error. For all parts of this problem, we will work mod 11, so we can encode 11 letters as shown below:

<table width="294">

 <tbody>

  <tr>

   <td width="36">A</td>

   <td width="27">B</td>

   <td width="27">C</td>

   <td width="27">D</td>

   <td width="26">E</td>

   <td width="25">F</td>

   <td width="27">G</td>

   <td width="27">H</td>

   <td width="24">I</td>

   <td width="24">J</td>

   <td width="24">K</td>

  </tr>

  <tr>

   <td width="36">0</td>

   <td width="27">1</td>

   <td width="27">2</td>

   <td width="27">3</td>

   <td width="26">4</td>

   <td width="25">5</td>

   <td width="27">6</td>

   <td width="27">7</td>

   <td width="24">8</td>

   <td width="24">9</td>

   <td width="24">10</td>

  </tr>

 </tbody>

</table>

Hector encodes the message by finding the degree ≤ 2 polynomial <em>P</em>(<em>x</em>) that passes through (0<em>,m</em><sub>0</sub>), (1<em>,m</em><sub>1</sub>), and (2<em>,m</em><sub>2</sub>), and then sends you the five packets <em>P</em>(0)<em>,</em><em>P</em>(1)<em>,</em><em>P</em>(2)<em>,</em><em>P</em>(3)<em>,</em><em>P</em>(4) over a noisy channel. The message you receive is

DHACK ⇒ 3<em>,</em>7<em>,</em>0<em>,</em>2<em>,</em>10 = <em>r</em><sub>0</sub><em>,r</em><sub>1</sub><em>,r</em><sub>2</sub><em>,r</em><sub>3</sub><em>,r</em><sub>4</sub>

which could have up to 1 error.

<ul>

 <li>First, let’s locate the error, using an error-locating polynomial <em>E</em>(<em>x</em>). Let <em>Q</em>(<em>x</em>) = <em>P</em>(<em>x</em>)<em>E</em>(<em>x</em>).</li>

</ul>

Recall that

<em>Q</em>(<em>i</em>)= <em>P</em>(<em>i</em>)<em>E</em>(<em>i</em>)= <em>r<sub>i</sub>E</em>(<em>i</em>)<em>,        </em>for      0 ≤ <em>i </em><em>&lt; n</em>+2<em>k</em><em>.</em>

What is the degree of <em>E</em>(<em>x</em>)? What is the degree of <em>Q</em>(<em>x</em>)? Using the relation above, write out the form of <em>E</em>(<em>x</em>) and <em>Q</em>(<em>x</em>) in terms of the unknown coefficients, and then a system of equations to find both these polynomials.

<ul>

 <li>Solve for <em>Q</em>(<em>x</em>) and <em>E</em>(<em>x</em>). Where is the error located?</li>

 <li>Finally, what is <em>P</em>(<em>x</em>)? Use <em>P</em>(<em>x</em>) to determine the original message that Hector wanted to send.</li>

</ul>

<h1>5          Error-Detecting Codes</h1>

Suppose Alice wants to transmit a message of <em>n </em>symbols, so that Bob is able to <em>detect </em>rather than <em>correct </em>any errors that have occured on the way. That is, Alice wants to find an encoding so that

Bob, upon receiving the code, is able to either

<ul>

 <li>tell that there are no errors and decode the message, or</li>

 <li>realize that the transmitted code contains at least one error, and throw away the message.</li>

</ul>

Assuming that we are guaranteed a maximum of <em>k </em>errors, how should Alice extend her message (i.e. by how many symbols should she extend the message, and how should she choose these symbols)? You may assume that we work in GF(<em>p</em>) for very large prime <em>p</em>. Show that your scheme works, and that adding any lesser number of symbols is not good enough.