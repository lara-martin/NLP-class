---
title: CMSC 473/673 - Spring 2024 @ UMBC
layout: default
active_tab: about
---

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
<a href="https://laramartin.net/NLP-class{{page.url}}">{% if page.type %}{{page.type}} {{page.number}}: {% endif %}{{page.title}}</a> has been released.
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

</div>
-->
# CMSC 473/673 Natural Language Processing at UMBC

## Spring 2024

### Course Description
Natural language processing (NLP) is the field of working with language to automatically perform a variety of tasks, instead of or in collaboration with people. NLP can focus on the Generation (NLG) and/or Understanding (NLU) of natural language. Recently, large language models (LLMs) like ChatGPT have gotten the attention of the general public, but they have also greatly changed the landscape of modern NLP research.
This course will show you both old & new techniques that are still used today and will give you a basic understanding of why & how we do NLP.

### Learning Objectives
By the end of the course, you will be able to...
1. Recall common tasks in NLP and formulate problems for them.
2. Diagnose and setup appropriate evaluation metrics for a given problem, including determining what an appropriate baseline might be.
3. Compare and contrast language models and other NLP methods.
4. Implement AI systems that use popular NLP toolkits and libraries.
5. Construct a literature review from state-of-the-art research.
6. Plan and create an NLP system for a particular task.


