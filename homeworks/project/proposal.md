---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: Project Proposal
type: Project Milestone
number: 1
active_tab: homework
release_date: 2025-02-28
due_date: 2025-03-10 23:59:00EST
submission: https://blackboard.umbc.edu/ultra/courses/_85408_1/outline/assessment/test/_7438455_1?courseId=_85408_1&gradeitemView=details
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
Please reacquaint yourself with the course's <a href="https://laramartin.net/NLP-class/#generative-ai">text generation policy</a>. <br>
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

The project is a chance for you to apply what you learned in class to a concrete task. You can **choose between two directions**: creating a novel NLP system or answering a research question. For the direction that you choose, write a project proposal that answers the questions below.  The final deliverable will a poster presentation and either a **demo** or a **paper**.

For this deliverable, don't worry as much about the format of the paper, but we are expecting you to have all the components and to write in full sentences (no bullets except when necessary).

If you are trying to decide between multiple project ideas, or if you’re struggling to come up with something, we highly encourage you to come to Office Hours and discuss it with Dr. Martin. She will be able to help you narrow down which ideas of yours are the most feasible + interesting.


## Demo: Build a novel NLP system
Use the techniques we have learned in class to build a novel NLP system. While fine-tuning a large language model on a custom dataset or few-shot prompting your model could be a component of your project, we are expecting something more involved than just this. By the end of the semester, you should have a demo that runs either in Colab or a website showcasing your system.

Write a project proposal that includes the following sections. The questions here are meant to guide your writing process.
1. __Project Name__ (1 point): This is the title of your paper so that we can refer to it.
2. __Project Description__ (3 points): What novel NLP system do you propose to design?
  - Give an example mockup (image) of what the user experience will look like.
  - Describe what the system is meant to do and what use it will have. (1 to 2 paragraphs)
3. __Data__ (3 points): What data will be needed to build your system? If this is few or zero shot prompting, explain how you will be designing your prompts.
  - What type of data is it? What does the data look like (amount, features)? How will you be using the data?
  - What are some examples of initial prompts? What is the type of output you want to get out of the model by prompting it? If it's few-shot, how many examples will you try?
4. __Proposed Method__ (3 points): How will you be using algorithms from class to create your system? Will you need to train a model?
  - Write 2-3 paragraphs explaining your proposed method.
  - If you are finetuning or few/zero-shot prompting the model, what model are you using?
5. __Related Work__ (3 points): Do similar systems exist to the one you propose to create?
  - Give references to them and explain how you think they relate to your project idea.
  - Refer to the papers that describe methods that you plan to use.
  - You can just mention the highlights of the papers for now. You will be going into more detail later.
  - I am expecting 3-5 papers for this type of project.
6. __Team Members__ (1 point): Give a list of the students who will participate in this project, and what contribution you expect each person to make to the project.


## Paper: Investigate an NLP research question
By the end of the semester, you should have an academic paper that describes the research question, the experiments you ran to try and answer it, and an analysis of the experimental results.

Write a project proposal that includes the following sections. The questions here are meant to guide your writing process.
1. __Project Name__ (1 point): This is the title of your paper so that we can refer to it.
2. __Project Description__ (3 points): What research question or problem are you trying to solve?
  - Write a problem definition (1 to 2 paragraphs)
  - Give an illustrative example of the problem and/or your proposed solution.
3. __Data__ (3 points): What data will be needed to build your system? If this is few or zero shot prompting, explain how you will be designing your prompts.
  - What type of data is it? What does the data look like (amount, features)? How will you be using the data?
  - What are some examples of initial prompts? What is the type of output you want to get out of the model by prompting it? If it's few-shot, how many examples will you try?
4. __Proposed Method__ (3 points): How will you be using algorithms from class to create your system? Will you need to train a model?
  - Write 2-3 paragraphs explaining your proposed method.
  - If you are finetuning or few/zero-shot prompting the model, what model are you using?
5. __Related Work__ (3 points): What previous research are you basing this idea on?
  - Give references to research papers that you think are relevant along with short explanations of how you think they relate to your project idea.
  - You can just mention the highlights of the papers for now. You will be going into more detail later.
  - I am expecting 5+ related papers for this type of project.
6. __Team Members__ (1 point): Give a list of the students who will participate in this project, and what contribution you expect each person to make to the project.

# Dataset Resources
* I have a list of story generation-adjacent resources on my website: [https://laramartin.net/resources.html](https://laramartin.net/resources.html)
* A great resource for finding the code/datasets from papers is [Papers with Code](https://paperswithcode.com/). You can even search by task, modality, or language on the [Datasets page](https://paperswithcode.com/datasets).
* [HuggingFace](https://huggingface.co/) also has a great collection of datasets and models. Plus, these datasets can be pulled and worked with directly in Python! Most of these also have papers corresponding with them.
* There is also [Kaggle](https://www.kaggle.com/), which is less curated (i.e., anyone can add things there and it's not really checked) and should be _navigated with caution_. I would use this only if you can't find anything useful on the other sites.

# What to Submit
1. Submit to Blackboard:
* `team#-proposal.pdf` (where "#" is your team number). This document is your project proposal. To make grading easier, your proposal should include section headers corresponding to each of items listed above (2-6 since the project name should just be at the top). LaTeX is preferred but not required. If you are doing the Paper version, you will use a more formal paper format later on.


# Grading
<div class="alert alert-warning" markdown="1">
* Project Name - 1 point
* Project Description - 3 points
* Data - 3 points
* Proposed Method - 3 points
* Related Work - 3 points
* Team Members - 1 point
</div>
