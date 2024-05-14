---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: Final Submission
type: Project Milestone
number: 5
active_tab: homework
release_date: 2024-05-01
due_date: 2024-05-17 10:30:00ET
submission: https://classroom.google.com/c/NjUwNDE2MzEwMzQx/a/NjgyNTMzMjk5ODEy/details
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
Your video is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. Add the link to the <a href="https://docs.google.com/spreadsheets/d/1bJuRQ0-dZ74hndlscTMMC3p-jLSxFsY50V8mqyrEudw/edit?usp=sharing">spreadsheet</a> to submit.<br>
Your paper is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before 11:59PM. Paper Submission Link: <a href="{{page.submission}}">{{page.submission}}</a>
<br><br>
Examples from last semester's AI class: <a href="https://docs.google.com/spreadsheets/d/1FnP2T5-VHwcEr3LfuJrPxgVEJhjsjpepHl3Ov1YWjlA/edit?usp=sharing">Here</a>
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
For your final project you should prepare a 2 minute video presentation for the class and a report documenting what you accomplished. **The video presentation submission is due {{ page.due_date | date: "%B %-d" }} before the exam time ({{ page.due_date | date: "%I:%M%p" }}) and the final report is due on {{ page.due_date | date: "%B %-d" }} at 11:59PM.**

## Video Presentation (5 points)
For this semester we are requiring all presentations to be in pre-recorded video form -- this will allow us to move through presentations quickly while simultaneously leaving you with a nice artifact that you can show off to friends/colleagues/future employers.
We will be enforcing a strict time limit of 2 minutes for the video submission so please do not exceed that.
To that end, please feel free to use editing software such as iMovie or Windows Movie Maker to edit down and refine your video presentation.
As long as you stay within the time limit, you are welcome to have multiple team-members trade off speaking in the presentation.
Finally, if you have built a system, you should try to include a quick demo of it (it can be sped up) or screenshots of it in your video presentation.

### Presentation Grading
Your presentation will be graded on the following criteria.
1. __Length__: The presentation length does not exceed 2 minutes.
2. __Motivation__: The motivation for the project and how it relates to course material is clearly explained.
3. __Communication__: The method and final results are explained in a way the class can understand, without use of acronyms of terms we have not covered in class (unless you define them).
4. __Results__: The main findings of the project are reported.
5. __Lessons Learned__: What did you learn from this project and what might you do differently next time? What questions or directions for future work remain?


## Project Final Report (28 points)
Your final report is a document that describes what you have accomplished in your project this semester. You are very welcome and *encouraged* to draw content from all previous reports you have submitted so far. At this point in the class, all of you have read and presented on academic papers. You should use those journal and conference papers as inspiration for what a good writeup looks like.

For your final report, the use of a conference template is **required**. You should use the [template from ACL](https://github.com/acl-org/acl-style-files). Please directly message us if you'd like to use a template from a different conference.

### Report Sections
The report should have the following sections.

__Title__ & __Author Names__: What are you calling your project? These are not graded but still important! (No section header for these bits)
1. __Project Description__: This is the "what" and the "why" of your project. 
 * The "what": Explain the main idea of your project and what you are trying to accomplish. It's okay if these have changed since the project proposal.
 * The "why": If it's a research project, what's your research question (i.e., what are you trying to prove with this work)? If it's an artifact that you're creating, why are you creating it?
 * Link to your code repository.
2. __Related work__: What previous research will you be using or building off of? What work are you inspired by? Don't just list previous work and summarize their contributions, rather, tell a short "story" using what you found out from the Literature Review. Explain how your work fits into the broader context.
3. __Methods__: What are the steps you took to accomplish your project? This section should include enough detail that someone reading it could reasonably attempt to reproduce your work. Include figures if applicable.
4. __Data__: Describe what your data is in detail. For example, what data have you decided to use? Where did you get it from, what does it look like, and what are some potential problems with it? If you are using few/zero shot prompting, what are some of your initial prompts? How have they been working?
5. __Evaluation__: How did you evaluate your results? How do you know if you've answered your research question? If you're creating an NLP system, what do you use to determine that it's working well?
  * These can be things like accuracy, diversity metrics, perplexity, BLEU/ROUGE scores, success rate, human evaluation scores, etc. depending on your project.
6. __Results__: Describe your main results as well as the results for intermediate steps that build toward your main project goal. Please include tables, plots, and example system outputs where applicable. Feel free to include negative results in this section as well.
7. __Discussion__: This is a _meta_ section to discuss how the project went.
What things did you try that didn't work out? If you were to start over from scratch, what would you do differently? If someone were to continue working on this project, what do you suggest are good next steps/good future work?

## Group Feedback (1 point)
You are also required to submit [this feedback form](https://docs.google.com/forms/d/e/1FAIpQLSdMVDwgj069f6U7H1UbAcBV2epp8XeUk9zOuAiZuquihPCP8A/viewform?usp=sf_link) for each member of your group.

## Extra Credit: Popular Choice (2 points)
Your classmates will vote on whose project & presentation was the coolest. This team will get 2 points.

### Grading
This section is our grading rubric for the final report. 

1. __Formatting__: All of the sections described in the previous section are present and clearly marked. The report includes a title of the project and the name of the authors at the top. Images, tables, and other figures have captions and are referenced in the text. The paper uses the [ACL template](https://github.com/acl-org/acl-style-files) (or other approved template). The paper makes use of citations that follow the standard convention of whatever conference the template is from.
2. __Communication__: Your report should be targeted at an audience who is familiar with NLP but has not taken the class and knows nothing about what you have done so far. You can imagine your audience as either the readers of a technical blog post (if you took the system option) or as reviewers of a paper submission to a conference such as ACL or EMNLP (if you took the research question option). You should aim to make your methods section clear enough that others could attempt to reproduce your work and your results section clear enough that readers understand exactly what experiments you ran.
3. __Style__: You should write in paragraphs and complete sentences unless there is a very good reason not to.
4. __Content__: The report answers all relevant questions posed in the previous section. Images, tables, plots, of other figures are used to support the report contents.
5. __Length__: There is no strict word length requirement, but if your paper has fewer than 1,500 words (not including references) then it is very likely you have not provided enough detail.

<div class="alert alert-warning" markdown="1">
Presentation
* Length - 1 point
* Motivation - 1 point
* Communcation - 1 point
* Results - 1 point
* Lessons Learned - 1 point

Report
* Formatting - 3 points
* Communication - 3 points
* Style - 1 point
* Content - 7 x 3 points each = 21 points

Group Feedback - 1 point

Extra Credit (Popular Choice) - 2 points extra credit
</div>

# What to Submit
Every member of your team needs to fill out [this feedback form](https://docs.google.com/forms/d/e/1FAIpQLSdMVDwgj069f6U7H1UbAcBV2epp8XeUk9zOuAiZuquihPCP8A/viewform?usp=sf_link).

Submit the following to the spreadsheet before the exam period ({{ page.due_date | date: "%I:%M%p" }}) on **{{ page.due_date | date: "%A, %B %-d}}**:
* A link to your pre-recorded video presentation. This can be on any video hosting platform ([YouTube](https://www.youtube.com/), [Vimeo](https://vimeo.com/watch), etc.). Please double check that the video link is visible to the public before submitting. It can be unlisted. 

Submit the following to Google Classroom by 11:59 PM on **{{ page.due_date | date: "%A, %B %-d}}**:
* `group#-final-report.pdf` which contains your project report. The use of a conference template is required. Use the [template from ACL](https://github.com/acl-org/acl-style-files) or please message us directly if you'd like to use a template from a different conference.
  * Note that this report includes the link to your code repo!
