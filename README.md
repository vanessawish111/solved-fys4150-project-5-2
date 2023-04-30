Download Link: https://assignmentchef.com/product/solved-fys4150-project-5-2
<br>



<h1>Theoretical background and description of the system</h1>

Large scale, time-dependent motion in the atmosphere and ocean is often conceptualized in terms of <em>Rossby waves</em>, which have scales of hundreds to thousands of kilometers. The waves are used, for example, to understand the meandering of the atmospheric Jet Stream and the adjustment of the ocean to changes in wind forcing. Rossby waves exist because of the Coriolis acceleration, which acts perpendicular to the velocity of a fluid parcel. The Coriolis acceleration varies with latitude, being negative in the Southern Hemisphere and positive in the Northern (and vanishes at the equator). As a result of this variation, fluid parcels experience a change in their spin or <em>vorticity </em>if they move to different latitudes.

We will use the shorthand notations

<em>,</em>

etc.

The equation governing the vorticity is:

<em>∂<sub>t</sub>ζ </em>+ <em>β∂<sub>x</sub>ψ </em>= 0<em>.                                                            </em>(1)

where <em>ζ </em>is the vorticity and <em>ψ </em>is the streamfunction, which determines the velocities:

<em>u </em>= <em>−∂<sub>y</sub>ψ      ,       v </em>= <em>∂<sub>x</sub>ψ,                                                   </em>(2)

Here <em>u </em>is the velocity component in the east-west direction (<em>x</em>) and <em>v </em>in the north-south direction (<em>y</em>). The vorticity is defined:

(3)

Thus the vorticity is the Laplacian of the streamfunction. Then there is the Coriolis parameter, defined as:

<em>f </em>= 2Ωsin(<em>θ</em>)                                                              (4)

where <em>θ </em>is the latitude and Ω is the rotation rate of the Earth, Ω = 2<em>π/day</em>. We often approximate <em>f </em>as a linear function, centered on a latitude <em>θ</em><sub>0</sub>:

<em>f ≈ f</em><sub>0 </sub>+ <em>βy                                                                 </em>(5)

where <em>f</em><sub>0 </sub>= 2Ωsin(<em>θ</em><sub>0</sub>), <em>β </em>= 2Ωcos(<em>θ</em><sub>0</sub>)<em>/R<sub>e </sub></em>and <em>y </em>= <em>R<sub>e</sub></em>(<em>θ − θ</em><sub>0</sub>), if <em>R<sub>e </sub></em>is the

Earth’s radius. This linear representation is called the <em>β</em>-plane approximation, and accounts for the <em>β </em>term in (1).

Thus the vorticity equation can be written in terms of one variable, the streamfunction, thus:

(6)

This is the <em>barotropic Rossby wave equation</em>.

We will examine analytic and numerical solutions to the vorticity equation in a <em>periodic domain </em>and a <em>closed domain</em>. A periodic domain is one that “wraps around”, like the atmosphere. A closed domain has walls, like the continents bounding the oceans.

<h1>Analytical solutions</h1>

<strong>Project 5a): Solution to the Rossby equation in a periodic domain. </strong>Consider the vorticity equation (6) in one dimension (we’ll add the second dimension later). Say the periodic domain extends from <em>x </em>= [0<em>,L</em>] (east-west). A suitable wave solution has the form:

2<em>nπx</em>

<em>ψ </em>= <em>A</em>cos(   <em> − ωt</em>)<em>,                                                   </em>(7)

<em>L</em>

where <em>n </em>is an integer (= 1<em>,</em>2<em>,···</em>), and where <em>ω </em>is the wave frequency and <em>A </em>is the amplitude.

Show that the solution is the same at the two boundaries, so that it satisfies the periodic boundary conditions. Then use this wave solution in equation (6) and solve for <em>ω</em>. Use the one-dimensional form for the vorticity:

<em>ζ </em>= <em>∂<sub>x</sub>v </em>= <em>∂<sub>xx</sub>ψ                                                             </em>(8)

The result is known as the wave <em>dispersion relation</em>.

The <em>phase speed </em>is the speed at which the Rossby waves move. To see how this comes about, consider the phase of the wave:

<em>nπx</em>

<em>θ </em>=   <em> − ωt.                                                           </em>(9)

<em>L</em>

For instance, if <em>θ </em>= 2<em>π</em>, then <em>ψ </em>= <em>A</em>cos(2<em>π</em>) = <em>A</em>. This is a maximum or “high pressure” point. To see how this moves, we solve (9) for <em>x</em>:

