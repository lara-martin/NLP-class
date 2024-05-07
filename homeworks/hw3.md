---
layout: default
img: beautiful-art.webp
caption: Beautiful Art
img_link: https://www.reddit.com/r/comics/comments/184eqmy/beautiful_art_oc/
title: Prompting Engineering
type: Homework
number: 3
active_tab: homework
release_date: 2024-04-24
due_date: 2024-05-06 23:59:00EST
submission: https://classroom.google.com/c/NjUwNDE2MzEwMzQx/a/Njc2MTc5MzM5MDM1/details
materials:
  -
    name: LLAMA-2 Prompting Notebook
    url: https://colab.research.google.com/drive/1rOsK21yRRye4vljiMhSOq_SN_m19JKw3?usp=sharing

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
Submission Link: <a href="{{page.submission}}">{{ page.submission }}</a><br><br>
Please be sure to double check the academic integrity and generative AI policies <a href="https://laramartin.net/NLP-class/#academic-integrity">listed on the syllabus</a>.
</div>

{% if page.materials %}
<div class="alert alert-info">
Materials for this assignment:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}


{{page.type}} {{page.number}}: {{page.title}}
=============================================================

## Learning Objectives
* Recall how to evaluate generated output
* Identify what prompting techniques produce better output
* Determine when LLMs like Llama-2 would be worth using

## Helpful Resources

* Original paper on few-shot prompting: [Language Models are Few-Shot Learners](https://papers.neurips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)
* Chain-of-thought prompting: [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://papers.neurips.cc/paper_files/paper/2022/hash/9d5609613524ecf4f15af0f7b31abca4-Abstract-Conference.html)

### Other ways of prompting
* [Prompt-and-Rerank: A Method for Zero-Shot and Few-Shot Arbitrary Textual Style Transfer with Small Language Models](https://aclanthology.org/2022.emnlp-main.141/)
* [Cutting Down on Prompts and Parameters: Simple Few-Shot Learning with Language Models](https://aclanthology.org/2022.findings-acl.222/)

## What to do

Start with [this notebook](https://colab.research.google.com/drive/1rOsK21yRRye4vljiMhSOq_SN_m19JKw3?usp=sharing) and change the prompts of the model to answer the questions below. This notebook also has the data.
Any time we ask for a prompt, please be sure to keep all the cells in the notebook with your prompt text. Copy the output from the model into the document where you answer the questions below. (This will keep the output in case the notebook is accidentally rerun.) The number of suggested prompts are **minimums**.

The task you will do is called the [Story Cloze Test](https://aclanthology.org/W17-0906/). In cloze tests, a segment of text is removed and the person taking the test is asked to fill in the blank. In the Story Cloze Test, the ending to the 5-sentence story is missing and the model has to figure out which sentence (out of 2 options) is the better choice. Examples of the task can be found here: [https://cs.rochester.edu/nlp/rocstories/](https://cs.rochester.edu/nlp/rocstories/)


<div class="alert alert-info" markdown="1">
All of the questions will be in relation to the Story Cloze Test.
You you be doing a variation of this task where you will be giving the model the first 4 sentences of the story, generating the last sentence, and comparing it with the "right" ending.<br><br>
You will be using various prompting techniques to get the large language model (LLM) Llama-2 to do the story completion.<br><br>
Select one story from the dataset to use as the story you're evaluating on for all of the questions below.
</div>

1. (4 points, 2 points per evaluation) Provide 2 different ways you might objectively evaluate the output that the model generates. **Pick one** of these methods and use it for the rest of the questions to compare the outputs. If you find a method that wasn't mentioned in the class slides, please cite your source!
2. (2 points) First, try the generation task using zero-shot prompting in the plainest way possible. Just ask the model to do the task. Don't give any examples for how to do it, don't use any fancy prompting techniques. Just ask it like you're asking a human to do the task. We will refer to this as your **baseline**.<br />
	a. Provide 2 prompts.
3. In class, we talked about [providing a "role" to the model as part of the instructions](slides/24-04-24_Prompting.pdf#page=18). <br />
	a. (2 pts) Provide 2 prompts trying this out.<br />
	b. (2 pts) How does this compare to the output from the baseline? **Use your objective measure from question 1 and also use your intuition for a more "subjective measure".**
4. What happens when you use examples (i.e., few-shot prompting -- passing some examples of the how to do the task in addition to the instructions)? <br />
	a. (4 pts) Provide 4 prompts trying out different numbers of examples.<br />
	b. (2 pts) How does changing the number of examples affect performance? Use your objective measure and your subjective measure.<br />
	c. (1 pt) Is there a cut-off where it isn't helpful to have more examples?
5. Consider [chain-of-thought prompting](https://papers.neurips.cc/paper_files/paper/2022/hash/9d5609613524ecf4f15af0f7b31abca4-Abstract-Conference.html), where you get the model to "show its work" to produce better results.<br />
	a. (2 pts) Provide 2 prompts trying chain-of-thought prompting.<br />
	b. (2 pts) How does this compare to your baseline? Use your objective measure and your subjective measure.
6. Llama-2 is not considered "state of the art", but it could still have its uses. Recall some of the tasks you looked into in HW1.<br />
	a. (3 pts) What types of NLP tasks do you think Llama-2 would be good at? Why?<br />
	b. (3 pts) What would it be bad at? Why?<br />
	c. (2 pts) Was Llama-2 good at this task? Why do you think that?
7. (2 pts) What types of "everyday" tasks (e.g., doing taxes, writing code) would Llama-2 be good at? Why?

### Extra credit
* Play around with different sampling strategies. [Use this guide for implementing them using Hugging Face.](https://huggingface.co/docs/transformers/generation_strategies) Pick one of the prompts that you used above and keep it the same as you change to different ways of sampling. Try 3 different ways of sampling.<br />
 a. (1 pt) What are the different ways you tried?<br />
 b. (6 pts, 2 pts each) How does it affect the generation?

## What to turn in
* The ipynb file with all of your prompts and the code that you used for evaluation
* A pdf with the answers to your questions and the output from the prompts

# Grading
<div class="alert alert-warning" markdown="1">
* Question 1 -  4 points
* Question 2 -  2 points
* Question 3 -  4 points
* Question 4 -  7 points
* Question 5 -  4 points
* Question 6 -  8 points
* Question 7 -  2 points
* Extra Credit -  7 points
</div>
