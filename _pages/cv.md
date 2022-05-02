---
layout: archive
title: ""
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[CV_Zihao-Ding.pdf](https://Darkhunter9.github.io/files/CV_Zihao-Ding.pdf)

# <center>Education</center>
***
- **Ph.D in Materials Science and Engineering**

    Carnegie Mellon University, 2018-2022 (expected)

- **M.S. in Machine Learning**

    Carnegie Mellon University, 2020-2022 (expected)

- **M.S. in Materials Science and Engineering**

    Carnegie Mellon University, 2016-2018

- **B.S. in Materials Science and Engineering**

    Shanghai Jiaotong University, 2013-2017

<br/>

# <center>Skills</center>
***
* **Materials characterization**
  * SEM, TEM, EBSD, FIB, EDS, AFM, XRD, Nanoindentation etc.
  * Electrochemical test, organic coating, surface processing
* **Programming**
  * C/C++, Python, Fortran
  * Tensorflow/Pytorch, CUDA/OpenCL
  * High performance computing, MySQL
* **Simulation**
  * Ansys/COMSOL

<br/>

# <center>Research & Projects</center>
***
<ul>{% for post in site.projects reversed %}
    {%if post.cv %}
        {% include archive-single-content-cv.html %}
    {% endif %}
    {% endfor %}</ul>

<br/>

# <center>Work experience</center>
***
<ul>{% for post in site.work reversed %}
        {% include archive-single-content-cv.html %}
    {% endfor %}</ul>

<br/>

# <center>Publications</center>
***
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

<br/>

# <center>Talks</center>
***
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

<br/>

# <center>Teaching</center>
***
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

  <!-- add awards and service (peer review one paper) -->