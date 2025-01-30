---
layout: default
img: periodic-table-of-nlp-tasks.png
caption: Periodic Table of NLP Tasks
img_link: https://www.innerdoc.com/periodic-table-of-nlp-tasks/
title: Being up to the Task
type: Homework
number: 1
active_tab: homework
release_date: 2025-02-05
due_date: 2025-02-18 23:59:00EST
submission: https://blackboard.umbc.edu/ultra/courses/_85408_1/outline/assessment/test/_7438115_1?courseId=_85408_1&gradeitemView=details
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

* Searching for basic information about NLP tasks.
* Exploring a dataset.
* Coming up with appropriate tasks for an application & providing your reasoning behind it.
* Determining appropriate inputs and outputs for tasks.
* Creating a system diagram.


## Description
You work for SuperDuperAI (SDAI), a start-up company that makes AI tools that their customers can use. You are their NLP specialist. One of SDAI's customers recently came to the company with a [database of textbooks](https://huggingface.co/datasets/open-phi/textbooks) that they collected. They want SDAI to make them an app that can quiz people when they select a textbook.

The flow of the app will look like this:<br>
a. The user types in a keyword that they're interested in, and the app finds relevant textbooks.<br>
b. They select the textbook and chapter they want to use.<br>
c. The app displays a question relevant to the chapter.<br>
d. The user answers the question.<br>
e. The app gives a numerical score for how well the user answered the question.

Being the NLP specialist on the team, **you are in charge of figuring out what is needed to create parts a, c, and e.**


### Question 1: Define the tasks (10 points)

You know about the following tasks, but you forget exactly what they do.
1. Document Ranking
2. Information Extraction
3. Part-of-Speech Tagging
4. Question Answering
5. Relation Extraction
6. Semantic Role Labelling
7. Sentence Boundary Disambiguation
8. Sentence Similarity
9. Summarization
10. Text segmentation

For this question, look up each of these NLP tasks, find a source that gives a definition, and give a *direct quote* of what your source said (and, of course, include where you found it).

For example, if I was defining what UMBC is:<br>
**UMBC**: "University of Maryland, Baltimore County (UMBC) is a top-ranked national university with an inclusive culture that connects innovative teaching and learning, research across disciplines, and civic engagement." (UMBC, https://umbc.edu/about/)

The formatting of your citation doesn't need to be in any particular format, but direct quotes *always* need to be surrounded by double quotes (").

Please note that you will be graded on the accuracy of your definition, so make sure your source is reliable.

<div class="alert alert-info">
Important: You will get zero (0) points for this if you do not reference your sources.
</div>

### Question 2: Select what task(s) are right for each step (18 points, 6 for each part)
There are no particular "right" answers that we are looking for. However, whatever you decide to pick, you must 1) explain why it would be a good fit (2 pts each) and 2) explain what would be the inputs (2 pts each) & outputs (2 pts each) to a model for the task. Select and motivate your selection for each of a, c, and e from the app description. (Do not do b or d.) You can use 1 or more tasks for each part.

Remember, you are using this [corpus of textbooks](https://huggingface.co/datasets/open-phi/textbooks). Give concrete examples of how your ideal inputs and outputs would look using this data! If you need any other data for your tasks, explain what that dataset might look like---you don't have to actually find it. 
For example, if I was training an image recognition model, the inputs would be the images and the outputs would be class labels for what object is in the image.


### Question 3: Draw a diagram (5 points)
Now that you have all of the components, draw a flow diagram of where the data is coming from and going to, what processes you have to do (nodes with your chosen tasks), and how the data would be transformed. **Include all steps a-e.** You will be graded on whether it includes all the steps and clearly conveys the information.

You can draw your diagram in any app you want. Diagram apps I use often are MS Powerpoint and draw.io. No hand-drawn diagrams, please.

# Grading
<div class="alert alert-warning" markdown="1">
* Question 1 - 10 points
* Question 2 - 18 points
* Question 3 - 5 points
</div>