<table width="459">

 <tbody>

  <tr>

   <td width="338">                                                              <em>x </em>=            +          <em>.</em>2<em>nπ       </em>2<em>nπ</em>Taking a time derivative, we obtain</td>

   <td width="121">(10)</td>

  </tr>

  <tr>

   <td width="338"><em>dx ωL c </em>= =</td>

   <td width="121">(11)</td>

  </tr>

 </tbody>

</table>

<em>θL ωtL dt </em>2<em>nπ</em>

Calculate the phase speed for the Rossby wave, using the dispersion relation. Which direction is the wave moving?

<strong>Project 5b): Solution to the Rossby equation with solid boundaries. </strong>More appropriate boundary conditions for the ocean are no flow at the two end points. In the present problem, we can enforce this with simple Dirichlet conditions: <em>ψ </em>= 0 at <em>x </em>= 0 and <em>x </em>= <em>L</em>. Use a wave solution with the form:

<em>ψ </em>= <em>A</em>(<em>x</em>)cos(<em>kx − ωt</em>)<em>,                                                    </em>(12)

where <em>k </em>is the wavenumber. Substitute this into equation (6). You’ll obtain terms multiplied by sin(<em>kx − ωt</em>) and others multiplied by sin(<em>kx − ωt</em>). Set each of these expressions to zero. One will give you the dispersion relation for the waves. The other will give you the form for <em>A</em>(<em>x</em>), which must satisfy the boundary conditions. You see that <em>k </em>will be <em>quantized</em>: only specific values will be allowed.

Waves like these are known as Rossby “basin modes”. The phase speed can be calculated as in the preceding problem. What is it? Discuss the structure of the wave (which is unusual).

<h1>Numerical solution</h1>

Now we consider solving equation (6) numerically. This involves two steps. If we know the velocity or streamfunction initially, we can advance the vorticity in time to a new time. Then the streamfunction at the new time is found by inverting (3). Having done this we may advance the vorticity to the next time level using (6), and so forth. We note that (6) is a <em>prognostic equation </em>and may therefore be solved numerically using a time stepping method. In contrast, (3) is a <em>diagnostic equation</em>. We will solve this using an elliptic solver.

To discretize the equations, we assume a grid of equally-spaced points:

<em>x<sub>j </sub></em>= <em>j</em>∆<em>x                                                                 </em>(13)

where ∆<em>x </em>is the grid spacing. We discretize time in a similar way:

<em>t<sup>n </sup></em>= <em>n</em>∆<em>t                                                                </em>(14)

where ∆<em>t </em>is the time step. Thus <em>t</em><sup>0 </sup>= 0, <em>t</em><sup>1 </sup>= ∆<em>t</em>, and so on.

We then approximate the derivatives by finite differences. For the spatial derivatives, we use centered-differences:

<em>ψ</em><em>jn</em>+1 <em>− ψ</em><em>jn−</em>1

<em>∂<sub>x</sub>ψ ≈                            ,                                                        </em>(15)

2∆<em>x</em>

<em>ψ</em><em>jn</em>+1 <em>− </em>2<em>ψ</em><em>jn </em>+ <em>ψ</em><em>jn−</em>1

<em>∂</em><em>xxψ ≈                        </em>2                       <em>,                                           </em>(16)

∆<em>x</em>

For the time stepping, we will test two methods. One involves a forward difference:

<em>ψ</em><em>jn</em>+1 <em>− ψ</em><em>jn</em>

<table width="459">

 <tbody>

  <tr>

   <td width="317">                                                            <em>∂<sub>t</sub>ψ ≈   </em><em>,</em>∆<em>t</em>while the second involves a centered difference:</td>

   <td width="142">(17)</td>

  </tr>

 </tbody>

</table>

<em>−</em>1

<em>∂<sub>t</sub>ψ ≈ </em><em>.                                                    </em>(18)

2∆<em>t</em>

<strong>Project 5c): Setting up the algorithms. </strong>Now we will examine numerical solutions in one dimension in the east-west direction. When calculating these, it is convenient to use <em>non-dimensional </em>forms of the equations:

<table width="272">

 <tbody>

  <tr>

   <td width="248"><em>∂<sub>t</sub>ζ </em>+ <em>∂<sub>x</sub>ψ </em>= 0<em>.</em></td>

   <td width="24">(19)</td>

  </tr>

  <tr>

   <td width="248"><em>∂<sub>xx</sub>ψ </em>= <em>ζ.</em></td>

   <td width="24">(20)</td>

  </tr>

 </tbody>

