# PiWE Week 7: Linters and Packaging

## Overall objectives

1. Restructure your CodeCamp project such that you define and use an installable Python package.  
1. Update your code so it adheres to stylistic conventions.


## Homework due next week

This is the last week that you will work in your CodeCamp teams.

We recommend you work on the two PRs in series, not in parallel.
I.e., finish Part 2A before starting 2B.

### Part 1: As a team, in class

Read through this page and make a plan of attack for who does which parts.

### Part 2: Individually and/or with your team

#### Part A: Restructure project to use a package

1. Check out into a feature branch.
1. Copy the `pyproject.toml` from this week's folder into your repo. 
1. Decide what to change in `pyproject.toml`, then update it to reflect your project.
1. Move files/folders around so that your repo structure matches the file structure indicated in the slides.
   * I.e., package in `src/`, code in `scripts/` and tests in `tests/`.
1. Create and activate a fresh environment called `codecamp` with Python verison 3.11.
1. Install your package per the instructions in the slides.
1. Run `code_week3.py`, `code_week4.py`, and `main.py` and make sure they work.
   * NB: You might need to update filepaths after the restructure.
   * DO NOT use `sys.path.append` if your codecamp imports are not working.
     If something went wrong, double-check your `pyproject.toml`, your installation process, and ask instructors for help.
1. Make sure the tests still pass.  
   * NB: Filepaths and working directory in tests can be tricky.
     Be sure to ask for help in office hours, Slack, etc., if you get stuck.
   * Don't use `sys.path.append` here, either.
1. Make a PR with your changes. Have another team member review/approve/merge.  

#### Part B: Clean up code style

1. Check out into a feature branch.
1. Enable the pylint and flake8 extensions in VS Code.  
1. Install pylint if you don't have it. In Anaconda Prompt, `pip install pylint`.  
1. Run pylint on codecamp: `pylint src/`. What is your score?  
1. Make changes to your code so your score is above 7 (ideally higher).
1. Make a PR with your changes. Have another team member review/approve/merge.  

### Optional: Form a final project team

Teams for final project should be formed before March 29 at 23:59.
See instructions in slides.
Project descriptions from last year are [here](https://github.com/DTUWind-46120-2025/46120-PiWE/tree/main/week08_final_project_intro).

## Extra credit

* Also update the code in `scripts` to have a pylint score of 7 or higher.
* Name your package `<team>-codecamp` and try to upload it to PyPI per the instructions
  in the slide deck. Can you successfully install it from PyPI without having to
  clone first?