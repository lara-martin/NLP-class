---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: Final Submission
type: Project Milestone
number: 4
active_tab: homework
release_date: 2026-05-03
due_date: 2026-05-14 11:59:00ET
submission: https://blackboard.umbc.edu/ultra/courses/_96481_1/outline/assessment/test/_8407431_1?courseId=_96481_1&gradeitemView=details
online_submission: https://blackboard.umbc.edu/ultra/courses/_98413_1/outline/assessment/test/_8407383_1?courseId=_98413_1&gradeitemView=details
materials:
  -
    name: Poster Template
    url: poster-template.pptx
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
The presentation day will be on May 14, 2026 from 10:30am - 12:30pm in <b>SONDHEIM 101</b>.
Posters must be submitted by May 13th at 12pm or earlier to <a href="mailto:gweiss@csee.umbc.edu,skyejonke@umbc.edu">Geoff Weiss and Skye Jonke</a>.
Everything is due on Blackboard by {{ page.due_date | date: "%A, %B %-d, %Y" }} before 11:59PM.<br>
Submission Link (in-person section): <a href="{{page.submission}}">{{ page.submission }}</a><br>
Submission Link (online section): <a href="{{page.online_submission}}">{{ page.online_submission }}</a><br>
It makes it easier to grade if one person from each section (online and in-person) submits.<br><br>
Please be sure to double check the academic integrity and generative AI policies <a href="https://laramartin.net/NLP-class/#academic-integrity">listed on the syllabus</a>.
<br><br>
Examples from my previous AI class: <a href="https://docs.google.com/spreadsheets/d/1FnP2T5-VHwcEr3LfuJrPxgVEJhjsjpepHl3Ov1YWjlA/edit?usp=sharing">Here</a>
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
Here are the requirements for the final submission of your project. Please refer to the appropriate section below for your project type.




## How will the presentation day work?

### Getting Ready
* Posters should be size **22 x 34**. This can be 22" tall and 34" wide or vice versa.
	* The CSEE department has generously agreed to pay for and print the posters.
	* I have provided a Powerpoint [poster template]({{page.materials[0].url}}) for you to use. You're welcome to adapt it as much as you like except make sure to keep it 22 x 34 (or 34 x 22). It's currently set to 22 x 34.
	* You are not required to use the template at all, but make sure it's the correct size. You can also make a poster in LaTeX, if you prefer.
	* If you want Dr. Martin to look at your poster before you print it, be sure to give them a couple days before you want to print it.
	* Please email your poster to [Geoff Weiss and Skye Jonke](mailto:gweiss@csee.umbc.edu,skyejonke@umbc.edu) by **noon** on **December 10**.
	* Save your poster as a **pdf** before sending it to Geoff & Skye.
	* In addition to emailing the poster to print, please submit the pdf on Blackboard.
	* Your poster will be ready by 5:30pm on December 10th in ITE 325 by the front desk. It will need to be trimmed. **Please pick up your poster and trim it** before coming to the presentation day on December 11th. Please let Lara know if you can't pick the poster up during business hours (9am-5pm) so she can get it for you.
	

Here are some example posters from previous classes that I liked:
* [Example Poster 1](team1-poster.pdf)
* [Example Poster 2](team3-poster.pdf)
* [Example Poster 3](team6-poster.pdf)
	

### On Presentation Day
* Posters will be attached to the walls around the room (SOND 101).
* Please be in Sondheim 101 on time or a bit earlier!! (10:30am on December 11th)
* The presentations will be open to the university, broadly, but mostly focused on CSEE folks.
* Within your team, designate some members to be "group 1" and the rest to be in "group 2". The first half of the time group 1 will present and group 2 will walk around and look at other posters/demos. Everyone will switch halfway through so that you all get a chance to see each other's work. You don't have to tell us who is in which group; this is just to let you know what's going to happen on presentation day.
* There will be a voting box where visitors can vote for their favorite presentation(s). The team with the most votes will get 2 points of extra credit on Milestone 4.
* **For demo teams**: Please bring a laptop and charger, and have your demo ready to be played with.


