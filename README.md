Download Link: https://assignmentchef.com/product/solved-csc411-assignment-1-nearest-neighbours-and-the-curse-of-dimensionality
<br>
<ol>

 <li><strong>Nearest Neighbours and the Curse of Dimensionality. </strong>In this question, you will verify the claim from lecture that “most” points in a high-dimensional space are far away from each other, and also approximately the same distance. There is a very neat proof of this fact which uses the properties of expectation and variance. If it’s been a long time since you’ve studied these, you may wish to review the Tutorial 1 slides<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>, or the Metacademy resources<sup>4</sup>.

  <ul>

   <li>First, consider two independent univariate random variables <em>X </em>and <em>Y </em>sampled uniformly from the unit interval [0<em>,</em>1]. Determine the expectation and variance of the random variable <em>Z</em>, defined as the squared distance <em>Z </em>= (<em>X </em>− <em>Y </em>)<sup>2</sup>. You are allowed to evaluate integrals numerically (e.g. using integrate.quad or scipy.integrate.dblquad), but you should explain what integral(s) you are evaluating, and why.</li>

   <li>Now suppose we sample two points independently from a unit cube in <em>d </em> Observe that each coordinate is sampled independently from [0<em>,</em>1], i.e. we can view this as sampling random variables <em>X</em><sub>1</sub><em>,…,X<sub>d</sub>,Y</em><sub>1</sub><em>,…,Y<sub>d </sub></em>independently from [0<em>,</em>1]. The squared Euclidean distance can be written as <em>R </em>= <em>Z</em><sub>1 </sub>+···+<em>Z<sub>d</sub></em>, where <em>Z<sub>i </sub></em>= (<em>X<sub>i </sub></em>−<em>Y<sub>i</sub></em>)<sup>2</sup>. Using the properties of expectation and variance, determine E[<em>R</em>] and Var[<em>R</em>]. You may give your answer in terms of the dimension <em>d</em>, and E[<em>Z</em>] and Var[<em>Z</em>] (the answers from part (a)).</li>

   <li><strong>[for your own benefit, not to be handed in] </strong>Based on your answer to part (b), compare the mean and standard deviation of <em>R </em>to the maximum possible squared Euclidean distance (i.e. the distance between opposite corners of the cube). Why does this support the claim that in high dimensions, “most points are far away, and approximately the same distance”?</li>

  </ul></li>

 <li><strong> Decision Trees. </strong><em>This question is taken from a project by Lisa Zhang and Michael Guerzhoy.</em></li>

</ol>

In this question, you will use the scikit-learn decision tree classifier to classify real vs. fake news headlines. The aim of this question is for you to read the scikit-learn API and get comfortable with training/validation splits.

We will use a dataset of 1298 “fake news” headlines (which mostly include headlines of articles classified as biased, etc.) and 1968 “real” news headlines, where the “fake news” headlines are from <a href="https://www.kaggle.com/mrisdal/fake-news/data">https://www.kaggle.com/mrisdal/fake-news/data</a> and “real news” headlines are from <a href="https://www.kaggle.com/therohk/million-headlines">https://www.kaggle.com/therohk/million-headlines</a><a href="https://www.kaggle.com/therohk/million-headlines">.</a> The data were cleaned by removing words from fake news titles that are not a part of the headline, removing special characters from the headlines, and restricting real news headlines to those after October 2016 containing the word “trump”. For your interest, the cleaning script is available as clean_script.py on the course web page, but you do not need to run it. The cleaned-up data are available as clean_real.txt and clean_fake.txt on the course web page.

Each headline appears as a single line in the data file. Words in the headline are separated by spaces, so just use str.split() in Python to split the headlines into words.

You will build a decision tree to classify real vs. fake news headlines. Instead of coding the decision trees yourself, you will do what we normally do in practice — use an existing implementation. You should use the DecisionTreeClassifier included in sklearn. Note that figuring out how to use this implementation is a part of the assignment.

Here’s a link to the documentation of sklearn.tree.DecisionTreeClassifier: <a href="http://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html">http:// </a><a href="http://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html">scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier. </a><a href="http://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html">html</a>

All code should be included in the file hw1_code.py which you submit through MarkUs.

<ul>

 <li>Write a function load_data which loads the data, preprocesses it using a vectorizer</li>

</ul>

<a href="http://scikit-learn.org/stable/modules/classes.html#module-sklearn.feature_extraction.text">(</a><a href="http://scikit-learn.org/stable/modules/classes.html#module-sklearn.feature_extraction.text">http://scikit-learn.org/stable/modules/classes.html#module-sklearn.featur</a>e_ <a href="http://scikit-learn.org/stable/modules/classes.html#module-sklearn.feature_extraction.text">extraction.text</a><a href="http://scikit-learn.org/stable/modules/classes.html#module-sklearn.feature_extraction.text">)</a>, and splits the entire dataset randomly into 70% training, 15% validation, and 15% test examples.

<ul>

 <li><strong> </strong>Write a function select_model which trains the decision tree classifier using at least 5 different values of max_depth, as well as two different split criteria (information gain and Gini coefficient), evaluates the performance of each one on the validation set, and prints the resulting accuracies of each model. You should use DecisionTreeClassifier, but you should write the validation code yourself. Include the output of this function in your solution PDF (pdf).</li>

 <li><strong> </strong>Now let’s stick with the hyperparameters which achieved the highest validation accuracy. Extract and visualize the first two layers of the tree. Your visualization may look something like what is shown below, but it does not have to be an image: it is perfectly fine to display text. It may be hand-drawn. Include your visualization in your solution PDF (pdf).</li>

 <li><strong> </strong>Write a function compute_information_gain which computes the information gain of a split on the training data. That is, compute <em>I</em>(<em>Y,x<sub>i</sub></em>), where <em>Y </em>is the random variable signifying whether the headline is real or fake, and <em>x<sub>i </sub></em>is the keyword chosen for the split.</li>

</ul>

Report the outputs of this function for the topmost split from the previous part, and for several other keywords.

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="https://www.cs.toronto.edu/~rgrosse/courses/csc411_f18/tutorials/tut1.pdf">https://www.cs.toronto.edu/</a><a href="https://www.cs.toronto.edu/~rgrosse/courses/csc411_f18/tutorials/tut1.pdf">~</a><a href="https://www.cs.toronto.edu/~rgrosse/courses/csc411_f18/tutorials/tut1.pdf">rgrosse/courses/csc411_f18/tutorials/tut1.pdf </a><sup><a href="https://metacademy.org/graphs/concepts/expectation_and_variance">4</a></sup><a href="https://metacademy.org/graphs/concepts/expectation_and_variance">https://metacademy.org/graphs/concepts/expectation_and_variance</a>