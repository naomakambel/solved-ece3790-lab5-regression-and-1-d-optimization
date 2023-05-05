Download Link: https://assignmentchef.com/product/solved-ece3790-lab5-regression-and-1-d-optimization
<br>
<strong>The purpose of this lab is to give you practical coding experience. </strong>It will also reinforce concepts we’ve covered in class.

<strong>Important: </strong>Please include the following signed statement with your submission.

I (We), [insert name(s)] attest that the work I am (we are) submitting is my (our) own work and that it has not been copied/plagiarized from online or other sources. Any sourced material used for completing this work has been properly cited. [Signature(s)]

<strong>Also Important: </strong>Labs done in pairs must be submitted with a short paragraph outlining each partner’s contribution.

<h1>Introduction</h1>

In this lab we are going to do some regression and optimization. First we are going to try to establish a model for some physical data. Then we will find the right trajectory by which to leave earth (in a <em>very </em>simplistic model) in order to make it off the planet and intercept other planets in our solar system.

<h1>Problem 1 – Regression</h1>

<h2>Data</h2>

At the heart of any regression problem is data. We give you flexibility in choosing data for applying regression, and encourage you to find something physically interesting. Of course Covid cases offer interesting trends to try and model using regression, but there are many other possibilities. Kaggle (kaggle.com) is an online community for data scientists. It is

a great repository for all kinds of data sets (see https://www.kaggle.com/datasets). You may find something interesting there. If you don’t want to go digging for data, you can always generate your own. Keep reading to see what kind of data you will need based on the functions you have to write.

<h2>Functions</h2>

For this problem you can use whatever programming language you prefer, and use linear algebra libraries for solving systems of equations. Personally I believe Matlab/Python is the right choice here, because as rapid prototyping tools you should get them up and running faster than other languages. Note: the point is not just to call some built-in regression/curvefitting function.

Implement <strong>one </strong>of the following functions (we suggest you implement all of them but it has been a long semester):

<ol>

 <li>A function linearregression. It should take in a set of sample data and produce the corresponding linear regression coefficients. It should be capable of multiple linear regression, so the input data should be a matrix (or 2-D array) where the first <em>m </em>columns are the independent variables at each sample point, and the last column is the dependent variable (or some format of this sort that works for you). The function should also calculate and return the correlation coefficient.</li>

 <li>A function polynomialregression. This should take in the polynomial order and onedimensional input data, convert it to multi-linear data, perform regression, and return the model parameters and correlation coefficient. Note that the correlation coefficient should be computed in the linearized space.</li>

 <li>A function exponentialregression. This should take in the data, linearize it, call linearregression and return the model parameters and correlation coefficient. Note that the correlation coefficient should be computed in the linearized space.</li>

</ol>

<h2>Main Program</h2>

Write a main program Lab 5 Problem 1 that:

<ul>

 <li>Validates your chosen function by generating data and using it to show that your regression code work properly. For example, you can create data <em>y </em>= <em>a</em><sub>0</sub>+<em>a</em><sub>1</sub><em>x</em>+<em>a</em><sub>2</sub><em>x</em><sup>2 </sup>by picking values for the coefficients. If you put this data through your polynomialregression function, you should recover the parameters exactly (to numerical precision) and get a correlation coefficient of 1.</li>

 <li>Applies your function to a noisy data set (hopefully this is some interesting data, but you can just generate a noisy set yourself if needed).</li>

</ul>

<h2>Analysis</h2>

From the main program produce appropriate plots 1) showing that your implementation works and that error quantification (correlation coefficient) is valid, and 2) showing how the chosen model fits a non-validation noisy data set. Write up a brief discussion of the results commenting on whether or not you believe the model has predictive value based on the quantified fit (correlation coefficient).

<h2>Discussion</h2>

Answer the following questions:

<ol>

 <li>Discuss your chosen data. Where did it come from? Was the function you programmed a good model for this data? Why or why not?</li>

 <li>Assuming you have <em>n </em>data samples, what is the computational complexity of applying multiple linear regression if we have <em>m </em>independent variables? Show your work/justify your answer.</li>

 <li>Why/how can linear regression be applied to data that follows an exponential trend?</li>

</ol>

A high-level explanation is sufficient.

<ol start="4">

 <li>What are the memory requirements of your regression implementation? Is there any room to improve the memory requirements? If so how?</li>

</ol>

<strong>Hand in:</strong>

All codes, plots, your analysis writeup, and answers to the discussion questions.

<h1>Problem 2 – 1-D Optimization</h1>

In this problem you will write code for the golden section search. You’ll validate these on a very simple function. Next you’ll do some optimization of a more interesting problem.

You’ve been given a function spaceship in both Python and Matlab. This function takes a single argument, the angle of departure of a spaceship (red x) from the planet earth at time 0, and simulates the time-evolution of the spaceship as it traverses through our solar system (a simple model consisting of the Sun, Earth, Mars, Jupiter, Saturn and Uranus). The model doesn’t even compute forces on the spaceship, and depending on the angle of departure the sun can be a serious problem but we will ignore that. I encourage you to look at the function and think about how it works. The input angle is in degrees. The function returns the minimum distance recorded between the spaceship and Saturn. Our goal is to minimize this distance by appropriately changing the angle (and nothing else so that this remains a 1-D optimization problem). Thus the function spaceship is our objective function <em>f</em>(<em>x</em>) where <em>x </em>is the angle of departure. Overall you don’t need to know how it works, and can simply use it as a “black box”.

<h2>Functions</h2>

You will probably want to write your functions in Python or Matlab as the provided code is in these languages. Otherwise, you will probably have to convert my code to another language. That is ok too, but may not be worth the effort. Also, the right way to do this is to pass a function handle to your method.

<ol>

 <li>A) Implement a function called goldensectionsearch that, given a function (handle), lower and upper bracketing bounds, error tolerance, and maximum iterations, will try to find the <u>maximum </u>of the function.</li>

</ol>

<h2>Main Program</h2>

Write a main program Lab 5 Problem 2 that:

<ul>

 <li>Solves the spaceship optimization problem using your goldensectionsearch function and stores the convergence history (error and estimate) of the solution. Remember, your function finds the maximum, but you want to find the minimum distance. Note that once you know things are working it may be worth turning off plotting in the objective function to speed things up.</li>

</ul>

<h2>Validation and Data Collection</h2>

Once you have completed writing your functions and main program you need to:

<ul>

 <li>Produce plots of the convergence history (error level and minimum value convergence each as a function of iteration, so two plots) for both the spaceship problem.</li>

</ul>

<h2>Evaluation and Discussion</h2>

Answer the following questions:

<ol>

 <li>Suppose we added another parameter to our spaceship optimization problem so that we could optimize over a fixed angle and fixed speed. Would you still be able to apply something like the golden section search to this 2-D problem? If so what changes would be required? What would you need to do in order to try and apply gradient search to that problem?</li>

 <li>How many iterations did it take your search to converge and to what error level? From your results do you see value in trying to reduce the number of function evaluations for this optimization problem? What about more complicated/realistic problems?</li>

</ol>

<strong>Hand in:</strong>

Hand in all code, plots, validation, and your answers to the discussion questions.