### Poster Grading
The posters will be graded on two main criteria:
* __Content__: (10 points) The poster contains enough relevant information that someone can get the highlights of the project without you necessarily presenting (although you will still be presenting it).
	* Information is written in clear language.
	* It must contain: 1) an introduction to what you did, 2) information about the methods/system (you may include a system diagram), 3) what evaluations you did and their results, and 4) any discussion (for paper teams) or takeaways (for demo teams).
* __Visuals__: (4 points) The poster contains relevant visuals without overwhelming the reader, and the text organization is nicely displayed and not too "wordy".


<!--
## Video Presentation (5 points)
All presentations must be a pre-recorded video -- this will allow us to watch the presentations asynchronously while simultaneously leaving you with a nice artifact that you can show off to friends/colleagues/future employers.
* Each video should be about 5 minutes in length.
* Please feel free to use video editing software to cut down and refine your video presentation.
* You are welcome to have multiple team-members trade off speaking in the presentation or have a single presenter.
* This can be on any video hosting platform ([YouTube](https://www.youtube.com/), [Vimeo](https://vimeo.com/watch), etc.). Please double check that the video link is visible to the public before submitting. It can be unlisted. 

### Presentation Grading
Your presentation will be graded on the following criteria.
1. __Motivation__: The motivation for the project and how it relates to course material is clearly explained.
2. __Methods/Demo__: Your methods are explained well and in detail / your demo is thorough.
2. __Communication__: The method and final results are explained in a way the class can understand, without use of acronyms of terms we have not covered in class (unless you define them). The presentation seems polished.
3. __Results__: The main findings of the project are reported.
4. __Lessons Learned__: What did you learn from this project and what might you do differently next time? What questions or directions for future work remain?

-->

## Demo: Build a novel NLP system

The final deliverable is the demo itself, a poster , and a supplemental document. Your demo should be a complete program that can run end-to-end.

Your demo should:
* Be runable by the grader, following the read me.
* Be posted on GitHub (or the repository site of your choice).
* **Not** be edited after the deadline. We will be grading the last commit pushed before the deadline.

In a separate document called `team#-supplement.pdf`, provide the
* __Project Description__ - Updated to take feedback into consideration, otherwise you can just copy this from previous milestones.
* __Back End Architecture__ - Updated to include any changes you made. Include the updated system diagram.
* __Evaluation__ - Completed with a comparison of your system or components of your system to baselines. Share what you found both in terms of measurements and overall insights.
* __LLM Use Statement__ - Describe exactly how you used LLMs to generate **parts of your code** (<a href="https://laramartin.net/NLP-class/index.html#generative-ai">refer to the syllabus for guidance</a>). If you did not use **any** generative text, please state so in this section.

You no longer need to mention who did what on your team.



### What to Submit
* The link to your repository.
* `team#-poster.pdf`, your poster.
* `team#-supplement.pdf`with the 4 components mentioned above.



### Grading
<div class="alert alert-warning" markdown="1">
You will get full points if you 1) include all of the material listed above and 2) incorporate the feedback you got from the previous submission.<br>


