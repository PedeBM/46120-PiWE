# PiWE Week 8: Final project introduction

Welcome to the final project phase of this course!

 * Slides: In this subfolder  
 * Recording: on Learn

## Overview

In the remaining part of PiWE, you will work on a final project in your group. 
You will develop a Python package for a wind energy related application with 
tests and documentation. 

Your individual final grade will be determined as a cumulative evaluation of 
your contributions to the final project and an individual written quiz.

**Due time of the final project**: 23:59 on Monday, May 4th, 2026.

### Pre-defined final projects
We provide three pre-defined final projects for you to choose, but you may also
submit a request for a different project if your group have an idea you would
like to pursue.

The three pre-defined final projects are as follows:

1. [**Wind resource assessment based on reanalysis data**](
   wind_resource_assessment/README.md)
2. [**Wind turbine modeling based on Blade Element Momentum (BEM) theory**](
   wind_turbine_modeling/README.md)
3. [**Wind power forecasting using machine learning**](
   wind_power_forecasting/README.md)

Introductions and details on these projects can be found in the respective 
sub-folders.

### How to develop the final project
You may notice that the final project is much more open than the CodeCamp
project, which essentially only lists the requirements, while all the design
and implementation details are left for you to decide. This is not by accident, 
as **the only way to actually learn how to develop tools/packages to solve 
realistic engineering problems is to actually do it from scratch by yourselves**.

You should also note that this course focuses on the programming aspect, not on
the actual models or physics. Thus, while you need to understand the background
to an extend that you can understand the procedure to fullfil the requirements, 
you don't need to be an expert in wind resource assessment, BEM theory and machine
learning/forecasting to be able to do the final projects. Thus, we will not
lecture about the models or physics during the class, but you are more than 
welcome to ask the instructors and TAs if you have any related questions.

Remember that
**the evaluation of the final project focuses more on the structure and quality of the code, not on the performance of your developed model/tool**. Thus, for example, for the machine learning models you developed for wind power forecasting, the accuracy of your model will not be judged.

We have a quite tight schedule before the deadline that you have to deliver the
package of your final project. You better discuss within your group and come up
with a plan quickly. 

To help your planning, below is a suggested development plan that you should 
consider:
* **Week 8 and 9**: Understand the project (background, requirements and necessary
steps/models/equations), explore the provided data (load, parse, and visualize),
and consider the preliminary design of the architecture of your package.

* **Week 10**: Implement and refine different parts of the package (including
tests).

* **Week 11**: Present your architecture and preliminary results in class, 
finalize the architecture and polish the code (including tests).

* **Week 12**: Refine the documentation, experiment on different computers (
   install the package, run the main script, check the test coverage, pylint
   score), fix all potential issues.

**Note that the notes provided in this repo can be quite relevant and important
for some tasks in the final projects: [notes_and_tips](../notes_and_tips).**

## Formal Requirements to pass
1. Your final project should have the structure and required files as shown in 
the following diagram:
   ```
   [your_final_project]
   ├── inputs/
   │   ├── data_files_we_provide
   │   └── data_files_you_found (optional)
   ├── outputs/
   │   └── data_files_you_generate (no need to push to Github)
   ├── src/
   │   └── your_python_package_codes
   ├── tests/
   │   └── python_scripts_you_write_for_tests
   ├── examples/
   │   ├── main.py (will run in evaluation)
   │   └── other_example_scripts_you_write (optional)
   ├── .gitignore
   ├── LICENSE
   ├── Collaboration.md
   ├── README.md
   ├── pyproject.toml
   └── any_other_files_you_may_want (optional)
   ```
2. Your Python package inside the `src` folder should include at least one 
class (we will cover class and object oriented programming in week 9).

3. Your Python package should implement the required functions, either as 
listed in **functional requirements** in the pre-defined projects, or as we 
agreed on and documented if you work on a custom project.

4. The README file should contains:
   * A brief overview of the package objective.  
   * Installation instructions.  
   * A description of the package architecture, with at least one diagram. 
   * A description of the class(es) you have implemented in your package, with
     clear reference to the file name of the code inside `src`.
   * A description of what peer review (if any) you have implemented.

5. We should be able to install your package successfully following the 
**Installation instruction** in your `README.md`.

6. Your `main.py` script inside the `examples` folder should demonstrate, in a
clear and structured manner, how the required functions are called and 
executed. Here you can copy the listed functional requirements, put them into
comments, and organize your code accordingly.

7. Your `main.py` script should run successfully and generate the expected 
results (like plots) in a reasonable time (less than 10 mins). If needed,
define a "demo" mode and/or use saved intermediate results.

8. Test coverage on your package should be higher than 80%, as evaluated using
`pytest-cov` on your `src` folder, i.e., by running:
   ```
   pytest --cov=src tests/
   ```

9. pylint score on your package should be higher than 8.0, as evaluated using
`pylint` on your `src` folder, i.e., by running:
   ```
   pylint src/
   ```

Note that each predefined project will have a list of functional requirements
too.

## Assessment Rubric
A detailed document explaining how your final project will be evaluated, 
similar like the one we used for the CodeCamp project, can be found in this
folder.


## Homework due next week

### PART 0: Sign up for a final project team (ASAP)

* Find a team of 2 to 3 people.  
* The deadline for signing up for a final project team is 23:59 Sunday, March 29. 
* How to sign up: check DTU Learn for the instructions.


### PART 1: Explore one of the pre-defined projects

* Discuss with your group, choose one pre-defined project to explore.
* Write a function to load, parse and plot the provided dataset in `inputs`, 
generate at least one figure. Ideally also with test in `tests`.
* Think about the structure/architecture of your package.

**Note**: the project you choose in this homework doesn't mean you have to 
stick to that project. Your group can make decision later on which project to 
work on. If you have a better project idea that your group want to pursue, 
first check the section on **Custom project**, and then come talk to us. 

But remember to **make a decision early**, so that your group has enough time 
to work on it.



## Custom project

If your group or youself choose to work on a custom project differs from the
three pre-defined ones, please note:

1. Your project should be somehow related to wind and energy systems.

2. The complexity of the project should be comparable to the pre-defined
ones.

3. You should be able to find relevant dataset by yourself, which preferably 
should be openly accessible.  

4. The size of your dataset, at lease for those needed to run your
`examples/main.py`, should not be too big, like less than 100 MB.

5. You will need to draft a general description and a list of **Functional
 requirements** for your custom project, similar to the README files in the
 pre-defined projects.

6. To get approval for your custom project idea, you need to send an email to
Ju Feng before midnight on Wednesday, April 8, including a document explaining 
the above points.  


## Solo teams

This class focuses on collaborative code development, so working in a team is 
the default. However, in some cases, we may grant exceptions for people working 
in solo teams. E.g., students working on research projects who have a 
particular use for their code.

To petition to work as a solo team, send an email Jenni by midnight on Tuesday, March 24, that explains your reason for working solo. Decisions on your petition 
will be made soon.

If your petition is denied, you will be required to work in a team, so 
procrastination is not advised. NOTE: If granted permission to work solo, you 
are still expected to use feature branches and PRs.