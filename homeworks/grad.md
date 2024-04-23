---
layout: default
img: 
caption: 
img_link: 
title: Graduate Assignment (20% of grade)
active_tab: homework
release_date: 2024-03-03
due_date1: 2024-03-11 23:59:00EST
due_date2: 2024-04-24 23:59:00EST
due_date3: 2024-05-01 23:59:00EST
due_date_final: 2024-05-15 23:59:00EST
submission: https://classroom.google.com/u/3/w/NjUwNDE2MzEwMzQx/tc/NjUxNTgzMTgyODgy
---


<div class="alert alert-info">

Checkpoint 1 due: {{ page.due_date1 | date: "%A, %B %-d, %Y" }}<br>
Checkpoint 2 due: {{ page.due_date2 | date: "%A, %B %-d, %Y" }}<br>
Checkpoint 3 due: {{ page.due_date3 | date: "%A, %B %-d, %Y" }}<br>
Final submission due: {{ page.due_date_final | date: "%A, %B %-d, %Y" }}<br>
All due dates are {{ page.due_date1 | date: "%I:%M%p" }} ET.
<br><br>
Submission Link: <a href="{{page.submission}}">{{ page.submission }}</a><br><br>
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
| Checkpoint 1 | Selection of one of GA1-GA3 and initial list of resources | Selection of topic for GA4 and initial list of papers | Ungraded |
| Checkpoint 2 | Initial report discussing progress, hurdles, and other challenges; and git repo containing at least three non-trivial/starter commits | Complete first draft, including citations | Ungraded |
| Checkpoint 3 | Feedback/suggestions on 2 other students' initial reports | Peer review | 10 points |
| Final Submission | Completed code, full git repository, completed writeup, and document summarizing how the feedback was used | Completed final paper + summary-of-changes document | 40 points |
| Final grade | || = total / 50|


## Description
For the graduate assignment, choose ONE of the following
assessments: **GA1-GA4**. GA1-GA3 will require you to implement NLP algorithms. For GA4, you will write a 4-page conference-style literature review paper on a particular topic.
While each person is free to choose which of these four options they will complete, I encourage each person to strongly consider how
each may be able to further their career/degree goals and choose the assessment that maximizes progress
toward that goal. For example, someone writing a disseration (doctoral or masters) may wish to do the
literature review paper, since it could help form the basis of the related work chapter of a dissertation. On
the other hand, someone may wish to really dive deep into an aspect of NLP implementation.
The possible assessments are divided into an “Implementation Track,” and a “Paper Track”. Both tracks
consist of advanced topics that we may very lightly cover, or mention, in the course. However, we will not
spend significant time on any of them.

---