<!--* Video Presentation - 5 points ([See description above.](#presentation-grading))-->
* Poster Content - 10 points ([See description above.](#poster-grading))
* Poster Visuals - 4 points
* Back End Architecture  - 2 points - Updated to reflect your final system. The system diagram can also be put on your poster, if you want.
* Evaluation - 5 points - Comparison is complete and shows off what works and doesn't work with your program.
* Minimal bugs - 5 points - Runs from beginning to end with minimal bugs (1-3 bugs, depending on the size/type of bug).
* Completeness - 10 points - The demo does what the previous milestones' architecture claim it would do (within reason).
* Read Me - 3 points - A short document explaining what your system is, and how to setup and run your demo. Put this readme in the README.md file of your repository.
* LLM Use Statement - 1 point

Total: 40 points
</div>
---

## Paper: Investigate an NLP research question

The final deliverable is the paper itself, a poster, and a supplemental document. The paper will be a continuation of the same one you've been building on.

Here are some example reports from previous classes again to aid you:
* [Example Report 1](example_report-2022-1.pdf)
* [Example Report 2](example_report-2022-2.pdf)
* [Example Report 3](example_report.pdf)




Your paper needs to be in a conference template, written in LaTeX.
* You can use [Overleaf](https://www.overleaf.com) to write LaTeX papers together. The CSEE department has a subscription to Overleaf now, so you should be able to have multiple collaborators on the same paper.
* If you do not have a conference/workshop in mind, I recommend that you use the [template from the Association for Computational Linguistics](https://www.overleaf.com/latex/templates/association-for-computational-linguistics-acl-conference/jvxskxpnznfj).




Your paper should include the following sections:
<div class="alert alert-warning" markdown="1">
Note that at this stage the questions below are *guiding* questions. Do not include the questions themselves in your paper and make sure that what you write in each section builds to be one cohesive section. Your content in each section should contain information beyond these questions as well.
</div>

<div class="alert alert-warning" markdown="1">
<b>Science 101</b><br>
A *research question* should be **something that can be proved true or false.** An example of a *bad* research question might be "Which dog is the best dog?" because it cannot be rejected (i.e., null hypothesis). <br> A *better* way to rephrase this---by potentially looking at the same problem---would be to ask "Is Pharaoh a good dog?". This can then be tested. You just need to define how to measure "goodness" in this case.
</div>

Your paper should have the following components, in order:

1. __Title__: What are you calling your study?
2. __Abstract__: A high-level overview of the paper and what people should take away from it if they aren't reading the whole thing.
3. __Introduction__: What research question(s) or problem are you trying to solve? (Start numbering sections from here.)
  - Why this it worth researching?
  - What contributions does this work make? (i.e., What are you doing that's novel?) You might have to compare to other research.
4. __Related Work__: What previous research has been done on this research question?
  - A narrative of 8-10+ related research papers, including how each of them is relevant to this work.
5. __Methods__: What are you doing or making to address your research question(s)?
  - If you are using any datasets, does the needed data already exist?  If so, how much data is available? What does the data look like? If you are just using a few examples for few-shot prompting, how did you select those?
  - Describe your solution to the problem/research question. What model(s) are you using? If you are using few- or zero-shot prompting, what do your prompts look like?
5. __Evaluation__: *Renamed from Experiments section* What experiments will you be running?
  - What are you measuring and why? What evaluation metrics do you plan to use to answer your research question(s)?
  - What are your proposed *baselines*? (That is, what are you comparing your method against?)
  - How do these experiments answer your research questions?
6. __Results__: What did you find from your evaluation?
	- This should be more than just a list of raw numbers. You should explain to the reader how to interpret any graphs or tables you have and describe any trends that you see.
7. __Discussion__: What insights can you take away from the results? What do the results mean for your research question?
8. __Conclusion__: In CS, this is often just a brief paragraph reminding people what the highlights of your paper were.
9. __References__: Papers are cited correctly in the conference's format and are references in the main text. (Do not number this section.)

In a separate document called `team#-supplement.pdf`, provide the
__LLM Use Statement__: Describe exactly how you used LLMs to generate parts of your paper (<a href="https://laramartin.net/NLP-class/index.html#generative-ai">refer to the syllabus for guidance</a>). If you did not use **any** generative text, please state so in this section.

You no longer need to mention who did what on your team.

### What to Submit
* `team#-finaldraft.pdf` which is your final paper.
* `team#-poster.pdf`, your poster.
* `team#-supplement.pdf`, the LLM use statement.


### Grading
<div class="alert alert-warning" markdown="1">

* Poster Content - 10 points ([See description above.](#poster-grading))
* Poster Visuals - 4 points
* Abstract - 3 points - Abstract is short but thoroughly describes what the paper is about.
* Results - 5 points - Data is explained and tables/graphs are made to accompany the text.
* Discussion - 5 points - Insights make sense and show that the results were thought about deeply.
* References - 2 points - Papers are correctly cited.
* Completeness - 10 points - All sections listed above are included, paper seems cohesive, and paper is in correct format.
* LLM Use Statement - 1 point

Total: 40 points
</div>
