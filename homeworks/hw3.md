---
layout: default
img: beautiful-art.webp
caption: Beautiful Art
img_link: https://www.reddit.com/r/comics/comments/184eqmy/beautiful_art_oc/
title: Prompting Engineering and Ethics
type: Homework
number: 3
active_tab: homework
release_date: 2026-04-21
due_date: 2026-05-05 23:59:00EST
submission: https://blackboard.umbc.edu/ultra/courses/_96481_1/outline/assessment/test/_8407416_1?courseId=_96481_1&gradeitemView=details
online_submission: https://blackboard.umbc.edu/ultra/courses/_98413_1/outline/assessment/test/_8528735_1?courseId=_98413_1&gradeitemView=details
materials:
  -
    name: Prompting Notebook
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
Submission Link (in-person section): <a href="{{page.submission}}">{{ page.submission }}</a><br>
Submission Link (online section): <a href="{{page.online_submission}}">{{ page.online_submission }}</a><br><br>
Please be sure to double check the academic integrity and generative AI policies <a href="https://laramartin.net/NLP-class/#academic-integrity">listed on the syllabus</a>.
</div>

<div class="alert alert-warning">
I have set the notebook to use Mistral-7b-instruct, but feel free to use another model. Just be sure to specify what model you're using and use the same model for all questions of the homework.
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
* Determine when smaller LLMs like Mistral/Llama-2/etc. would be worth using
* Consider the ethical implications of using an LLM

## Part 1: Prompting

### Helpful Resources

