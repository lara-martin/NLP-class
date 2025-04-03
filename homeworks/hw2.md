---
layout: default
img: evaluating_tech_things.png
caption: Evaluating Tech Things
img_link: https://xkcd.com/2072/
title: Evaluation
type: Homework
number: 2
active_tab: homework
release_date: 2025-03-04
due_date: 2025-04-04 23:59:00EST
submission: https://blackboard.umbc.edu/ultra/courses/_85408_1/outline/assessment/test/_7438117_1?courseId=_85408_1&gradeitemView=details
materials:
  -
    name: GLUE data
    url: https://huggingface.co/datasets/nyu-mll/glue/viewer/rte
  -
    name: Torch Tutorial from Knowledge Check
    url: https://colab.research.google.com/github/pytorch/tutorials/blob/gh-pages/_downloads/dd1c511de656ab48216de2866264b28f/deep_learning_tutorial.ipynb
  -
    name: RNN Tutorial
    url: https://pytorch.org/tutorials/beginner/former_torchies/nnft_tutorial.html#example-2-recurrent-net
  -
    name: Character RNN Tutorial
    url: https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html
  -
    name: HW 2 Data Prep Code
    url: https://colab.research.google.com/drive/1fTakwqcG55XUxhJ48mwawqegDxYq_zj9
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

The assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}.
<br>
Submission Link: <a href="{{page.submission}}">{{ page.submission }}</a><br><br>
Please be sure to double check the academic integrity and generative AI policies <a href="https://laramartin.net/NLP-class/#academic-integrity">listed on the syllabus</a>.
</div>

{% if page.materials %}
<div class="alert alert-info">
Materials for this assignment:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}


<!-- TODO: add in help with padding the input -->

{{page.type}} {{page.number}}: {{page.title}}
=============================================================

## Learning Objectives
* Calculate common evaluation metrics (recall, precision, F1, accuracy) for multiclass classification.
* Explain when certain evaluation metrics should be modified to fit the problem.
* Create and analyze a simple baseline model.
* Follow code from online for making a neural network.
* Compare the performance of a baseline and a neural model.


## Question 1 (24 points): Evaluating by Hand

Each of the following scenarios describes the result of some (made up) classifier: there is a list of the correct labels, and the corresponding predictions. For each of
the following situations, compute accuracy, recall, precision, and F1 score. You may verify
your answers with code, but **you must show work, or some intermediate steps, to receive full
credit** on this problem.

Slides from [2/18](https://laramartin.net/NLP-class/slides/25-02-18_ML-Evaluation.pdf) and [2/20](https://laramartin.net/NLP-class/slides/25-02-20_ML-Evaluation.pdf) will be the most useful for this question.

a) (4 points total) A binary classification result, where the correct labels are
`[T, T, F, T, F, T, F, T]` and the predicted labels are
`[T, F, T, T, F, F, F, T]`. Assume `T` means “true” (the desired class) and `F`
(“false”) is the “default” class. 
* (1 pt) Compute accuracy.
* (3 pts) Compute recall, precision, and F1 for `T`.

b) (4 points total) A binary classification result, where the correct labels are
`[T, F, F, F, F, F, F, T]` and the predicted labels are
`[F, T, F, F, F, F, F, F]`. Assume `T` means “true” (the desired class) and `F`
(“false”) is the “default” class. 
* (1 pt) Compute accuracy.
* (3 pts) Compute recall, precision, and F1 for `T`.

c) (8 points total) A multiclass classification result, where the correct labels are
`[T, F, M, F, F, F, M, T]` and the predicted labels are
`[F, T, M, F, F, F, F, T]`. Assume `T` means “true,” `M` means “maybe,” and
`F` (“false”) is the “default” class. 
* (1 pt) Compute accuracy. 
* (6 pts) Then, compute, at **both the micro and macro levels**, average recall, precision, and F1. 
* (1 pt) Explain why you should *not* include the `F` class in the precision, recall, and F1 computations.

