---
title: 'Mini Project 5: Feedback and Revision'
date: 2017-04-11 10:00:00 -04:00
description: 'Reflection and revision is an important part of the iterative feedback
  process. In this mini project, you will select one of your first four mini projects
  to revise/extend and resubmit.'
due: 2017-12-10 9:00:00 -05:00
survey_url: https://goo.gl/forms/NaFs9SKwSgbpDnQ32
---

## Introduction

Reflection and revision is an important part of the iterative feedback
process. In this mini project, you will select one of your first four mini
projects to revise/extend and resubmit.

The basis for the revision comes from several places:

1. For each of the mini projects (and toolboxes) in this class, you received detailed feedback comments from the NINJAs via email and / or GitHub pull requests.
2. You (hopefully) know much more Python now than when we started
3. There may be extensions or alternate directions you wanted to pursue but didn't have time

In addition to correcting any errors in the original submission, you should
make some technical improvement. This could take many forms, but examples
include:

* Re-writing an older mini project using an object-oriented style.
* Finding and improving performance bottlenecks. {% comment %}using [algorithm analysis\]
({% link _days/day-17.md %}) and/or [code profiling]({% link _days/day-19.md %}){% endcomment %}
* Pursuing one of the "Going Beyond" options.
* Taking a toolbox to the next level.
* Something else awesome.

{% if false %}
This exercise should not take as long as the other mini projects, and it is
[worth about half as much]({% link pages/policies.md %}).
{% else %}
This exercise should not take as long as the other mini projects. It is worth a bonus of half as much as the other mini projects.
{% endif %}

## How to proceed

### Choose what to work on

Select which mini project you would like to revise. You may individually
revise MP4. If you and your partner want to work together on MP4, you must
each make a significant contribution. Send us a proposal (see below) if you
choose this option.

In most cases, doing a "going beyond" on a toolbox you submitted can satisfy this assignment.
If you would like to do a toolbox that you did not do as part of your 5 required toolboxes,
send a note to the teaching team to explain why doing a new toolbox will serve you the best for MP5.

_[Optional]_ If you'd like some feedback on your proposed technical
improvement or help coming up with one, send a short (1-2 sentences is OK)
proposal to the instructor via Slack.

### Branch out

In this mini-project, we'll model a git workflow (one of many possible) in
which there is one stable release branch and all new development happens in
the master branch, just like we've been doing so far.

Create a new branch called `release` in your repository. You can do this
[directly on GitHub](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/),
or on the [command line](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging). This release
branch will point to your original mini project submission, and you will make
all the new revisions in the `master` branch.

### Get it done

Complete your revision and improvement and push your work to GitHub.

### Turn it in

Create a pull request from your master branch to your release branch. Submit
your work by [filling out this form]({{ page.survey_url }}) with the
URL of your pull request.
