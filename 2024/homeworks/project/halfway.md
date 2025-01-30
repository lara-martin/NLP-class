---
layout: default-2024
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/
title: Halfway Point
type: Project Milestone
number: 3
active_tab: homework
release_date: 2024-03-25
due_date: 2024-04-03 23:59:00EST
submission: https://classroom.google.com/c/NjUwNDE2MzEwMzQx/a/NjcxMjc1NjA2MjU5/details
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
<br>Submission Link: <a href="{{page.submission}}">{{ page.submission }}</a>

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

Welcome to the halfway point of your project!
For this milestone, you are showing that you've made some progress in your project. In particular you should: 
* Update your paper based on the feedback the class staff left for you from the last milestone.
* Show any progress you have made, including preliminary results, methods, etc.



# Document

Your document should include the following sections:

__Title__ & __Author Names__: What are you calling your project? These are not graded but still important! (No section header for these bits)
1. __Project Description__: This is the "what" and the "why" of your project. 
 * The "what": Explain the main idea of your project and what you are trying to accomplish. It's okay if these have changed since the project proposal.
 * The "why": If it's a research project, what's your research question (i.e., what are you trying to prove with this work)? If it's an artifact that you're creating, why are you creating it?
2. __Related Work__: What previous research will you be using, building off of, or being inspired by? Tell a short "story" using what you learned from the papers.
3. __Methods__: What are the steps to accomplish your project? This should describe both the steps you've done so far (data collection and system planning) and the ones you plan to do. This doesn't have to be the final methods that you end up using, but writing out a plan out will help you figure out some details you might not have thought of otherwise!
4. __Data__: Describe what your data is in detail. For example, what data have you decided to use? Where did you get it from, what does it look like, and what are some potential problems with it? If you are using few/zero shot prompting, what are some of your initial prompts? How have they been working?
5. __Evaluation Plan__: What will you be using to evaluate your research question or that the components of your NLP system are working well? 
  * These can be things like accuracy, diversity metrics, perplexity, BLEU/ROUGE scores, success rate, human evaluation scores, etc. depending on your project.
6. __Preliminary Results__: Describe any results you have so far. These can include results for intermediate steps that build toward your main project goal and don't have to use your final evaluation metrics. If you haven't gotten anything working successfully yet, negative results or plans for experiments to run are great to report too! This section should include tables, plots, and example system outputs where applicable.
7. __Attribution__: For each of your team mates, write a couple sentences describing their main contributions to the project so far and what each person plans to do for the rest of the project.

# What to Submit
Submit the following to [Google Classroom]({{page.submission}}):
* `group[#]-milestone3.pdf` which contains your updated project paper. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points as well. While not required, we highly recommend that you use LaTeX and a conference template ([ACL's template](https://github.com/acl-org/acl-style-files)). You will be required to use a conference template for the next milestone.

# Grading
<div class="alert alert-warning" markdown="1">
* Project Description: Make sure you do not only include a description of the project, but also a reason why this project is important (i.e. motivation) (3pts)
* Related Work: Do not just summarize previous work, but relate it to your project. (3pt)
* Methods: What have you completed up to now? What do you plan on doing? Write down a concrete plan of action. (3pt)
* Data: Do not just list the datasets, but describe them, and explain how you will use them. (3pt)
* Evaluation Plan: What evaluation metrics you chose and why? Are they applicable to your task? (3pt)
* Preliminary Results: What have you noticed so far when making/running your system? How are they performing? (3pt)
* Attribution: Do not forget to note which team member will do what. (1pt)
</div>
