---
title: "Introduction"
teaching: 15
exercises: 0
questions:
- "What is programming?"
- "What is Python?"
- "When might Python be useful to a librarian?"
objectives:
- "EIL5 programming"
- "Familiarity with "
- "Understand the benefits of writing a Python script to replace a manual task"
keypoints:
- "Programming is the designing and writing of instructions for telling a computer what you want it to do"
- "Programming can be useful to repeat tasks regularly"
- "Programs are a great way to share processes with others"
- "Python is a general purpose programming language"
---
## Programming - an overview

FIX ME: Add content

## The Python language in a nutshell

FIX ME: Add content

## A simple use case example

Monty has been tasked with comparing two sets of IDs for articles written by 
an academic at his institution. One set comes from her University's institutional
repository, and the other comes from holdings on a commercial article database.

His supervisor, Pip, wants to check which of the articles held locally have been added
to the commercial database and which have not. Pip has provided him with an excel spreadsheet with
the IDs from each source as two columns of data.

Monty has been advised he'll have to do this regularly, and because he knows some Python,
he decides to write a short script that will perform this task for him without
any manual checking.

He writes the following script in a plain text file and saves it as compare-ids.py:

~~~
def compare_ids():
    with open('local.txt') as local_f:
            local = set(local_f.readlines())
    with open('remote.txt') as remote_f:
        remote = set(remote_f.readlines())
    result = list(local - remote)
    with open('result.txt', 'w') as f:
        f.writelines(result)
    print("There are {} IDs in the institutional repository that aren't in the commercial database".format(len(result)))
    print("See result.txt for list of IDs")
~~~

Monty saves the two rows of IDs in the Excel into two text files, local.txt and remote.txt.

He then opens a terminal window and navigates to the directory he saved the text files, and
types `python3 compare-ids.py`.

The script runs and tells Monty there were 27 IDs missing from the commercial database. A new 
text file has also been created listing the IDs miising from the commercial database.