</table>

These are obtained by <em>scaling </em>each term by typical values. Doing this, the domain extends from <em>x </em>= 0 to <em>x </em>= 1, which is much simpler than worrying about realistic sizes. For the latter equation you can use your code from project 1.

For the boundary conditions, we’ll consider both the periodic domain (that wraps around) and the bounded domain (with solid walls). For the bounded domain, the streamfunction is zero at the ends, while for the periodic one the boundary values can vary.

Write the algorithms for the two time-stepping methods and the equations you need to implement for the one-dimensional case, including the numerical analogues of the boundary conditions.

<strong>Project 5d): Truncation errors and stability. </strong>Determine the truncation errors of the two time-stepping schemes and investigate their stability properties. What do you conclude about the two schemes? What is the stability criterion for the stable algorithm.

<strong>Project 5e): Implementation.          </strong>Now we’ll implement the model, using both time-stepping schemes. Hereafter we’ll use two (non-dimensional) initial conditions, a sine wave:

<table width="458">

 <tbody>

  <tr>

   <td width="435"><em>ψ</em>(<em>x,</em>0) = sin(4<em>πx</em>)and a Gaussian:</td>

   <td width="24">(21)</td>

  </tr>

  <tr>

   <td width="435"><em>x − x</em>02 <em>ψ </em>= exp<em>− </em><em> ,</em></td>

   <td width="24">(22)</td>

  </tr>

 </tbody>

</table>

<em>σ</em>

Here <em>σ </em>= 0<em>.</em>1 the width of the Gaussian.

Compare the time-stepping routines, using the sine wave in the periodic domain. Use ∆<em>x </em>= 1<em>/</em>40 and ∆<em>t </em>as determined from the results of (5d). Store the results at three times, in addition to the initial condition, e.g. <em>t </em>= 0, <em>t </em>= 50, <em>t </em>= 100 and <em>t </em>= 150. Is one of the time-stepping routines better than the other?

<strong>Project 5f): Visualization and discussion. </strong>Now we’ll examine a suite of solutions, using the stable time-stepping algorithm. Consider the following:

<ol>

 <li>Calculate the phase speed of the sine wave in the periodic domain. Do</li>

</ol>

this by using a <em>Hovmuller diagram</em>. For this you construct a matrix with <em>ψ</em>(<em>x,t</em>) at different times. <em>t </em>= 0 can be on the bottom row, then <em>t </em>= ∆<em>t </em>in the next row, <em>t </em>= 2∆<em>t </em>in the next and so. Contour the matrix and extract the phase speed.

How does it compare to the theoretical prediction in (5a)?

<ol>

 <li>Now consider the sine wave in the bounded domain. How does this evolve</li>

</ol>

differently? Rationalize the results using the theoretical prediction from (5b).

<ol>

 <li>Now examine the Gaussian, in the periodic domain. How does the Hov-muller diagram differ? Can you find a phase speed? Try varying the width, <em>σ</em>. How does this affect the phase speed.</li>

 <li>Lastly, describe the evolution of the Gaussian in the bounded domain.How does this compare to the sine wave in the same domain?</li>

</ol>

<strong>Project 5g): Moving to two dimensions. </strong>Extend the code you have developed here to two dimensions, that is, <em>ψ </em>= <em>ψ</em>(<em>x,y,t</em>) and <em>ζ </em>= <em>ζ</em>(<em>x,y,t</em>). It means that we deal with a 2+1 dimensional problem. Our differential equations become

<table width="458">

 <tbody>

  <tr>

   <td width="212"><em>∂<sub>t</sub>ζ </em>+ <em>∂<sub>x</sub>ψ </em>= 0<em>,</em>and</td>

   <td width="223"><em>t &gt; </em>0 and         <em>x,y ∈ </em>[0<em>,</em>1]<em>,</em></td>

   <td width="24">(23)</td>

  </tr>

  <tr>

   <td width="212">(<em>∂<sub>xx</sub>ψ </em>+ <em>∂<sub>yy</sub>ψ</em>) = <em>ζ,</em></td>

   <td width="223">      <em>t &gt; </em>0 and       <em>x,y ∈ </em>[0<em>,</em>1]<em>,</em></td>

   <td width="24">(24)</td>

  </tr>

 </tbody>

</table>

