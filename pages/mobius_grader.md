---
title: Möbius Grader
---
# Möbius Grader

Möbius Grader is an open-source web-app for automated grading of parametric modelling assignments 
using [Möbius Modeller](mobius_modeller.html). 

The Möbius Grader is used for grading assignments for the 
[Edx Spatial Computational Thinking Professional Certificate Programme](mobius_moocs.html). 

{% include fig.html 
file="mobius_grader.png" 
caption="Möbius Evolve Grader integrated into teh Edx Generative Modelling MOOC." 
%}

## Grading Process

Möbius Grader automates the grading process of parametric modelling assignments in cloud, on the
Amazon Web Services (AWS) platform.

Let's imagine that you are required to create a script that generates a box consisting
of six polygon faces, with variable height, width and length. For this description, we will still
think of this as a single function. So the grader will have both your submitted script and the
answer script.

* `submitted_box_func(length, width, height)`
* `answer_box_func(length, width, height)`

The grader will then run a series of tests with predefine values for length, width, and height. Both
submitted and answer scripts will be executed, generating a series of 3D models.

* `box_result1 = submitted_box_func(1, 2, 3)`
* `box_result2 = submitted_box_func(2, 1, -1)`
* `box_answer1 = answer_box_func(1, 2, 3)`
* `box_answer2 = answer_box_func(2, 1, -1)`

The grader will then compare the result 3D models to the answer 3D models. When comparing models,
the grader will look at each entity in the answer model and see if it can find a matching entity in
the result model. So in this case, the answer models will have 6 polygons. So for each of these
polygons, the grader will look for a matching polygon in the result model. A match means that the
polygon must have the same shape and topology, and must have the same position and orientation. (The
matching process will be discussed in more detail later.)

So let's say that you made an error in your script, and that the results are as follows:

* For *box_result1*, the grader found 5 out of 6 matching polygons.
* For *box_result2*, the grader found 2 out of 6 matching polygons.

Your final grade would be the average of the two results:

* grade = (5/6 + 2/6) / 2 = 58%

# Source Code

Source code is available on Github.

- Lead Developer (2018 - ongoing): Tung Do Phuong Bui
- [Möbius Grader on Github](https://github.com/design-automation/mobius-external-grader){:target="blank"}
- [Möbius Grader Edx Server on Github](https://github.com/design-automation/edx-server){:target="blank"}

## Paper

{% include ref-conf.html
    authors="Pung, D|Bui, TDP|Janssen, P"
    year="2020"
    date="August 5-6"
    place="Bangkok, Thailand"
    pages="323-332"
    title="Automated Grading of Parametric Modelling Assignments - A Spatial Computational Thinking Course"
    proceedings="Proceedings of CAADRIA 2020"
    cumincad_id="caadria2020_048"
    researchgate_id="355338440"
%}



