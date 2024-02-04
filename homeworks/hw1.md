---
layout: default
img: CL.png
caption: Computational Linguistics
img_link: https://qwantz.com/index.php?comic=170 
title: Getting into the Data
type: Homework
number: 1
active_tab: homework
release_date: 2024-02-07
due_date: 2024-02-28 23:59:00EST
submission: 
---

<!-- Check whether the assignment is ready to release -->
{% capture today %}{{'now' | date: '%s'}}{% endcapture %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% if release_date > today %} 
<div class="alert alert-danger">
Warning: this assignment is out of date.  It may still need to be updated for this year's class.  Check with your instructor before you start working on this assignment.
</div>
{% endif %}
<!-- End of check whether the assignment is up to date -->


<!-- Check whether the assignment is up to date -->
{% capture this_year %}{{'now' | date: '%Y'}}{% endcapture %}
{% capture due_year %}{{page.due_date | date: '%Y'}}{% endcapture %}
{% if this_year != due_year %} 
<div class="alert alert-danger">
Warning: this assignment is out of date.  It may still need to be updated for this year's class.  Check with your instructor before you start working on this assignment.
</div>
{% endif %}
<!-- End of check whether the assignment is up to date -->


<div class="alert alert-info">
{% assign seconds = 1 | times: 24 | times: 60 | times: 60 %}
{% assign nextDay = page.due_date %}

The proposal document is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}.
<br>
Submission Link: <a href="{{page.submission}}">{{ page.submission }}</a>
</div>

{% if page.materials %}
<div class="alert alert-info">
You can download the materials for this assignment here:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}


{{page.type}} {{page.number}}: {{page.title}}
=============================================================


## Question 1: Corpora (30 points)
In this question, you'll be doing some basic counting of words---the Hello, "World" of NLP.


You will need to load up the ``en_ewt`` subcorpus of the Universal Dependencies corpus. %
You may use the Huggingface ``datasets`` module to assist, or you may download and load the files yourself.
Note that in its raw form UD is distributed as a collection of specialized ``conllu`` files---the Huggingface ``datasets`` library handles parsing those ``conllu`` files for you.
For this assignment, do not run your code on the test data.
<span style="color:red"> **If you use the test data, you will not receive full credit!** </span>

