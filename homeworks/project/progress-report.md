---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/
title: Project Progress
type: Project Milestone
number: 2
active_tab: homework
release_date: 2026-03-26
due_date: 2026-04-14 23:59:00EST
submission: https://blackboard.umbc.edu/ultra/courses/_96481_1/outline/assessment/test/_8407429_1?courseId=_96481_1&gradeitemView=details
online_submission: https://blackboard.umbc.edu/ultra/courses/_98413_1/outline/assessment/test/_8407381_1?courseId=_98413_1&gradeitemView=details
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
Submission Link (in-person section): <a href="{{page.submission}}">{{ page.submission }}</a><br>
Submission Link (online section): <a href="{{page.online_submission}}">{{ page.online_submission }}</a><br>
It makes it easier to grade if one person from each section (online and in-person) submits.<br><br>
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

By now, you should have made some progress on your project. This milestone will flesh out some of the components of your project from the proposal. Be sure to read the appropriate section for your project type below as the requirements start to diverge.


## Demo: Build a novel NLP system
For this milestone, you will describe your demo in more detail. The milestone after this one will have a shorter report needed but will require a somewhat-working demo. 

Write a report that includes the following sections. The questions here are meant to guide your writing process.
1. __Project Description__: What novel interactive experience do you propose to design? (This will collapse the __Project Description__ and __Related Work__ sections from your proposal into one section.)
  - Do similar systems exist to the one you propose to create? Give pointers to them and explain how you think they relate to your project idea. What were your inspirations?
  - What niche do you expect this program to fill? (Why are you making it? What does it do? Who is it for?)
  - Give an example mockup of what the user experience will look like. (Also consider: will there be any graphics or AI-generated images?)
  - Describe how you expect users to interact with the system. What is the interface?
  - Include a repo link to your code (as it is so far) in this section. You can link to it in a footnote or put it in the main text.
3. __Back End Architecture__: What does the overall architecture of your system look like? 
  - Describe how your architecture will work. 
  - What will each component of your pipeline be? Describe any datasets, models, tools, and tricks you're using or plan to use. Be specific about the details of why you're using them and what they're doing in the overall system.
  - Give an example diagram of the backend system (the pipeline of components).
4. __Evaluation__: In order to tell if your system is performing well, you need an evaluation. How do you plan on evaluating your system?
  - What baselines, benchmarks, or other systems do you plan on comparing your system to? They can be pre-existing applications. You don't necessarily need to reimplement them---for example, I'm not expecting you to remake Duolingo---but you need a way of comparing to them.
  - What metrics do you plan to use to compare your system to the baselines/benchmarks/existing applications? You can come up with ways of evaluating the components of your system separately and/or you can evaluate the entire system by doing a little user study where you will ask your friends to evaluate.
5. __Team Members__: Give a list of the students who are participating in this project, and what contributions you have made and expect to make for the project.
  - In this section also mention what you have completed so far and what is still left to do. You won't be graded on how far you've gotten in the project, but obviously the further you get, the less you'll have to scramble last-minute.
6. __LLM Use Statement__: Describe exactly how you used LLMs to generate parts of your proposal document (<a href="https://laramartin.net/NLP-class/index.html#generative-ai">refer to the syllabus for guidance</a>). If you did not use **any** generative text, please state so in this section.

### Grading
<div class="alert alert-warning" markdown="1">
You will get full points if you 1) include all of the material listed above and 2) incorporate the feedback you got from the previous submission.<br>

* Project Description - 10 points
* Back End Architecture - 5 points
* Evaluation - 5 points
* Team Members - 2 points
* LLM Use Statement - 1 point

Total: 23 points
</div>


## Paper: Investigate an NLP research question
For this milestone, you will take the components of your proposal and begin to move them into more "paper-like" sections. You will also be adding in some more details.

While not required at this stage, we highly recommend that you use LaTeX and a conference template since you will have to for the next milestone. If you do not have a conference/workshop in mind, I recommend that you use the [template from the Association for Computational Linguistics](https://www.overleaf.com/latex/templates/association-for-computational-linguistics-acl-conference/jvxskxpnznfj).

<div class="alert alert-warning" markdown="1">
<b>Science 101</b><br>
A *research question* should be **something that can be proved true or false.** An example of a *bad* research question might be "Which dog is the best dog?" because it cannot be rejected (i.e., null hypothesis). <br> A *better* way to rephrase this---by potentially looking at the same problem---would be to ask "Is Pharaoh a good dog?". This can then be tested. You just need to define how to measure "goodness" in this case.
</div>

Your paper should include the following sections. The questions here are meant to guide your writing process.
1. __Introduction__: What research question(s) or problem are you trying to solve? (This is where your problem definition from the __Project Description__ of your proposal goes.)
  - Why this it worth researching?
  - What contributions does this work make? (i.e., What are you doing that's novel?)
  - If you are writing any code, either share the link to your repository in a footnote or mention it in the main text.
2. __Related Work__: What previous research has been done on this research question?
  - Turn your previous list of citations into a little *narrative* of what has been done previously in the field. Take a look at some previously-published papers to see how they write their related works section.
3. __Methods__: What are you doing or making to address your research question(s)?
  - If you are using any datasets, does the needed data already exist?  If so, how much data is available? What does the data look like? If you are just using a few examples for few-shot prompting, how did you select those?
  - Describe your solution to the problem/research question. What model(s) are you using? If you are using few- or zero-shot prompting, what do your prompts look like?
4. __Experiments__: What experiments will you be running?
  - What are you measuring and why? What evaluation metrics do you plan to use to answer your research question(s)?
  - What are your proposed *baselines*? Or are you using a pre-defined benchmark? (That is, what are you comparing your method against?)
  - How do these experiments answer your research questions?
5. __Team Members__: Give a list of the students who are participating in this project, and what contributions you have made and expect to make for the project.
  - In this section also mention what you have completed so far and what is still left to do. You won't be graded on how far you've gotten in the project, but obviously the further you get, the less you'll have to scramble last-minute.
6. __LLM Use Statement__: Describe exactly how you used LLMs to generate parts of your proposal document (<a href="https://laramartin.net/NLP-class/index.html#generative-ai">refer to the syllabus for guidance</a>). If you did not use **any** generative text, please state so in this section.

### Grading
<div class="alert alert-warning" markdown="1">
You will get full points if you 1) include all of the material listed above and 2) incorporate the feedback you got from the previous submission.<br>

* Introduction - 5 points
* Related Work - 5 points
* Methods - 5 points
* Experiments - 5 points
* Team Members - 2 points
* LLM Use Statement - 1 point

Total: 23 points
</div>

# What to Submit
Submit the following to [Blackboard]({{page.submission_link}}):
* `team#-milestone2.pdf` which contains your milestone 2 submission. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points. 



