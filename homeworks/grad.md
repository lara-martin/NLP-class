---
layout: default
img: 
caption: 
img_link: 
title: Graduate Assignment (15% of grade)
active_tab: homework
release_date: 2025-02-28
due_date1: 2025-03-24 23:59:00EST
due_date2: 2025-04-24 23:59:00EST
due_date3: 2025-05-01 23:59:00EST
due_date_final: 2024-05-15 23:59:00EST
---


<div class="alert alert-info">

Checkpoint 1 due: {{ page.due_date1 | date: "%A, %B %-d, %Y" }}<br>
Checkpoint 2 due: {{ page.due_date2 | date: "%A, %B %-d, %Y" }}<br>
Checkpoint 3 due: {{ page.due_date3 | date: "%A, %B %-d, %Y" }}<br>
Final submission due: {{ page.due_date_final | date: "%A, %B %-d, %Y" }}<br>
All due dates are {{ page.due_date1 | date: "%I:%M%p" }} ET.
<br><br>
Submissions are under the "Grad Assignment" folder on Blackboard.<br><br>
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


{{page.title}}
=============================================================

## Learning Objectives

* Implement AI systems that use popular NLP toolkits and libraries.
or
* Construct a literature review from state-of-the-art research.

## Submissions
All milestones must be met for full credit. 

