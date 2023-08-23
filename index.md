---
title: CMSC 671-01 Principles of Artificial Intelligence - UMBC
layout: default
active_tab: main_page 
---

<!--
<div class="alert alert-warning" markdown="1">
Want to join the class, but didn't attend the first lecture? Here are the steps to follow:
1. [Get a permit by signing yourself up for CIS 700-001 via the waitlist system](https://forms.cis.upenn.edu/waitlist/index.php).  
2. [Do the for-credit in-class assignment from the first lecture](http://interactive-fiction-class.org/in_class_activities/play-text-adventures/play-text-adventures.html).
3. [Listen to recording of the first lecture](https://upenn.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx?folderID=8b5f2734-0738-4f52-90f5-ab3c01236b7c) and [look over the slides](http://interactive-fiction-class.org/slides/text-adventure-games.pdf).
4. [Complete the first homework assignment before class on Thursday](http://interactive-fiction-class.org/homeworks/text-adventure-game/text-adventure-game.html).
</div>
-->

<!--
<div class="alert alert-success" markdown="1">
[Post your game here.](https://docs.google.com/document/d/1XpBEevYpHvLjCr-3CkAhERN_GPHsjNmkPo-Wf9KjxDs/edit?usp=sharing)
</div>
-->

<!-- Display an alert about upcoming homework assignments -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% for page in site.pages %}
{% if page.release_date and page.due_date %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%s'}}{% endcapture %}
{% if release_date < now and due_date >= now %}
{% if page.type == "in-class" %}
<!-- In class activity -->
<div class="alert alert-info">
The in-class activity for {{ page.release_date | date: "%A %b %-d" }} will be to <a href="{{page.url}}">{{ page.title }}</a>.  
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
<a href="{{page.url}}">{{page.type}} {{page.number}}: {{page.title}}</a> has been released.  
{% if page.deliverables %}
The assignment has multiple deliverables.
<ul>
{% for deliverable in page.deliverables %}
<li>{{ deliverable.due_date | date: "%b %-d, %Y" }} - {{deliverable.description}}.</li>
{% endfor %}
</ul>
{% else %}
It is due before {{ page.due_date | date: "%I:%M%p" }} on {{ page.due_date | date: "%A, %B %-d, %Y" }}.
{% endif %}
</div>
{% endif %}
{% endif %}
{% endif %}
{% endfor %}
<!-- End alert for upcoming homework assignments -->


<!--
<div class="alert alert-success" markdown="1">
A great example of what you could build if you take this class is the [AI Dungeon](https://play.aidungeon.io/), which is an interactive fiction game  that was developed by a student at BYU using [Open AI's GPT-2](https://openai.com/blog/better-language-models/) large scale language model.
</div>
-->
<!--
<div class="alert alert-success" markdown="1">
First day of class is Thursday, January 13, 2022 at 1:45pm-3:15pm Eastern. It will take place virtually. Here is the [Zoom link](https://upenn.zoom.us/j/95868341588?pwd=a0NvbkhtUEdYTTk5d0Vmc2VvcHJrUT09). We look forward to seeing you there!
</div>
-->
# CMSC 671-01 Principles of Artificial Intelligence at UMBC


### Course Description
Artificial Intelligence (AI), the study of how machines can behave in an intelligent, human-like manner, is shaping the way we interact with modern technology on a daily basis. In this introductory course, we will discuss what an intelligent agent is, and explore how an agent can solve problems by searching, make informed decisions, reason under uncertainty, and even learn. This course will help you develop the general foundational tools necessary to implement your own intelligent agents, understand the methods behind recent advances in AI, and pursue more specialized AI applications, including game AI, knowledge representation, machine learning, natural language processing, computer vision, planning, robotics, and more.

### Learning Objectives
By the end of the course, you will be able to...
* Predict the behavior of different search algorithms
* Define decision making problems, and implement agents that can solve them
* Apply probabilistic reasoning to problems with uncertainty
* Compare and contrast machine learning methods, and determine an appropriate method for a given
problem
* Reflect on the societal impacts of the AI methods and applications discussed in class


### Staff
Instructor
: [Lara Martin](https://laramartin.net)
: [laramar@umbc.edu](mailto:laramar@umbc.edu)
: Office Hours: Tuesdays, 2:30-3:30pm EST and Fridays 10am-11am EST in ITE 216, also <a href="https://calendly.com/laramar/schedule">by appointment</a> 

TA
: [Aydin Ayanzadeh]()
: [aydina1@umbc.edu](mailto:aydina1@umbc.edu)
: Office Hours: 

### Logistics
Time and Place
: Fall 2023, Tuesdays & Thursdays from 1:00-2:15pm EST
: Janet & Walter Sondheim 103
: First day of class is August 31, 2023
: Last day of class is December 12, 2023



Textbook
: [Artificial Intelligence: A Modern Approach](http://aima.cs.berkeley.edu/) (fourth edition) by Stuart Russell and Peter Norvig. AI is moving fast, so the edition matters! A digital version of the textbook can be found through Blackboard under "My Textbooks & Course Resources".


Grading
: 
* 10% Class Knowledge Checks
* 5% Paper Presentation
* 50% Homeworks (5 in total; 10% each)
* 10% Midterm
* 25% Final Project


Asynchronous questions to the instructor & TA or discussions with fellow classmates will be through the class's [Blackboard under "Discussions"](https://blackboard.umbc.edu/ultra/courses/_76209_1/engagement). There is no grade for these discussions; they are only for your benefit. If you have a question that is specific to you, please email [both Lara & Aydin](mailto:laramar@umbc.edu;aydina1@umbc.edu) with _[CMSC 671]_ at the beginning of the subject line.

Class Knowledge Checks
: These checks are in place to see how well you all are understanding the material as the course goes. There will be a synchronous and an asynchronous option:
* Synchronous: clicker questions in class, in-class assignments
* Asynchronous: minute questions, make-up in-class assignments

Paper Presentations
: Over the course of the semester, each student must prepare a 10-15 minute presentation on a research paper relevant to the course. Since these presentation will be a substantial component of the learning experience in the class, slides must be prepared and emailed to us at least 72 hours in advance of the lecture they will be presented in (e.g., by 3PM on the Monday before the presenation date), so that we can provide feedback on them. Failure to send us the slides ahead of time will result in a grade penalty on the presentation. 

Homeworks
: 

Midterm
: 

Final Project
: 

Collaboration Policy
: Unless otherwise noted, you ARE allowed to work in pairs on the homework assignments and the paper presentation, and teams of 3-5 for the final project. You must clearly indicate the names of all people involved when submitting the assignment, attributing who did what for the assignment.
Please note that you are **NOT allowed to collaborate on the midterm.**

Late Day Policy
: Each student has five free "late days".  Homeworks can be submitted at most two days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. **Late days only apply to the homeworks. They cannot be used on the final project, which must be finished by the final day of class.  Late days may not be used for paper presentations.**



Class materials have been borrowed from Dr. Chris Callison-Burch, Dr. Tim Finin, Dr. Cassandra Kent, Dr. Cynthia Matuszek, and Dr. Mark Riedl.


------
## UMBC School Policies

### Accessibility and Disability Accommodations, Guidance and Resources
Accommodations for students with disabilities are provided for all students with a qualified disability under the Americans with Disabilities Act (ADA & ADAAA) and Section 504 of the Rehabilitation Act who request and are eligible for accommodations. The Office of Student Disability Services (SDS) is the UMBC department designated to coordinate accommodations that creates equal access for students when barriers to participation exist in University courses, programs, or activities.

If you have a documented disability and need to request academic accommodations in your courses, please refer to the SDS website at [sds.umbc.edu](http://sds.umbc.edu/) for registration information and office procedures.

SDS email: [disability@umbc.edu](mailto:disability@umbc.edu)

SDS phone: [410-455-2459](tel:410-455-2459)

If you will be using SDS approved accommodations in this class, please contact the instructor to discuss implementation of the accommodations. During remote instruction requirements due to COVID, communication and flexibility will be essential for success.

### Sexual Assault, Sexual Harassment, and Gender Based Violence and Discrimination
[UMBC Policy](https://ecr.umbc.edu/gender-discrimination-sexual-misconduct/) in addition to federal and state law (to include Title IX) prohibits discrimination and harassment on the basis of sex, sexual orientation, and gender identity in University programs and activities. Any student who is impacted by sexual harassment, sexual assault, domestic violence, dating violence, stalking, sexual exploitation, gender discrimination, pregnancy discrimination, gender-based harassment, or related retaliation should contact the University’s Title IX Coordinator to make a report and/or access support and resources. The Title IX Coordinator can be reached at [titleixcoordinator@umbc.edu](mailto:titleixcoordinator@umbc.edu) or [410-455-1717](tel:410-455-1717).

You can access support and resources even if you do not want to take any further action. You will not be forced to file a formal complaint or police report. Please be aware that the University may take action on its own if essential to protect the safety of the community.

If you are interested in making a report, please use the [Online Reporting/Referral Form](https://umbc-advocate.symplicity.com/titleix_report/index.php/pid419318?).  Please note that, if you report anonymously, the University’s ability to respond will be limited.

**Notice that Faculty and Teaching Assistants are Responsible Employees with Mandatory Reporting Obligations**

All faculty members and teaching assistants are considered Responsible Employees, per UMBC’s [Policy on Sexual Misconduct, Sexual Harassment, and Gender Discrimination](https://ecr.umbc.edu/policy-on-sexual-misconduct-sexual-harassment-and-gender-discrimination/). Faculty and teaching assistants therefore required to report all known information regarding alleged conduct that may be a violation of the Policy to the Title IX Coordinator, even if a student discloses an experience that occurred before attending UMBC and/or an incident that only involves people not affiliated with UMBC.  Reports are required regardless of the amount of detail provided and even in instances where support has already been offered or received.

While faculty members want to encourage you to share information related to your life experiences through discussion and written work, students should understand that faculty are required to report past and present sexual harassment, sexual assault, domestic and dating violence, stalking, and gender discrimination that is shared with them to the Title IX Coordinator so that the University can inform students of their [rights, resources, and support](https://ecr.umbc.edu/rights-and-resources/).  While you are encouraged to do so, you are not obligated to respond to outreach conducted as a result of a report to the Title IX Coordinator.

If you need to speak with someone in confidence, who does not have an obligation to report to the Title IX Coordinator, UMBC has a number of [Confidential Resources](https://ecr.umbc.edu/policy-on-sexual-misconduct-sexual-harassment-and-gender-discrimination/#confidential-resources) available to support you: 

[Retriever Integrated Health](https://health.umbc.edu/) (Main Campus): [410-455-2472](tel:410-455-2472); Monday – Friday 8:30 a.m. – 5 p.m.; For After-Hours Support, Call 988.

[Center for Counseling and Well-Being](https://shadygrove.umd.edu/student-affairs/counseling-well-being) (Shady Grove Campus): [301-738-6273](tel:301-738-6273); Monday-Thursday 10:00a.m. – 7:00 p.m. and Friday 10:00 a.m. – 2:00 p.m. (virtual) [Online Appointment Request Form](https://shadygrove.titaniumhwc.com/)

Pastoral Counseling via [The Gathering Space for Spiritual Well-Being](https://i3b.umbc.edu/spaces/the-gathering-space-for-spiritual-well-being/): [410-455-6795](410-455-6795); [i3b@umbc.edu](mailto:i3b@umbc.edu); Monday – Friday 8:00 a.m. – 10:00 p.m.

#### Other Resources

[Women’s Center](https://womenscenter.umbc.edu/) (open to students of all genders): [410-455-2714](tel:410-455-2714); [womenscenter@umbc.edu](mailto:womenscenter@umbc.edu); Monday – Thursday 9:30 a.m. – 5:00 p.m. and Friday 10:00 a.m. – 4 p.m.

[Shady Grove Student Resources](https://ecr.umbc.edu/shady-grove-title-ix-resources/), [Maryland Resources](https://ecr.umbc.edu/maryland-resources/), [National Resources](https://ecr.umbc.edu/national-resources/).

#### [Child Abuse and Neglect](https://ecr.umbc.edu/child-protection/)

Please note that Maryland law and [UMBC policy](https://education.umbc.edu/child-abuse-reporting-policy//) require that faculty report all disclosures or suspicions of child abuse or neglect to the Department of Social Services and/or the police even if the person who experienced the abuse or neglect is now over 18.

### [Pregnant and Parenting Students](https://www2.ed.gov/about/offices/list/ocr/docs/pregnancy.html)
UMBC’s [Policy on Sexual Misconduct, Sexual Harassment and Gender Discrimination](https://ecr.umbc.edu/policy-on-sexual-misconduct-sexual-harassment-and-gender-discrimination/) expressly prohibits all forms of discrimination and harassment on the basis of sex, including pregnancy. Resources for pregnant, parenting and breastfeeding students are available through the University’s [Office of Equity and Civil Rights](https://ecr.umbc.edu/students/).  Pregnant and parenting students are encouraged to contact the Title IX Coordinator to discuss plans and ensure ongoing access to their academic program with respect to a leave of absence – returning following leave, or any other accommodation that may be needed related to pregnancy, childbirth, adoption, breastfeeding, and/or the early months of parenting.

In addition, students who are pregnant and have an impairment related to their pregnancy that qualifies as disability under the ADA may be entitled to accommodations through the [Office of Student Disability Services](https://sds.umbc.edu/accommodations/registering-with-sds/).

### Religious Observances & Accommodations
UMBC [Policy](https://provost.umbc.edu/wp-content/uploads/sites/46/2022/08/Religious-Observance-Academic-Policy-2022_2023.pdf) provides that students should not be penalized because of observances of their religious beliefs, and that students shall be given an opportunity, whenever feasible, to make up within a reasonable time any academic assignment that is missed due to individual participation in religious observances. It is the responsibility of the student to inform the instructor of any intended absences or requested modifications for religious observances in advance, and as early as possible. For questions or guidance regarding religious observances and accommodations, please contact the Office of Equity and Civil Rights at [ecr@umbc.edu](mailto:ecr@umbc.edu).

### Hate, Bias, Discrimination and Harassment
UMBC values safety, cultural and ethnic diversity, social responsibility, lifelong learning, equity, and civic engagement.

Consistent with these principles, [UMBC Policy](https://ecr.umbc.edu/discrimination-and-bias/) prohibits discrimination and harassment in its educational programs and activities or with respect to employment terms and conditions based on race, creed, color, religion, sex, gender, pregnancy, ancestry, age, gender identity or expression, national origin, veterans status, marital status, sexual orientation, physical or mental disability, or genetic information.

Students (and faculty and staff) who experience discrimination, harassment, hate, or bias based upon a protected status or who have such matters reported to them should use the [online reporting/referral form](https://umbc-advocate.symplicity.com/titleix_report/index.php/pid954154?) to report discrimination, hate, or bias incidents. You may report incidents that happen to you anonymously. Please note that, if you report anonymously, the University’s ability to respond may be limited.