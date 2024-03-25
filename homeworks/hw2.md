---
layout: default
img: evaluating_tech_things.png
caption: Evaluating Tech Things
img_link: https://xkcd.com/2072/
title: Evaluation
type: Homework
number: 2
active_tab: homework
release_date: 2024-03-27
due_date: 2024-04-03 23:59:00EST
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

The assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}.
<br>
Submission Link: <a href="{{page.submission}}">{{ page.submission }}</a><br><br>
Please be sure to double check the academic integrity and generative AI policies <a href="https://laramartin.net/NLP-class/#academic-integrity">listed on the syllabus</a>.
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

## Learning Objectives




## Description


### Question 1 (24 points)

Each of the following scenarios describes the result of some (made up) classifier: there is a list of the correct labels, and the corresponding predictions. For each of
the following situations, compute accuracy, recall, precision, and F1 score. You may verify
your answers with code, but you must show work, or some intermediate steps, to receive full
credit on this problem.

a) (4 points) A binary classification result, where the correct labels are
`[T, T, F, T, F, T, F, T]` and the predicted labels are
`[T, F, T, T, F, F, F, T]`. Assume `T` means “true” (the desired class) and `F`
(“false”) is the “default” class. Compute accuracy, and compute recall, precision, and
F1 for `T`.

b) (4 points) A binary classification result, where the correct labels are
`[T, F, F, F, F, F, F, T]` and the predicted labels are
`[F, T, F, F, F, F, F, F]`. Assume `T` means “true” (the desired class) and `F`
(“false”) is the “default” class. Compute accuracy, and compute recall, precision, and
F1 for `T`.

c) (8 points) A multiclass classification result, where the correct labels are
`[T, F, M, F, F, F, M, T]` and the predicted labels are
`[F, T, M, F, F, F, F, T]`. Assume `T` means “true,” `M` means “maybe,” and
`F` (“false”) is the “default” class. Compute accuracy. Then, compute, at **both the micro
and macro levels**, average recall, precision, and F1. Explain why you should *not* include
the `F` class in the precision, recall, and F1 computations.

d) (8 points) A multiclass classification result, where the correct labels are
`[C, C, A, C, C, C, C, C, B, A, C, C, C]` and the predicted labels are
`[C, C, C, C, C, C, C, C, B, A, A, C, C]`. In this example, there is no
“good” default option, so we can consider `A`, `B`, and `C` to be all possible classes/labels
of interest. Compute accuracy. Then, compute, at **both the micro and macro levels**,
average recall, precision, and F1. Explain why you *should* include all classes in the
precision, recall, and F1 computations.


# Grading
<div class="alert alert-warning" markdown="1">
* Question 1 - 10 points
* Question 2 - 18 points
* Question 3 - 5 points
</div>