### Staff
**Instructor**
: [Lara Martin](https://laramartin.net)
: [laramar@umbc.edu](mailto:laramar@umbc.edu)
: Office Hours: Tuesdays, 3-4pm ET and Wednesdays 2-3pm ET in ITE 216, also <a href="https://calendly.com/laramar/schedule">by appointment</a>.

**TA**
: Duong Ta
: [dta1@umbc.edu](dta1@umbc.edu)
: Office Hours: TBA in ITE 334, also <a href="mailto:">by appointment</a>.

### Logistics
**Time and Place**
: Spring 2024, Mondays & Wednesdays from 11:30 AM - 12:45 PM ET
: Interdisciplinary Life Sciences S 101
: First day of class is January 29, 2024
: Last day of class is May 15, 2024
<br><br>
**Textbooks**
: [Speech and Language Processing](https://web.stanford.edu/~jurafsky/slp3/) by Dan Jurafsky and James H. Martin
: [Introduction to Natural Language Processing](https://github.com/jacobeisenstein/gt-nlp-class/blob/master/notes/eisenstein-nlp-notes.pdf) by Jacob Eisenstein


#### Grading

| Assignment | 473 (undergrad) | 673 (grad) |
|----------------|---------------------|----------------|
| Class Knowledge Checks | 10% | 10% |
| Homeworks | 50% | 30% |
| Project | 40% | 40% |
| Grad Assignment | - | 20% |


#### Google Classroom
Google Classroom will be used for grading and most communication. (Please email [both Lara & Duong](mailto:laramar@umbc.edu;dta1@umbc.edu?subject=[CMSC 473/673] Need access to Google Classroom) specifying the email address you want to use, if you need to be added.)
Asynchronous questions to the instructor & TA or discussions with fellow classmates will be through Google Classroom.  There is no grade for discussions; they are only for your benefit.

Disclaimer: This is the first time that I'm using Google Classroom, so there might be some hiccups along the way.

#### Assignment Descriptions

**Class Knowledge Checks**
: These checks are in place to see how well you all are understanding the material as the course goes. These might look like clicker questions (using Poll Everywhere), "minute" questions to get you to think about the topic of the day, or a small in-class assignment. These will not be graded for accuracy, just whether or not you did them.
If you cannot attend a lecture for any reason, you can make up the "minute" questions or assignments in your own time. [Please ask Dr. Martin](mailto:laramar@umbc.edu?subject=[CMSC 473/673] Make-up clicker question) if you need to make up a day where we did only clicker questions.
Your two lowest grade class knowledge checks (i.e., incomplete or missing submissions) will be dropped.


**Homeworks**
: There are 3 homeworks: [NLP Tasks]() (learning objective 1), [NLP Evaluation]() (learning objective 2), [NLP Methods]() (learning objective 3). They each have a corresponding page on this website with more information.

**Project (learning objective 6)**
: Teams will come up with NLP project ideas (with the help of Lara & Duong) and implement them. There will be check-ins along the way to see how you are progressing and to see how well your team is working together. Teams can consist of both graduate and undergraduate students.
: [Milestone 1: Project Proposal](homeworks/project/proposal.html)
: [Milestone 2: Project Preparation and Informal Literature Review](homeworks/project/lit-review.html)
: [Milestone 3: Halfway Point]()
: [Milestone 4: Complete Draft](homeworks/project/draft.html)
: [Milestone 5: Final Submission](homeworks/project/final-submission.html)

**Graduate Assignment (learning objective 4 or 5)**
: If you are taking the graduate version of the course (CMSC 673), you will have an extra assignment that you need to complete. This assignment has two options that you can choose between (which you can choose depending on what career trajectory you plan). The graduate assignment is done individually.
: **Option 1: [Implementation]()** -- (suited for implementation-focused students) If you choose this option, you will pick an NLP tool from a list and implement it.
: **Option 2: [Paper]()** -- (suited for research-focused students) If you choose this option, you will find papers for and write up a literature review summarizing what you found.

### Class Policies
#### Late Day Policy
Each student has ten free "late days".  Homeworks can be submitted at most three days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. **Late days cannot be used on the project's final milestone or the final grad assignment milestone, which must be finished by the final day of class.**


#### Academic Integrity
If you are struggling because of the material or having difficulties completing the assignments on time, please [reach out to Dr. Martin](mailto:laramar@umbc.edu) rather than copying another student or looking up answers online. We can come up with a solution to help you out before you feel like you need to resort to cheating.

Plagiarism or any sort of cheating is not tolerated in this class. All work submitted must be your own (or, if permitted, with partners---see [Collaoration Policy](#collaboration-policy). If you are allowed external sources
on an assignment, please be sure to cite your source! This includes Large Language Models (LLMs): Please see [the next section](#generative-ai) for our policy specific to ChatGPT and other generative AI. Remember, reusing your own work from a different class is not permitted; this is self-plagiarism. If you are suspected of cheating, plagiarism, or other forms of academic dishonesty, your case will be brought to the attention of the Undergraduate Academic Conduct Committee or Graduate Council Grievance Committee and may result in an F in the course, depending on the Committee’s decision. **Your first offense will result in at least a 0 (zero) on the assignment.** If you would like more information on what constitutes as academic dishonesty, please consult [https://academicconduct.umbc.edu/](https://academicconduct.umbc.edu/).

#### Generative AI
If you use ChatGPT (or similar chatbots or AI-based generation tools), you must describe exactly how you used it, including providing the prompt, the original generation, and your edits. This applies to prose, code, or any form of content creation. Not disclosing is an academic integrity violation. If you do disclose, your answer may receive anywhere from 0 to full credit, depending on the extent of substantive edits, achievement of learning objectives, and overall circumvention of those objectives.

Use of AI/automatic tools for grammatical assistance (such as spell-checkers or Grammarly) or small-scale predictive text (e.g., next word prediction, tab completion) is okay. Provided the use of these tools does not change the substance of your work, use of these tools may be, but is not required to be, disclosed.

#### Collaboration Policy
##### Not allowed
The **homeworks** are designed for us to get an idea of how well you're picking up the material and applying it. Therefore, you are not allowed to collaborate on the homeworks.
The **graduate assignment** is also done individually.

##### Allowed
However, for the **project**, you are allowed to work in teams of 3-5. You can also discuss answers/submissions for the **class knowledge checks**.
You must clearly indicate the names of all people involved when submitting the assignment. You are also required to list who did what for the project milestones.

#### Technology Use
You're allowed to use your computer in class since the clicker questions will be by phone or web browser ([https://www.polleverywhere.com/](https://www.polleverywhere.com/).

##### Acknowledgements
Class materials have been borrowed from Dr. Chris Callison-Burch, Dr. Marine Carpuat, Dr. Frank Ferraro, and Dr. Alan Ritter. Generative AI policy is borrowed from Dr. Frank Ferraro.


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