A. Read through the documentation discussing the format of the dataset:  [https://universaldependencies.org/docs/format.html](https://universaldependencies.org/docs/format.html)
  
  * Using this documentation, verify to yourself that the first sentence has 29 tokens (nothing to turn in).
  * With that understanding, compute the number of sentences in both the training and development splits?
  (Hint: you'll want to use _train_ and _validation_ splits!)
  * On average, how many words are there per sentence for each split?

You can use any method you want to compute the number and averages (e.g., Linux commands, or a small Python or Java program). Turn in what you wrote. 


While it is a good idea to question your data, especially if it looks strange/not what you expected, for this question you can take these tokens as they are: assume that, for _some_ application, they are useful.
The text you see is called _tokenized text_.
In particular, it is text that has been tokenized, or split into individual "words," according to a particular specification.
You may be surprised that we consider punctuation as different tokens.


But let's dive into this some more.
The individual instances you observe are _tokens_, where each token is drawn from a set of _types_.
Using a programming analogy, we can say that word types are like classes while word tokens are like instances of that class.
For example, in the following sentence there are six types and eight tokens:

  ```
  the gray cat chased the tabby cat .
  ```


Notice that this computation includes punctuation.

B. Working with the training set only: Using the ``tokens`` key (or if you're processing the conllu directly, the ``FORM`` field), how many different word types and tokens are there? %
  Do not perform any processing that modifies the words.
  Turn in the code for this.

C. Examine some of the most common words from the training set, like the twenty, thirty, and fifty most common ones.
  Using examples, discuss what you notice about those common words.
  Each word should be alphanumerically (lexically) distinct.

D. In the above question, should all of these items actually be considered distinct?
  What are some ways that we could group together words?
  Hypothesize some effects your collapsing would have.
  You can argue for or against your collapsing method.

  _Hint:_
  <br>
  There is not a right or wrong answer here.
  You may want to examine the ``lemmas`` field when coming up with your answer.
  Some collapsing methods may be more appropriate than others, but the question is to think about these methods and what effect they may have.[^1]
  
  
 [^1]: Now, there are _simpler_ answers.   In particular, some collapsing methods can be accomplished with simple calls to standard string processing functions.   Others could be accomplished with some more advanced processing (e.g., see column 3).


E. Using the tokens/FORM field, examine some of the least common words in the training set.
  For this question, I recommend implementing a way of examining words that only appear $m$ times in training. With this, you should be able to identify words that appear only once, or only appear 10 times, or 100 times.
  
  i. At what general point (value of $m$) do the words start looking like "standard" words?
   * Note that there's no _precise_ value of $m$ that's correct or incorrect: this is about you looking at the data and thinking about possible linguistic / empirical trends.
  ii. Now, regardless of whether these words were \textit{standard}, are they "reasonable?"
  That is, are they items that you would want to be able to talk about as distinct items? %
  From a computational point of view, do you want to spend the computational resources to deal with them?

  Argue for or against these items' reasonableness.  If you find them unreasonable, propose a solution.   You do not need to implement it.



7. Now it's time to look at the development (aka validation) split.
  i.  How many word tokens are there in this split?
  ii.  How many word types in the validation split were not seen in the training data? We call these _out of vocabulary_ (OOV) words.
  iii. This proportion of OOV words is pretty standard in NLP. Did the number of OOV words surprise you? Briefly discuss (roughly 2-3 sentences) the potential implications of having this many OOV words.

  Again, do not perform any processing that modifies the words.
  Turn in the code for this.
  


## Question 2: Pytorch (15 points)
While there are a number of libraries that are popular to use for machine learning, especially when it comes to the neural/deep learning aspects of NLP, Pytorch is a very popular library.
Especially if you are not familiar with Pytorch, go through the [Pytorch tutorials](https://pytorch.org/tutorials/) listed under "Introduction to PyTorch (on the left).
The most important, _general_ ones for now are the "Basics", "Tensors", "Build the Neural Network", and "Automatic Differentiation".
I recommend opening an interpreter, such as a Colab notebook, and running the code in the tutorial as you read it.

%For this question, feel free to try these out for yourself.


A. A _layer_ is simply a way of encapsulating some computable function. Describe, in words, what ``torch.nn.Linear`` computes.
B. Pytorch is row major. However, this can get a bit annoying when having to deal with matrix-vector multiplication, since the vector would need to be a column vector represented in row major order. So, Pytorch will often try to be liberal and accommodating in how it interprets one-dimensional tensors. We can see this in the following code (assume all imports are okay):
```
f = torch.nn.Linear(3, 2, bias=False)
f.weight = torch.nn.Parameter(
     torch.Tensor([[3, 2, 1], 
                   [1, 4, 1]]))
x = torch.Tensor([1, 0, 0])
y = f(x)
```
State what the value of ``y`` is, and describe conceptually what this computation is doing. (Hint: you could also try ``f(torch.Tensor([0, 1, 0]))``,  ``f(torch.Tensor([0, 0, 1]))``, and / or ``f(torch.Tensor([1, 1]))``. You can also try different values of {\tt f.weight}, just make sure that it retains the same 2x3 shape.)
C. Now, following after B, consider
```
z = y.sum()
```
The recommended Pytorch tutorials covered that running ``z.backward()`` will compute ``the gradient.'' But, what gradient is actually being computed, and how does it depend on ``x`` vs. how does it depend on the value of ``f.weight``? To help answer this, you can examine the gradient that is actually computed (``f.weight.grad``).








# Grading
<div class="alert alert-warning" markdown="1">
* Question 1 - 30 points
* Question 2 - 15 points
</div>

# Footnotes