| Item | If you select from the Implementation Track: | If you select from the Paper Track: | Grade |
| ---- | ------------------------- | ------------------- | -----------|
| Checkpoint 1 | Selection of one project type and initial implementation idea | Selection of topic and initial list of papers | Ungraded |
| Checkpoint 2 | Initial report discussing progress, hurdles, and other challenges; and git repo containing at least three non-trivial/starter commits | Complete first draft, including citations | Ungraded |
| Checkpoint 3 | [Feedback/suggestions on 2 other students' initial reports](https://drive.google.com/file/d/1d_YcRGmIRbJavs2nKFaBf-dKOZybtam4/view) | [Peer review](https://drive.google.com/file/d/1kEbMa1gAvkH-y-DiO_lbnzIoJNWe0n4-/view) | 10 points |
| Final Submission | Completed code, full git repository, completed writeup, and document summarizing how the feedback was used | Completed final paper + summary-of-changes document | 40 points |
| Final grade | || = total / 50|


## Description
For the graduate assignment, choose ONE of the following
assessments.
The possible assessments are divided into an “Implementation Track,” and a “Paper Track”. Both tracks
consist of advanced topics that we may very lightly cover, or mention, in the course. However, we will not
spend significant time on any of them.
The Implementation Track will require you to implement and adapt NLP techniques. For the Paper Track, you will write a 4-page conference-style literature review paper on a particular topic.
While each person is free to choose which of these two options they will complete, I encourage each person to strongly consider how each may be able to further their career/degree goals and choose the assessment that maximizes progress toward that goal. For example, someone writing a disseration (doctoral or masters) may wish to do the literature review paper, since it could help form the basis of the related work chapter of a dissertation. On the other hand, someone may wish to really dive deep into an aspect of NLP implementation.


---

## Implementation Track
Implement your proposed solution from [HW 1](https://laramartin.net/NLP-class/homeworks/hw1.html) for **one** of the three parts (a, c, or e):

a. The user types in a keyword that they’re interested in, and the app finds relevant textbooks.
c. The app displays a question relevant to the chapter.
e. The app gives a numerical score for how well the user answered the question.

Once you select which problem you will do, the rest of the project will include:
1. finding potential methods for implementing it and/or finding existing repositories that tackle some of the components you want
2. finding a dataset that will help create the system
3. adapting the models/code/libraries to fit your problem
4. evaluating your system

At the end of the semester, you will submit:
* A link to your repository
* A writeup document that describes:
	* Your reasoning behind the methodology that you used
	* How you found the repositories you are using and why you decided to pick that particular implementation
	* Any hurdles you encountered in your implementation
	* How you found and modified your data
	* What evaluation metrics you used and why
	* A table of the results of your evaluation
	* A comparison of your system to a zero-shot prompted GPT-3.5 model
	* An analysis of what you would've done differently in retrospect


<div class="alert alert-danger">
Please cite all code that you find and adapt for your project. Since there aren't standardized ways to cite existing code, you can put the link to the repository/StackOverflow question/tutorial in a comment before the chunk of code that you took (and potentially adapted) from that source. If it's not clear what you took from the source, please explain what you took or how you were inspired by the algorithm in a comment.
If you fail to do this, this will be seen as an academic integrity violation and you will get a zero on the assigment.<br><br>
Furthermore, you are not allowed to simply take a repository and use it for your entire solution. If your code is found to be significantly similar to an existing repository (even if you cite it), you will get a zero on the assignment.<br><br>
Please cite any AI-generated code in the way that is specified in the course syllabus.
</div>


Accounting for items like tables
and graphs, an appropriate target length of this writeup should be approximately 2-4 pages.
Within the Implementation Track, you will be primarly evaluated on the completeness
of your implementation. However, the thoroughness and clarity of the writeup will be a sizeable (but non-majority) portion of your grade.

### Milestones

**Milestone 1: Selection of Option.** Select which of the options (a,c,or e) you will do and fill out the short form online. Write a short description of your initial idea for how you might implement it.

**Milestone 2: Initial draft of writeup, and git repo of your code with ≥ 3 non-trivial commits.** You must submit two items: an initial version of your writeup, and a git repository of your implementation containing at least three, non-trivial commits (e.g., commits affecting more than just whitespace or comments). Your writeup does not need to include results,
but it does need to include a discussion of your proposed system; a discussion of your
implementation (or expected implementation), including any hurdles you are currently encountering; a discussion of what data you are using (+ if and how you adpated it); and a discussion of what tests you are running or will run to ensure correctness.

You will turn in:
* an **ANONYMIZED** PDF of your writeup (name the file with your UMBC ID, e.g., "AB1234.pdf"),
* a git repo for your code. Your repo must be private, but please share it with the course staff. **Please do not list the repo on your writeup.**
Your anonymized PDF will be provided to other students to review/provide feedback on (see Milestone 3); your code will not be shared. You may optionally provide a written description of what, if
any, writing assistance you received (e.g., the GSA Writing Advisor).

**Milestone 3: Feedback on Discussion.** You will receive up to two other students’ initial writeups; you must provide feedback on the breadth, depth, and clarity of exposition. You may also provide suggestions on hurdles that are described in
the writeup(s). Reviewing forms and guides will be provided. To receive full credit for the reviews,
you must provide constructive and civil reviews (a guide will be provided).
This feedback will be “double-blind:” as a reviewer, you will not know whose writeups you are
reviewing, and as an author, you will not know who your reviewers are. This is why it is important for
the Milestone 1 drafts to be anonymized. All paper-reviewer identities will be known to course staff.

**Final Writeup and Full Code.** This must be a complete, well-written writeup.
You will turn in:
* a **NON-ANONYMIZED** PDF of the writeup,
* your code repo,
* a PDF document discussing the changes made, both as a result of the reviews/feedback and
along with any unprompted changes.
As with the initial submission, you may also provide a written description of what, if any, writing
assistance you received (e.g., the GSA Writing Advisor).



---

## Paper Track
(GA4) Write a literature review paper in which you select one of a set of topics, and (i) identify, (ii) analyze,and (iii) synthesize modern approaches for the topic you choose.

Here are some examples of literature review papers (also called survey papers) that have been published at conferences on more specific NLP topics. Your paper should be like these, although it doesn't have to be *quite* as thorough.
* [Neural Machine Translation for Low-resource Languages: A Survey](https://dl.acm.org/doi/pdf/10.1145/3567592)
* [Automatic Story Generation: Challenges and Attempts](https://arxiv.org/abs/2102.12634)


Select one of the following topics (see [Paper Topics](#paper-topics)), and (i) identify, (ii) analyze, and (iii) synthesize modern approaches for the topic you choose.

**Identify.** For this assignment you will need to find an appropriate number of papers to discuss in detail.
Though the final number that you select is highly dependent on, among other things, which topics you
choose, the length of the papers, and their venues, a reasonable number of papers is between five and
ten. This range does not constitute required minimums or maximums.
You may read many more papers than you discuss in detail. Do not view this as “wasted” effort—these
should help inform the overall narrative and context for your discussion.

**Analyze.** Ask and answer fundamental research questions: what were the goals of each of the papers? What
scientific and engineering questions did each of the tackle? How well did the evaluations support the
main claims? What was not done that could have been done?

**Synthesize.** How do the efforts relate to one another? Do they follow one after another, making (incremental) progress on a task (metric)? Does one question some basic assumptions of another, and if so, how do the other papers fit in? What are the limitations of these approaches, and what still remains to be
done? You can also link these papers and ideas to related fields.


#### Requirements 
Within the Paper Track, you will be primarly evaluated primarily on the completeness, thoroughness,
and clarity of your paper. Grammatical, logical, organizational, or factual errors will be negatively impact
the score. Weak or lacking analysis and synthesis will also be large negative influences on the score.

Papers should be four pages, not including references, in the ACL format. Paper must
use the [ACL style guide](https://github.com/acl-org/acl-style-files) (either LaTeX or Word is fine).
Be sure to cite appropriately and follow all academic honesty standards. You may include figures (your
own, reproductions, or copies of existing figures); be sure to provide appropriate credit for the figures.
However, make the figures count: do not include them simply to pad the paper. Do not consider just
“recent” papers; try to find papers from the past 25 years.

Some good places to find papers include 
* [*ACL](https://aclanthology.org/)
* [COLM](https://openreview.net/group?id=colmweb.org/COLM/2024/Conference#tab-accept)

Or if you're interested in speech:
* [Interspeech](https://www.isca-archive.org/index.html)
* [ICASSP](https://ieeexplore.ieee.org/xpl/conhome/1000002/all-proceedings)

You can also find papers using [Google Scholar](https://scholar.google.com/) if you know the right keywords.

### Milestones
**Milestone 1: Selection of Option, Topic, and Initial list of papers.** Decide on a topic and fill out the short form online.  It would also be beneficial if you find at least 5 papers related to your topic. If you list them in the form, I can give you feedback  regarding their relevance to your topic and their quality. This list is not your complete or final list of papers you’ll read or consult: it is meant as a starting point. You may also remove papers from this list when you actually write your paper.

**Milestone 2: Initial version of the paper.**  Despite it being “initial,” this must be a complete, well-written paper. Although this part is ungraded, the better this draft is, the more informative the feedback you'll get from your peers. 

You will turn in:
* an **ANONYMIZED** PDF of the paper (name the file with your UMBC ID, e.g., "AB1234.pdf"),
* the paper’s source (such that we could regenerate the PDF).
Your anonymized PDF will be provided to other students to review (see Milestone 3); your source
will not be shared. You may also provide a written description of what, if any, writing assistance you
received (e.g., the GSA Writing Advisor).

**Milestone 3: Paper Peer Review.** In this process, you will receive up to two other students’ papers; you must provide feedback on the breadth, depth, and clarity of exposition. Reviewing forms and guides will be provided. To receive full credit for the reviews, you must provide constructive and civil reviews (a guide will be provided). This review will be “double-blind:” as a reviewer, you will not know whose papers you are reviewing, and as an author, you will not know who your reviewers are. This is why it is important for the Milestone 1 papers to be anonymized. All paper-reviewer identities will be known to course staff.

**Final version of the paper.** This must be a complete, well-written paper.

You will turn in:
* a **NON-ANONYMIZED** PDF of the paper,
* a PDF document discussing the changes made, both as a result of the reviews/feedback and
along with any unprompted changes, and
* the paper’s source (such that we could regenerate the PDF).
As with the initial submission, you may also provide a written description of what, if any, writing
assistance you received (e.g., the GSA Writing Advisor).

### Paper Topics

Please select a topic from the ones listed below. With consultation of the instructor, you may propose your
own topic.

####  Hierarchical/Advanced Language Modeling
For this topic, you will examine advanced and/or hierarchical approaches to language modeling. 

#### Grounded Language Processing
For this topic, you will examine how non-language signals (e.g., image or audio features) can help NLP
tasks, how NLP tasks/models can improve understanding/analysis of those non-language signals, or both.

####  Structured Prediction for NLP
For this topic, you will examine structured prediction for a single task, or a significant, relevant aspect of
that task. Roughly, structured prediction is any task that given an input, produces some object or label
with an internal structure, such as a syntax tree or semantic frame.

####  Computational Methods for Linguistic Subfields
For this topic you will examine how computational/statistical models are developed to better explain (or
mimic) linguistic phenomena/subfields. For example, you could explore computational approaches to phonology, morphology, syntax, semantics, or pragmatics—or any combination, e.g., morphosyntax, syntactic-
semantic, phonology/morphology, typology, etc.

#### Natural Language Generation
For this topic you will examine methodological and/or evaluation approaches for generating natural language. Classic examples of natural language generation include machine translation and abstractive summarization. There’s an entire SIG (special interest group) on generation (SIGGEN) and a conference (INLG) devoted to it.

####  Ethical Issues and Bias in NLP
For this topic you will explore ethical concerns (and approaches for dealing with them) in NLP, and/or issues
of implicit/explicit bias in NLP models. You might want to check out the FAccT conference proceedings if you're interested in this topic.

####  NLP for [Insert Your Area Here]
For this topic you would survey how NLP can be used in an area of study of interest to you. For instance,
there are special interest groups (called SIGs) for NLP for the humanities, Semitic languages, and biomedical
applications—among many others. Look at the “SIGs” row at to bottom of the ACL Events table at [https://aclanthology.org/](https://aclanthology.org/).


#### Your Choice!
Unsatisfied with any of the above options? Then feel free to pick your own topic. The requirement is that
you must clear it with the instructor first and it must have a significant relevance to material covered in this
course.


### Resources

What types of sources that you should cite in your paper?


#### Resources you can use
* peer-reviewed conference papers
* peer-reviewed journal papers

#### Resources you are allowed to use but should limit the use of
* arXiv preprints
* peer-reviewed workshop papers
* technical reports (e.g., official reports posted by developers to explain their new model)


#### Resources you shouldn't use
* blog posts
* course materials from this class (such as slides)
* other online courses and their materials
* slides from tutorials or presentations for papers given at conferences
* textbooks
* any sort of article, writing, manuscript, or slides not covered by the previous list (unless specifically
approved in advance, in writing)





Assignment adapted from Dr. Frank Ferraro.