d) (8 points total) A multiclass classification result, where the correct labels are
`[C, C, A, C, C, C, C, C, B, A, C, C, C]` and the predicted labels are
`[C, C, C, C, C, C, C, C, B, A, A, C, C]`. In this example, there is no
“good” default option, so we can consider `A`, `B`, and `C` to be all possible classes/labels
of interest. 
* (1 pt) Compute accuracy. 
* (6 pts) Then, compute, at **both the micro and macro levels**, average recall, precision, and F1. 
* (1 pt) Explain why you *should* include all classes in the precision, recall, and F1 computations.

## Question 2 (13 points): Baselines

One very important aspect of NLP is the ability to identify good and reasonable
baseline systems. These baseline systems help you contextualize any progress (or harm) your
proposed approach makes. Coming up with these baselines is not always easy. However, in classification, a
very common one is called the “most frequent class” baseline. This most frequent class baseline simply identifies the most common label y' from the training set, and then when presented with any evaluation instance, simply returns y'.

The purpose of this question is to (1) setup a naive baseline to compare against the model you'll make in Question 3, and (2) implement evaluation metrics in Python. 

a) (1 point) As a toy problem, consider a small training set with 5 instances. If the class labels for those 5 instances are [α, α, β, γ, α], respectively. What label would the most frequent baseline return?

b) (12 points) Working from the [GLUE](https://huggingface.co/datasets/nyu-mll/glue) **RTE** corpus, calculate a most frequent class baseline on the training set for predicting entailment. Implement the 5 metrics: accuracy, macro precision, macro recall, micro precision, and micro recall. I strongly recommend using the existing implementations of accuracy, recall, and precision in the Python library `sklearn`, e.g., `sklearn.metrics.precision_score` and `sklearn.metrics.recall_score`. Then evaluate your baseline "model" **on only the dev/validation set** using the 5 metrics.
Turn in your code (5 points), these 5 scores (5 points), and a brief paragraph (2 points) both describing what you observe from using this baseline and analyzing how reasonable the predictions made by this baseline are.


## Question 3 (19 points): Model Training and Evaluation 
Now you will train a basic recurrent neural network and compare it to your baseline. Please note that you will be graded on how well you implemented your model and your analysis of how well it did, not on the performance of the model itself.

1. Start with my modified implementation of the [data prep code](https://colab.research.google.com/drive/1fTakwqcG55XUxhJ48mwawqegDxYq_zj9) for this assignment. Note that the input has both sentences separated by a special word `||`. Be sure to keep them together as a single input but treat the "||" as its own type.
2. [Continue to follow the tutorial](https://colab.research.google.com/github/pytorch/tutorials/blob/gh-pages/_downloads/dd1c511de656ab48216de2866264b28f/deep_learning_tutorial.ipynb) to setup the network. [This tutorial](https://pytorch.org/tutorials/beginner/nn_tutorial.html) and [this tutorial](https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html) might also be helpful.
3. Switch the BoWClassifier model to an RNN using [`torch.nn.RNN`](https://pytorch.org/docs/stable/generated/torch.nn.RNN.html). Use a hidden size of 128.
4. Train the network on the [GLUE](https://huggingface.co/datasets/nyu-mll/glue) **training** set for **5 epochs**.
5. Calculate accuracy, macro precision, macro recall, micro precision, and micro recall on the **dev set**.
6. Turn in your code (8 points), these 5 scores (5 points), and a brief paragraph (5 points) explaining how the network did with its predictions, how it compares to your frequent class baseline from Question 2, and what insights you can take away from comparing the two. 
7. Be sure to include a comment at the top of your code stating **all of the places** where you got the code that you adapted (e.g., the tutorial links) (1 point).

### Extra credit (5 points): 

Train another type of neural network and repeat steps 4-6 on this new network. Then answer the following questions:
* How does this network compare to the previous network (question 3) and the frequent class baseline (question 2b)?
* Why do you think it performed that way?


# Grading
<div class="alert alert-warning" markdown="1">
* Question 1 - 24 points
* Question 2 - 13 points
* Question 3 - 19 points
* Extra credit - 5 points
</div>
