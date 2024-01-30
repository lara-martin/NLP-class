---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: Project Proposal
type: Project Milestone
number: 1
active_tab: homework
release_date: 2024-02-07
due_date: 2024-02-18 23:59:00EST
submission: https://classroom.google.com/u/3/w/NjUwNDE2MzEwMzQx/tc/NjUxMjcyNDAwOTIx
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
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}.
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

The project is a chance for you to apply what you learned in class to a concrete task. You can **choose between two directions**: creating a novel NLP system or answering a research question. For the direction that you choose, write a project proposal that answers the questions below.  You should also prepare to give a two-minute “lightning” presentation on your proposal in class on **{{ page.due_date | date: "%B" }} {{ page.due_date | date: "%-d" | plus:1}}**. More information about the presentation can be found under "[What to Submit](#what-to-submit)"

If you are trying to decide between multiple project ideas, or if you’re struggling to come up with something, we highly encourage you to come to Office Hours and discuss it with the staff. We are experienced researchers and should be able to help you narrow down which ideas of yours are the most feasible + interesting.

## Option 1: Build a novel NLP system
Use the techniques we have learned in class to build a novel NLP system. By the end of the semester, you should have a demo that runs either in Colab or a website showcasing your system.

Write a project proposal that includes the following sections:
1. __Project Description__(3 points): What novel AI system do you propose to design?
  - Give an example mockup of what the user experience will look like. (1 to 2 paragraphs + diagram)
2. __Data__(3 points): What data will be needed to build your system? If this is few or zero shot, explain how you will be designing your prompts.
  - Does the needed data already exist?  If so, how much data is available?
3. __Proposed Method__(3 points): How will you be using algorithms from class in order to create your system? Will you need to train a model?
  - Write 2-3 paragraphs explaining your proposed method.
4. __Related work__(2 points): Do similar systems exist to the one you propose to create?
  - Give references to them and explain how you think they relate to your project idea.
  - This section will be fleshed out more in the next milestone, so for this submission just include the most relevant related works.
5. __Team members__(1 point): Give a list of the students who will participate in this project, and what contribution you expect each person to make to the project.


## Option 2: Attempt to answer an NLP research question
By the end of the semester, you should have an academic paper that describes the research question, the experiments you ran to try and answer it, and an analysis of the experimental results.

Write a project proposal that includes the following sections:
1. __Project Description__ (3 points): What research question or problem are you trying to solve?
  - Write a problem definition (1 to 2 paragraphs)
  - Give an illustrative example of the problem and/or your proposed solution.
2. __Data__ (3 points): What kind of data will you need to train and evaluate your method? If this is few or zero shot, explain how you will be designing your prompts.
  - Does the needed data already exist?  If so, how much data is available?
3. __Evaluation__ (3 points): What evaluation metrics do you plan to use to answer your research question?
4. __Related work__ (2 points): What previous research are you basing this idea on?
  - Give references to research papers that you think are relevant along with short explanations of how you think they relate to your project idea.
  - This section will be fleshed out more in the next milestone, so for this submission just include the most relevant related works.
5. __Team members__ (1 point): Give a list of the students who will participate in this project, and what contribution you expect each person to make to the project.

# What to Submit
Submit to Google Classroom:
* `proposal.pdf` which contains your project proposal. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points. LaTeX is preferred but not required.

Prepare the following for class:
* A two minute “lightning” presentation pitching your idea to the class. You should add a __single slide__ to this [Google Slides presentation](https://docs.google.com/presentation/d/1ELEsrtPzomThfCEcvc3xJTN1ox2NogmYHNllQEFbbO0/edit?usp=sharing), which you will need to use your UMBC email to access. You will have time for a longer presentation at the end of the semester.
  * For some examples of past lightning talks, you can find slides to projects from an Interactive Fiction and Text Generation class I taught here: [past slides](https://docs.google.com/presentation/d/14SnEPKNyEtDZuUlJnIRxx57xQInliMvK4pLdnVurh5E/edit?usp=sharing).



# Grading
<div class="alert alert-warning" markdown="1">
* Project Description - 3 points
* Data - 3 points
* Proposed Method or Evaluation - 3 points
* Related Work - 2 points
* Team Members - 1 point
* Lightning Talk - 2 points
</div>