where we now have made a model with a square lattice for <em>x </em>and <em>y</em>. The last equation is just another example of Poisson’s equation which can be solved by Jacobi’s method, or the Gauss-Seidel method or the so-called Successive Over Relaxation method discussed in chapters 6 and 10 of the lecture notes.

How would you extend the boundary conditions from one dimension to two dimensions? And can you find a closed form solution here as well? It is left to you to decide upon what kind of boundary conditions you deem appropriate.

<strong>Project 5h): Solving the two-dimensional equations numerically. </strong>Use an explicit scheme for (23). To solve (24) you need to use for example an iterative method like Jacobi’s or Gauss-Seidel method or the Successive Over Relaxation (SOR) method. These methods are described in the lecture notes, see chapters 6 and 10.

Outline the algorithm for solving the two-dimensional equations and implement the scheme as function of ∆<em>x </em>(assuming ∆<em>x </em>= ∆<em>y</em>) and ∆<em>t</em>. Solve the equations numerically and give a critical discussion of your results. Compare your results with the closed-form answer if possible. Discuss the stability of the solution as function of different values of ∆<em>x </em>and ∆<em>t</em>.

<strong>References.          </strong>A very good reference is the textbook by <a href="https://www.springer.com/us/book/9783540225515">Winther and Tveito on </a><a href="https://www.springer.com/us/book/9783540225515">partial differential equations</a><a href="https://www.springer.com/us/book/9783540225515">.</a> It is available online <a href="https://vpn2.uio.no/+CSCO+0h756767633A2F2F797661782E66636576617472652E70627A++/book/10.1007/b138016/page/1">from the University library</a><a href="https://vpn2.uio.no/+CSCO+0h756767633A2F2F797661782E66636576617472652E70627A++/book/10.1007/b138016/page/1">.</a>

<h1>Introduction to numerical projects</h1>

Here follows a brief recipe and recommendation on how to write a report for each project.

<ul>

 <li>Give a short description of the nature of the problem and the eventual numerical methods you have used.</li>

 <li>Describe the algorithm you have used and/or developed. Here you may find it convenient to use pseudocoding. In many cases you can describe the algorithm in the program itself.</li>

 <li>Include the source code of your program. Comment your program properly.</li>

 <li>If possible, try to find analytic solutions, or known limits in order to test your program when developing the code.</li>

 <li>Include your results either in figure form or in a table. Remember to label your results. All tables and figures should have relevant captions and labels on the axes.</li>

 <li>Try to evaluate the reliabilty and numerical stability/precision of your results. If possible, include a qualitative and/or quantitative discussion of the numerical stability, eventual loss of precision etc.</li>

 <li>Try to give an interpretation of you results in your answers to the problems.</li>

 <li>Critique: if possible include your comments and reflections about the exercise, whether you felt you learnt something, ideas for improvements and other thoughts you’ve made when solving the exercise. We wish to keep this course at the interactive level and your comments can help us improve it.</li>

 <li>Try to establish a practice where you log your work at the computerlab. You may find such a logbook very handy at later stages in your work, especially when you don’t properly remember what a previous test version of your program did. Here you could also record the time spent on solving the exercise, various algorithms you may have tested or other topics which you feel worthy of mentioning.</li>

</ul>

<h1>Format for electronic delivery of report and programs</h1>

The preferred format for the report is a PDF file. You can also use DOC or postscript formats or as an ipython notebook file. As programming language we prefer that you choose between C/C++, Fortran2008 or Python. The following prescription should be followed when preparing the report:

<ul>

 <li>Use Devilry to hand in your projects, log in at <a href="http://devilry.ifi.uio.no/">http://devilry.ifi. </a><a href="http://devilry.ifi.uio.no/">no</a> with your normal UiO username and password and choose either</li>

</ul>

’fys3150’ or ’fys4150’. There you can load up the files within the deadline.

<ul>

 <li>Upload <strong>only </strong>the report file! For the source code file(s) you have developed please provide us with your link to your github domain. The report file should include all of your discussions and a list of the codes you have developed. Do not include library files which are available at the course homepage, unless you have made specific changes to them.</li>

 <li>In your git repository, please include a folder which contains selected results. These can be in the form of output from your code for a selected set of runs and input parametxers.</li>

 <li>In this and all later projects, you should include tests (for example unit tests) of your code(s).</li>

 <li>Comments from us on your projects, approval or not, corrections to be made etc can be found under your Devilry domain and are only visible to you and the teachers of the course.</li>

</ul>

Finally, we encourage you to work two and two together. Optimal working groups consist of 2-3 students. For this specific report you can hand in a common report.