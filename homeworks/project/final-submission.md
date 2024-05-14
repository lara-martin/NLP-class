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