* Original paper on few-shot prompting: [Language Models are Few-Shot Learners](https://papers.neurips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)
* Chain-of-thought prompting: [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://papers.neurips.cc/paper_files/paper/2022/hash/9d5609613524ecf4f15af0f7b31abca4-Abstract-Conference.html)
* Prompting slides: [26-04-09_prompting.pdf](https://laramartin.net/NLP-class/slides/26-04-09_prompting.pdf)

#### Other ways of prompting
* [Prompt-and-Rerank: A Method for Zero-Shot and Few-Shot Arbitrary Textual Style Transfer with Small Language Models](https://aclanthology.org/2022.emnlp-main.141/)
* [Cutting Down on Prompts and Parameters: Simple Few-Shot Learning with Language Models](https://aclanthology.org/2022.findings-acl.222/)

### What to do

<div class="alert alert-danger" markdown="1">
IMPORTANT! Before you start, please note that the number of tokens that are outputted is automatically printed out after the model is done generating. Please write down this number for every time you run the model <b>even if you don't report that prompt for this homework</b>. You will need the sum of these for Part 2.
</div>

Start with [this notebook](https://colab.research.google.com/drive/1rOsK21yRRye4vljiMhSOq_SN_m19JKw3?usp=sharing) and change the prompts of the model to answer the questions below. This notebook also has the data.
Any time we ask for a prompt, please be sure to keep all the cells in the notebook with your prompt text. Copy the output from the model into the document where you answer the questions below. (This will keep the output in case the notebook is accidentally rerun.) The number of suggested prompts are **minimums**.



<div class="alert alert-info" markdown="1">
All of the questions will be in relation to the following task.
For a given set of steps from WikiHow, you will be predicting the title of the article. That is, generating a title and comparing it with the original title.<br><br>
You will be using various prompting techniques to get the large language model (LLM) to do the title prediction.<br><br>
Select one article from the dataset provided in the notebook to use as the data you're evaluating on for all of the questions below.
</div>


1. (2 points for explaining why your evaluation metric is reasonable) You will need some objective evaluation metrics to determine how well your prompting is doing. You will be using two objective evaluation metrics throughout this homework. Take the time now to implement both in your code.
	a. The for the first one, you will use BLEU. BLEU is common evaluation metric used in NLP created to evaluate how accurate machine translation (the computational translation of one human language to another) systems were. You can call BLEU using this library: [https://www.nltk.org/api/nltk.translate.bleu_score.html](https://www.nltk.org/api/nltk.translate.bleu_score.html)
	b. For the second evaluation metric, you will pick your own. If you find a method that wasn't mentioned in the class slides, please cite your source!
2. First, try the generation task using zero-shot prompting in the plainest way possible. Just ask the model to do the task. Don't give any examples for how to do it, don't use any fancy prompting techniques. Just ask it like you're asking a human to do the task. We will refer to this as your **baseline**.<br />
	a. (2 pts) Provide 2 prompts.
	b. (2 pts) Run your 2 implemented objective evaluation metrics and report your scores.
3. In class, we talked about [providing a "role" to the model as part of the instructions](slides/24-04-24_Prompting.pdf#page=18). <br />
	a. (2 pts) Provide 2 prompts trying this out.<br />
	b. (2 pts) How does this compare to the output from the baseline? **Use both objective measures from question 1 and also use your intuition for a more "subjective measure".**
4. What happens when you use few-shot prompting? <br />
	a. (4 pts) Provide 4 prompts trying out different numbers of examples (i.e., different "n-shot" prompts).<br />
	b. (2 pts) How does changing the number of examples affect performance? Use your objective measure and your subjective measure.<br />
	c. (1 pt) Is there a cut-off where it isn't helpful to have more examples?
5. Consider [chain-of-thought prompting](https://papers.neurips.cc/paper_files/paper/2022/hash/9d5609613524ecf4f15af0f7b31abca4-Abstract-Conference.html), where you get the model to "show its work" to produce better results.<br />
	a. (2 pts) Provide 2 prompts trying chain-of-thought prompting.<br />
	b. (2 pts) How does this compare to your baseline? Use your objective measures and your subjective measure.
6. Try two other techniques that we talked about [in class](https://laramartin.net/NLP-class/slides/26-04-09_prompting.pdf).
	a. (2 pts) Provide both of those prompts.<br />
	b. (2 pts) How do these compare to your baseline? Use your objective measures and your subjective measure.
7. These models are not considered "state of the art", but they could still have their uses. Recall some of the tasks you looked into in HW1.<br />
	a. (3 pts) What types of NLP tasks do you think the model you chose would be good at? Why?<br />
	b. (3 pts) What would it be bad at? Why?<br />
	c. (2 pts) Was the model you chose good at this task? Why do you think that?
8. (2 pts) What types of "everyday" tasks (e.g., doing taxes, writing code) would the model you chose be good at? Why?

#### Extra credit
* Play around with different sampling strategies. [Use this guide for implementing them using Hugging Face.](https://huggingface.co/docs/transformers/generation_strategies) Pick one of the prompts that you used above and keep it the same as you change to different ways of sampling. Try 3 different ways of sampling.<br />
 a. (1 pt) What are the different ways you tried?<br />
 b. (3 pts, 1 pt each) How does it affect the generation?
 

## Part 2: Ethics
Although you are using a smaller model than some state-of-the-art models and you're using a quantized (condensed) version of it, there can still be some ethical ramifications. In this part, you will be considering some of these.

1. (2 points) Using [this calculator](https://energy.inference.net/), approximate how much energy you used for this homework. Select the model you used (or the closest relative to the model you used) and enter in how many tokens the prompts generated **across all of the prompts you used whether or not you reported them in the homework**. If you called the model, that adds to your total.<br>
Under "Environmental Impact", select the "Grid Region" of "United States (Average)". Report your total Carbon Emissions.<br>
The average household in the US generates 0.345 kg CO2 from electricity in *a year*. Compare this number to the number you calculated.
2. (2 points) Were there any toxic generations to any of the prompts you provided for Part 1? Discuss them if so. If not, why do you think you didn't see any?
3. (2 points) Considering how the model did across your prompts, do you believe that it was trained on WikiHow data? Why or why not?
4. (2 points) Regardless of your answer to the previous question, let's say the model was trained on WikiHow data. How might you mitigate the impact?

## What to turn in
* The code that you used for evaluation
* A document with the answers to your questions, all of your prompts, and the output from the prompts

# Grading
<div class="alert alert-warning" markdown="1">
Part 1: Prompting
* Question 1 -  2 points
* Question 2 -  4 points
* Question 3 -  4 points
* Question 4 -  7 points
* Question 5 -  4 points
* Question 6 -  4 points
* Question 7 -  8 points
* Question 8 -  2 points
* Extra Credit -  4 points

Part 2: Ethics
* Question 1 - 2 points
* Question 2 - 2 points
* Question 3 - 2 points
* Question 4 - 2 points
</div>