## Implementation Track
Pick one:<br>
(GA1) Using the Universal Dependencies corpora, implement and evaluate a neural arc-standard dependency parser. <br>
(GA2) Re-implement the “Character-Aware Neural Language Models” work of Kim et al. (2016). <br>
(GA3) Follow the tutorial ["A Tutorial on Hidden Markov Models and Selected Applications in Speech Recognition" (Rabiner, 1989)](https://ieeexplore.ieee.org/document/18626) to implement an HMM.


For any of these options, you must
1. implement the specific algorithm or system,
2. train it on the specified data,
3. evaluate it on the specified data,
4. create a written lab report/writeup that includes
  * a prose-based discussion of the algorithm;
  * a prose-based discussion of your implementation, including any hurdles you encountered (and
how you addressed them);
  * a discussion of what tests you ran to ensure correctness;
  * results on both dev/validation and test splits; and
  * a summary of the approach’s ability to do the task(s) you evaluated.
  
Be sure to cite appropriately and follow all academic honesty standards. Accounting for items like tables
and graphs, an appropriate target length of this writeup is anywhere from 1 to 3 pages (though that is not a
hard limit).
Within the Implementation Track, you will be primarly evaluated on the completeness and correctness
of your implementation. However, the thoroughness and clarity of the writeup will be a sizeable (but non-majority) portion of your grade.

### Milestones

**Milestone 1: Selection of Option.** Select which of the options (GA1-GA3) you will do and fill out the short form online.

**Milestone 2: Initial draft of writeup, and git repo of your code with ≥ 3 non-trivial commits.** You must submit two items: an initial version of your writeup, and a git repository of your implementation containing at least three, non-trivial commits (e.g., commits affecting more than just whitespace or comments). Your writeup does not need to include results,
but it does need to include a prose-based discussion of the algorithm; a prose-based discussion of your
implementation (or expected implementation), including any hurdles you are encountering; and a discussion of what tests you are running or will run to ensure correctness.You must turn in:
* an **ANONYMIZED** PDF of your writeup (name the file with your UMBC ID, e.g., "AB1234.pdf"),
* a git repo for your code.
Your anonymized PDF will be provided to other students to review/provide feedback on (see Milestone 3); your code will not be shared. You may optionally provide a written description of what, if
any, writing assistance you received (e.g., the GSA Writing Advisor).

**Milestone 3: Feedback on Discussion.** You will receive up to two other students’ initial writeups; you must provide feedback on the breadth, depth, and clarity of exposition. You may also provide suggestions on hurdles that are described in
the writeup(s). Reviewing forms and guides will be provided. To receive full credit for the reviews,
you must provide constructive and civil reviews (a guide will be provided).
This feedback will be “double-blind:” as a reviewer, you will not know whose writeups you are
reviewing, and as an author, you will not know who your reviewers are. This is why it is important for
the Milestone 1 drafts to be anonymized. All paper-reviewer identities will be known to course staff.

**Final Writeup and Full Code.** This must be a complete, well-written writeup.
You must turn in:
* a **NON-ANONYMIZED** PDF of the writeup,
* your code repo,
* a PDF document discussing the changes made, both as a result of the reviews/feedback and
along with any unprompted changes.
As with the initial submission, you may also provide a written description of what, if any, writing
assistance you received (e.g., the GSA Writing Advisor).

### Implementation Options
#### (GA1) Implement and evaluate a neural arc-standard dependency parser

The algorithm is described in either textbook, and you may follow the broad outline given by [Chen and Manning (2014)](https://aclanthology.org/D14-1082/), but note that you do not have to re-implement this work exactly. I strongly recommend that you run through the algorithm on paper, and really understand it, before you begin coding. Train and evaluate
your system twice: the first time on English-EWT, the other is another language from UD of your choice.
For this option, you may use existing layers in the toolkits Pytorch, Tensorflow, or Keras.

#### (GA2) Implement the Wall Street Journal/Penn Treebank perplexity results from [Kim et al. (2016)](https://aaai.org/papers/10362-character-aware-neural-language-models/)

To do this, you will need to get the data from the instructor.
In addition to re-creating the Penn treebank results, also evaluate this model on at least one non-English
language from the UD data. For this option, you may use existing layers in the toolkits Pytorch, Tensorflow,
or Keras.

#### (GA3) Create a Hidden Markov Model from [Rabiner (1989)](https://ieeexplore.ieee.org/document/18626)'s tutorial

1. Find a text dataset on HuggingFace. Make sure that it has a training/testing split (or make it yourself).
2. Turn the text into [ARPAbet phonemes](https://en.wikipedia.org/wiki/ARPABET) using the [CMUdict](http://www.speech.cs.cmu.edu/cgi-bin/cmudict)
3. Train an HMM from scratch following [Rabiner (1989)](https://ieeexplore.ieee.org/document/18626).
4. Use the forward algorithm to calculate the likelihood of the sequences in the testing data.


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

### Milestones
**Milestone 1: Selection of Option, Topic, and Initial list of papers.** Decide on a topic and fill out the short form online.
 It would also be beneficial if you find at least 5 papers related to your topic. If you list them in the form, I can give you feedback
 regarding their relevance to your topic and their quality.
This list should not be your complete or final list
of papers you’ll read or consult: it is meant as a starting point. You may also remove papers from this
list when you actually write your paper.

**Milestone 2: Initial version of the paper.**  Despite it
being “initial,” this must be a complete, well-written paper. Although this submission will not
solely comprise your grade, it should be a paper that you would find acceptable for determining your
grade for the course’s paper component. To receive full credit, your paper must be a legitimate and
full response to the prompt. You must turn in:
* an **ANONYMIZED** PDF of the paper (name the file with your UMBC ID, e.g., "AB1234.pdf"),
* the paper’s source (such that we could regenerate the PDF).
Your anonymized PDF will be provided to other students to review (see Milestone 3); your source
will not be shared. You may also provide a written description of what, if any, writing assistance you
received (e.g., the GSA Writing Advisor).

**Milestone 3: Paper Peer Review.** In this process, you will
receive up to two other students’ papers; you must provide feedback on the breadth, depth, and clarity
of exposition. Reviewing forms and guides will be provided. To receive full credit for the reviews,
you must provide constructive and civil reviews (a guide will be provided).
This review will be “double-blind:” as a reviewer, you will not know whose papers you are reviewing,
and as an author, you will not know who your reviewers are. This is why it is important for the
Milestone 1 papers to be anonymized. All paper-reviewer identities will be known to course staff.

**Final version of the paper.** This must be a complete, well-written paper.
You must turn in:
* a **NON-ANONYMIZED** PDF of the paper,
* a PDF document discussing the changes made, both as a result of the reviews/feedback and
along with any unprompted changes, and
* the paper’s source (such that we could regenerate the PDF).
As with the initial submission, you may also provide a written description of what, if any, writing
assistance you received (e.g., the GSA Writing Advisor).

### Paper Topics

Please select a topic from the three listed below. With consultation of the instructors, you may propose your
own, separate topic.

####  Hierarchical/Advanced Language Modeling
For this topic, you will examine advanced and/or hierarchical approaches to language modeling. Examples
include (modified) Kneser-Ney smoothing [[Chen and Goodman (1999)](https://www.sciencedirect.com/science/article/pii/S0885230899901286)], syntactic and/or semantic language
models [[Chelba and Jelinek (1998)](https://aclanthology.org/P98-1035/)], topic models [[Blei et al. (2003)](https://www.jmlr.org/papers/volume3/blei03a/blei03a.pdf); [Teh et al. (2006)](https://www.jstor.org/stable/27639773)], hierarchical
Bayesian language models [[MacKay and Peto (1995)](https://www.semanticscholar.org/paper/A-hierarchical-Dirichlet-language-model-MacKay-Peto/01fa57bd91f731522c861404d29e4604ba6ac6d3); [Teh (2006)](https://aclanthology.org/P06-1124/)] , and neural language models.

#### Grounded Language Processing
For this topic, you will examine how non-language signals (e.g., image or audio features) can help NLP
tasks, how NLP tasks/models can improve understanding/analysis of those non-language signals, or both.
For example, the task of (sequential) image captioning or video summarization involves producing natural
language output that describes what is happening in those input images or videos. Visual question answering
(and its variants) requires systems to answer questions about an image with a sunny sky in the background,
answer the question “does it look like it’s going to rain?” Meanwhile, tasks involving conversational and
dialogue agents (e.g., Google Now, or Alexa) may need to take in spoken language input and perform some
action (including generating “spoken” language output) based on it.

####  Structured Prediction for NLP
For this topic, you will examine structured prediction for a single task, or a significant, relevant aspect of
that task. Roughly, structured prediction is any task that given an input, produces some object or label
with an internal structure. This is in contrast to prediction tasks that simply predict a single, “flat” label,
without any decomposable or introspective structure. We’ve already briefly talked about two instances of
structured prediction—machine translation/alignment and part of speech tagging—and we’ll see more as we
get further along in the semester. Canonical examples of structured prediction problems include, but are not
limited to: (a) syntactic parsing (constituency or dependency); (b) machine translation; (c) semantic parsing
(including FrameNet, PropBank, AMR, and VerbNet parsing); (d) structured information extraction (such
as template-based slot filling as in the ACE Relation Extraction task); (e) ontology induction; and (f) entity
coreference or cross-document entity linking. Generally, “bags-of-items” models do not arise in structured
prediction tasks. Tasks like question answering, recognizing/determining textual entailment, and sentiment
analysis may or may not involve structured prediction. Your paper is not restricted to the preceding items;
they are offered as suggestions.

####  Computational Methods for Linguistic Subfields
For this topic you will examine how computational/statistical models are developed to better explain (or
mimic) linguistic phenomena/subfields. For example, you could explore computational approaches to phonology, morphology, syntax, semantics, or pragmatics—or any combination, e.g., morphosyntax, syntactic-
semantic, phonology/morphology, typology, etc. (Try searching the [ACL Anthology](https://aclanthology.org/) for those terms.)

#### Natural Language Generation

For this topic you will examine methodological and/or evaluation approaches for generating natural language. Classic examples of natural language generation include machine translation and abstractive summarization. There’s an entire SIG on generation (SIGGEN) and conference (INLG) devoted to it.

####  Ethical Issues and Bias in NLP
For this topic you will explore ethical concerns (and approaches for dealing with them) in NLP, and/or issues
of implicit/explicit bias in NLP models. For example, this briefly appeared in some of the associations
identified by Church and Hanks (1989). More recently you may have heard about how for a while Google
Translate would always translate the Turkish sentence “o bir doktor” using the masculine pronoun “he”
even though that Turkish sentence is gender neutral (this particular case has now been addressed). There
are workshops on Ethics and gender bias in NLP. There is also a more general growing community called
FAT/ML (Fairness, Accountability, and Transparency in Machine Learning). You can look through the
associated proceedings (but make sure there’s an NLP component).

####  NLP for [Insert Your Area Here]
For this topic you would survey how NLP can be used in an area of study of interest to you. For instance,
there are special interest groups (called SIGs) for NLP for the humanities, Semitic languages, and biomedical
applications—among many others. Look at the “SIGs” row in the main table at [https://aclweb.org/anthology/](https://aclweb.org/anthology/).
Although sentiment analysis often asks for a single label at the end, the internal classification may operate over structures. That
is, the final flat label may be the result of some internal, latent structured prediction.
[Workshops](https://aclweb.org/anthology/venues/ws/) also often offer targeted application and interest areas, for example in the legal domain, patents, economics, and others!

#### Your Choice!
Unsatisfied with any of the above options? Then feel free to pick your own topic. The requirement is that
you must clear it with the instructor first and it must have a significant relevance to material covered in this
course.

---

## Resources
### Allowed Resources
The only reference materials you may peruse, read, skim, look at, use, or otherwise consult are:
* published textbooks (online versions or drafts are acceptable)
* peer-reviewed papers
* arXiv preprints
* slides from tutorials or presentations for papers given at conferences
* course materials from this class (such as slides, lecture discussion, and Discord notes and discussion)
* the official documentation of community-standard libraries, like numpy, SciPy, sklearn, PyTorch, and
HuggingFace

### Disallowed Resources
You are **not** allowed to peruse, read, skim, look at, use, or otherwise consult any of the following:
* blog posts
* any sort of article, writing, manuscript, or slides not covered by the previous list (unless specifically
approved in advance, in writing)
* code or pseudo-code available online from existing implementations
* other online courses and their materials


<div class="alert alert-danger">
The use of any of these disallowed resources will be considered a serious academic integrity violation and will result in,
at a minimum, an automatic 0 on this entire assignment (i.e., a 0 will be recorded for 20% of your entire
course grade).
</div>


Assignment adapted from Dr. Frank Ferraro.
