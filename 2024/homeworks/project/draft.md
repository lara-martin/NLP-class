---
layout: default-2024
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/
title: Final Report Draft
type: Project Milestone
number: 4
active_tab: homework
release_date: 2024-04-20
due_date: 2024-05-03 23:59:00EST
submission: https://classroom.google.com/c/NjUwNDE2MzEwMzQx/a/NjUyODk1MTIxMTcz/details
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

For this Milestone, we are requiring you to write a rough draft of your final report (with appropriate blanks for experiments you have not yet conducted) by building on the report you've been iterating on this semester. While this may sound strange (How can I write the final report without having results?), writing a draft of the final report early can be a very effective technique for organizing your thoughts and final experiments. Your project should be about ~85% complete at this stage.

We want to emphasize that you shouldn't stress out too much about making this submission perfect but we highly recommend taking this opportunity to write a solid first draft. Your future selves will be thankful!

To be specific, for this Milestone, you should:
* Finish all baseline experiments and get as many preliminary results from your main experiments as possible. You should show significant progress towards your main experimental results.
* Create your final report using the provided conference paper template: [ACL](https://github.com/acl-org/acl-style-files) (Please ask us directly if you would like to use a template for a different conference. Also, if you are not familiar with LaTeX and would like to try using it, let us know.) 
* Fill in as much of the final report as possible given your current results. Your report contain the sections outlined below. 

## Project Final Report
Your final report is a document that describes what you have accomplished in your project this semester. You are welcome and *encouraged* to draw content from the previous reports you have submitted so far. You should use journal and conference papers as inspiration for what a good writeup looks like.

### Report Sections
The report should have the following sections. A lot of these can be reused and "fleshed out" from the previous Milestones.

__Title__ & __Author Names__: What are you calling your project? These are not graded but still important! (No section header for these bits)
1. __Project Description__: This is the "what" and the "why" of your project. 
 * The "what": Explain the main idea of your project and what you are trying to accomplish. It's okay if these have changed.
 * The "why": If it's a research project, what's your research question (i.e., what are you trying to prove with this work)? If it's an artifact that you're creating, why are you creating it (e.g., who would use it)?
2. __Related work__: What previous research will you be using or building off of? What work are you inspired by? Tell a short "story" starting with what you found out from the Lit Review.
3. __Methods__: What are the steps you took to accomplish your project? This section should include enough detail that someone reading it could reasonably attempt to reproduce your work. Include figures if applicable.
4. __Data__: Describe what your data is in detail. For example, what data have you decided to use? Where did you get it from, what does it look like, and what are some potential problems with it? If you are using few/zero shot prompting, what are some of your initial prompts? How have they been working?
5. __Evaluation__: How are you evaluating your results? How do you know if you've answered your research question? If you're creating an NLP system, what do you use to determine that it's working well?
  * These can be things like accuracy, diversity metrics, perplexity, BLEU/ROUGE scores, success rate, human evaluation scores, etc. depending on your project.
6. __Results__: Describe your main results as well as the results for intermediate steps that build toward your main project goal. (Note for the milestone: If you are still waiting on important results, please talk about them and how they will fit into the final report.) **Negative results or plans for experiments to run are great to report too!** Please include tables, plots, and example system outputs where applicable.
7. __Discussion__: This is a _meta_ section to discuss how the project went.
What things did you try that didn't work out? If you were to start over from scratch, what would you do differently? If someone were to continue working on this project, what do you suggest are good next steps/good future work?
8. __Attribution__: For each of your teammates, write a couple sentences describing their main contributions to the project. If you have any concerns about distribution of work, feel free to email us directly. This will not be in the final write-up, but we want to make sure you all still have a final plan for who will be doing what for the last part of the project.

### Grading
This section is our grading rubric for the final report. This Milestone will not be graded too harshly but please keep these guidelines in mind. The more effort you put into this draft, the better our suggestions can be so that you can have a great final draft for the next Milestone.

1. __Formatting__: All of the sections described in the previous section are present and clearly marked. The report includes a title of the project and the name of the authors at the top. Images, tables, and other figures have captions and are referenced in the text. The paper makes use of citations that follow the standard convention of the conference template.
2. __Communication__: Your report should be targeted at an audience who is familiar with NLP but has not taken the class and knows nothing about what you have done so far. You can imagine your audience as either the readers of a technical blog post (if you took the NLP system option) or as reviewers of a paper submission to an AI conference such as ACL (if you took the research question option). You should aim to make your methods section clear enough that others could attempt to reproduce your work and your results section clear enough that readers understand exactly what experiments you ran.
3. __Style__: You should write in paragraphs and complete sentences unless there is a very good reason not to.
4. __Content__: The report answers all relevant questions posed in the previous section. Images, tables, plots, of other figures are used to support the report contents.
5. __Length__: There is no strict word length requirement, but if your paper has fewer than 1,500 words (not including references) then it is very likely you have not provided enough detail.

<div class="alert alert-warning" markdown="1">
* Formatting - 1 point
* Communication - 2 points
* Style - 1 point
* Content (description, related work, methods, data, evaluation, results, discussion) - 7 x 3 points each =  21 points
* Attribution - 1 point
* Length - 1 point
</div>

# What to Submit
Submit the following to [Google Classroom]({{page.submission}}):
* `group[#]-milestone4.pdf` which contains your rough draft submission. To make grading easier, your report should include section headers corresponding to each of the bulleted points. As stated earlier, you are now required to use the [template from ACL](https://github.com/acl-org/acl-style-files) for this milestone.
