---
layout: default-2024
title: CMSC 473/673 - Schedule
active_tab: lectures
---


<!-- Create a HTML anchor for the most recent lecture -->
{% assign anchor_created = false %}
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
<!-- End create a HTML anchor for the most recent lecture -->



<div class="alert alert-info">
The lecture schedule will be updated as the term progresses.
</div>

<table class="table table-striped">
  <thead>
    <tr>
      <th>Date</th> 
      <th>Lecture Topic</th>
      <th>Readings for this Lesson</th>
      <th>Homework Due</th>
    </tr>
  </thead>
  <tbody>
    {% for lecture in site.data.2024.lectures %}
	    <!-- Create a HTML anchor for the most recent lecture -->
	    {% capture lecture_date %}{{lecture.date | date: '%s'}}{% endcapture %}
	    {% assign lecture_date = lecture_date | plus: 0 %}
	    {% assign now = now | minus: 14400 %}

	    <tr
	    {% if lecture.type %}
	      {% if lecture.type == 'deadline' %}
		class="warning"
    	      {% elsif lecture.type == 'tutorial' %}
		class="tutorial"
	      {% elsif lecture.type == 'no_lecture' %}
		class="danger"
	      {% endif %}
	    {% endif %}
	    >

	    <!-- End create a HTML anchor for the most recent lecture -->
	      <td width="19%">{{ lecture.date | date: '%a, %b %-d, %Y' }}</td>
	      <td width="20%">
		 {{ lecture.title }}<br>
		 {% if lecture.type != 'no_lecture' and lecture.title %}
			{% if lecture.slides %}
			  <a href="{{ lecture.slides }}">[slides]</a>
			{% endif %}

			{% if lecture.video %}
			  <a href="{{ lecture.video }}">[video] </a>
			{% endif %}

			{% if lecture.guest_speaker %}
			  {% if lecture.guest_url %}
			    by <a href="{{ lecture.guest_url }}">{{ lecture.guest_speaker }}</a> 
			  {% else %} 
			  by {{ lecture.guest_speaker }}
			  {% endif %}
			{% endif %}
		      	{% if lecture.guest_speaker2 %}
		      	  and
			  {% if lecture.guest_url2 %}
			    <a href="{{ lecture.guest_url2 }}">{{ lecture.guest_speaker2 }}</a> 
			  {% else %} 
			    {{ lecture.guest_speaker2 }}
			  {% endif %}
			{% endif %}
		{% endif %}
	      </td>
	      <td>
		{% if lecture.required %} 
		<ul>
		  {% for reading in lecture.required %}
		    <li>
		    {% if reading.url %}
			{{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a> 
		      <br />
		    {% else %}
		       {{ reading.authors }}, {{ reading.title }} 
		      <br />
		    {% endif %}
		    </li>
		  {% endfor %}
		</ul>
		{% endif %}
	      </td>    
	      <td>
		{% if lecture.homework_due %} 
		  {% for hw in lecture.homework_due %}
		    {% if hw.url %}{% if hw.url contains '://' %}<a href="{{hw.url}}">{% else %}<a href="homeworks/{{hw.url}}">{% endif %}{{hw.title}}</a><br>
		    {% else %}{{hw.title}} 
		    {% endif %}
		    {% if hw.note %}<i>{{hw.note}}</i>{% endif %}
		  {% endfor %}
		{% endif %}
	      </td>
	    </tr>
    {% endfor %}
    
  </tbody>
</table>

