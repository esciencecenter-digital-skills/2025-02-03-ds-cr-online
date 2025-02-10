![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2025-02-03-ds-cr Good Practices in Research Software Development - Day 2

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://edu.nl/ca6g7

Collaborative Document day 1: https://edu.nl/r84aa

Collaborative Document day 2: https://edu.nl/ca6g7

Collaborative Document day 3: https://edu.nl/epqkf

Collaborative Document day 4: https://edu.nl/4ynkp

##  🫱🏽‍🫲🏻 Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## 🎓 Certificate of attendance

If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl.
Please request your certificate within 8 months after the workshop, as we will delete all personal identifyable information after this period.

## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, raise your hand in zoom. Click on the icon labeled "Reactions" in the toolbar on the bottom center of your screen,
then click the button 'Raise Hand ✋'. For urgent questions, just unmute and speak up!

You can also ask questions or type 'I need help' in the chat window and helpers will try to help you.
Please note it is not necessary to monitor the chat - the helpers will make sure that relevant questions are addressed in a plenary way.
(By the way, off-topic questions will still be answered in the chat)


## 🖥 Workshop website

[link](https://esciencecenter-digital-skills.github.io/2025-02-03-ds-cr-online/)

🛠 Setup

Day 1 and 2: [link](https://carpentries-incubator.github.io/collaborative-git-and-github-lesson/)

Day 3 and 4: [link](https://esciencecenter-digital-skills.github.io/good-practices-lesson/#software-setup)

## 👩‍🏫👩‍💻🎓 Instructors

Olga Lyashevska, Francesco Nattino

## 🧑‍🙋 Helpers

Ole Mussmann, Claire Donnelly  

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city


## 🗓️ Agenda
|  Time | Topic                                    | 
| -----:|:---------------------------------------- | 
|  9:00 | Welcome and icebreaker                   |
|  9:15 | Collaboration with Git and GitHub |
| 10:15 | Coffee break                             | 
| 10:30 | Collaboration with Git and GitHub |
| 11:30 | Coffee break                             | 
| 11:45 | Collaboration with Git and GitHub  |
| 12:45 | Wrap-up                                  | 
| 13:00 | END                                      | 

## ❄️ Icebreaker
Imagine you are on a deserted island, pick three emojis to describe what you would bring with you.

Useful website: https://emojidb.org/



## 🔧 Exercises

#### Exercise: Working as a project collaborator (in pairs):
- PERSON A: Create an issue in the repository
- PERSON B: Clone this repository to your system
- PERSON B: Create a new branch
- PERSON B: Make the changes requested in the issue
- PERSON B: Push the changes to the remote repository on GitHub
- PERSON B: Submit a Pull Request, refer to the issue (e.g. "Closes #1")
- PERSON A: Review the Pull Request
- PERSON B: Address the comments
- PERSON A: Approve the Pull Request
- PERSON B: Merge the Pull Request

### Extra exercise if you are done with the above.
#### Exercise: Working as an external contributor (in pairs)

- PERSON A: Create an issue in Person B's repository
- PERSON A: Fork the repository to their own (= Person A's) account
- PERSON A: Clone the repository, make changes, push them back to the fork
- PERSON A: Submit a Pull Request from the fork to the original repository
- PERSON B: Make a change in the original repository in the same place as person A's proposed changes
- PERSON A: Solve the merge conflict in the Pull Request
- PERSON B: Review/Approve the Pull Request
- PERSON B: merge the Pull Request
 
## 🧠 Collaborative Notes

### Collaborating on code with Github

#### Workflow for this section:
- Create a new repository (or use the one that you made yesterday)
    - Make sure it has a unique name (e.g. python-sum)
    - Add README & .gitignore files
    - Choose a licence: Apache 2.0
- Go to your new repository and add a new collaborator
    - Go to the settings tab and click on collaborators on the left hand side
    - Add collaborator and type in the name of the person you want to add
    - The person can then accept the invite

- Creating an issue: 
    - In the issues tab, create a new issue.
    - This is a way to track things that you want to implement or fix in your project.
    - In issues, you can link to people (e.g. @username), PRs (e.g. #1) and links etc. You can also assign people to take care of an issue. 

- Clone the repo you are collaborating on:
    - Copy SSH link: `git clone [ssh-link]`
    - Create a new branch: `git switch -c 1-add-python-sum`
    - Make the change you want to make: `vim sum-two-numbers.py` (or use the editor you prefer), add the code and save the file. 
    - Commit and push your changes to GH
    - This will open a pull request on GH.

- Creating a pull request:
    - After pushing your changes, the option to create a pull request (PR) automatically appears in GH.
    - You can add a title and description of the changes the pull request addresses:
        - Best practice is to list what the PR addresses and which issue(s) it addresses (you can link issues with e.g #1)
    - Choose a reviewer for the PR

- Code review:
    - When you open the pull request you can open the "files changes" to look at the files that have changed
    - You can leave comments on specific parts of the code (hover over the bit of code and click +)
    - When you "start a review" the comments are in draft mode until you click "finish your review".
    - Leave a general comment and either: 
        - "Approve" - branch can be merged, 
        - "Comment" - just leaving comments, the person can choose what the want to do 
        - "Request changes" -  changes should be made before merging
    
- Addressing comments: 
    - `git pull`
    - Make sure you are on the correct branch then make your changes. 
    - Commit and push your changes. 
    - Respond to the comments on the PR
        - Say you addressed them, or how you did or if there were any problems with the suggestion. 
    - Re-request a review

- Suggesting a change: 
    - In GH, click + where you want to add your suggestion. This will open a comment, on the top bar (on the right or preview) you can click on "add a suggestion" and you can adjust the code. 
    - Your collaborator can then accept the suggestion and commit it within GH without needing to pull. 

Once everyone is happy, you can merge the PR into main! 

- Creating a fork:
    - A fork is cloning a repository serverside (in this case GH). You can then make changes and commit them to your own fork without affecting the original project.
    - You do this when you want to make changes to a project that you do not have write access to. This is often the case with big projects (e.g. [Pandas](https://github.com/pandas-dev/pandas), [Xarray](https://github.com/pydata/xarray) etc), but smaller ones too. 
    - If you make a change that you want to contribute to the original project, you can make a pull request from your fork. 

#### General notes:
- Choosing a licence is important, as in principle if you do not choose one no one is allowed to use your code. [Apache licence 2.0](https://choosealicense.com/licenses/apache-2.0/) is a permissive open source licence.
- If someone does not use GitHub, you can still invite them by using their e-mail address: it will send an invite to join GitHub.
- To accept an invite, you can either do it through the notifications in GH or through email. (You can also go directly to the repository and accept there.)
- When creating a new branch, you can name it what you want but try to be descriptive of what the branch will do. If using issues, you can add the number of the issue.
- When you create a new local branch to work on, it is not seen by GH. So when pushing your local branch to GH for the first time you will be prompted to create this branch on GH too (set upstream branch). 
    - `git push -u origin [branch]` 

#### Linking a pull request to an issue
To link a pull request to an issue to show that a fix is in progress and to automatically close the issue when someone merges the pull request, type one of the following keywords followed by a reference to the issue. For example, Closes #10 or Fixes octo-org/octo-repo#100.

close
closes
closed
fix
fixes
fixed
resolve
resolves
resolved

## 📚 Resources
- Choosing a licence: https://choosealicense.com/licenses/
- Tracking issues: https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues
- Using keywords in GH: https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/using-keywords-in-issues-and-pull-requests
- Code reviews: https://dev.to/akdevcraft/how-to-review-code-2gam
- Git guide: https://github.com/git-guides
- git cheatsheet: https://education.github.com/git-cheat-sheet-education.pdf
- forking: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks
- Resolving merge conflicts in GitHub: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github
- Resolving merge conflicts in the command line: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line
- Duplicating repository: https://docs.github.com/en/repositories/creating-and-managing-repositories/duplicating-a-repository


## ❓Questions
- to create a branch I am used to command checkout -b <branchname> instead of git switch -c <branchname>. Is there a difference?
    - Answer: switch is now used in favour of checkout but both commands do the same thing. git checkout is more versatile and can be used for more than switching branches. 
- is it also possible to create a Pull Request in git commandline? Would be handy
    - Answer: Technically yes, but GH offers a lot of features that make it nicer for reviewing code. If you want to try it though, you can do this with [git CLI](https://medium.com/@ravipatel.it/creating-a-git-pull-request-using-the-command-line-a-detailed-guide-4ef1ea017fe2).
- when does it make sense to merge the working branch with main in the local directory?
    - Answer: Is it better practice to merge the working branch with main on the remote, i.e. via a Pull Request! So you can have other people reviewing your work..
- In our project at work, we now have a lot of branches. Is it good habit to delete old branches? Local and remote I mean?
    - Answer: Yes, you can indeed remove old branches. Note that you don't loose the list of commits when you remove a branch, just the 'reference' to them with the branch name.
- Is there a way to visualize the history of branches, commits etc? Something to quickly see in a visual way the workflow for that repository.
    - Answer: In the repository: Insights -> Network
- You always git add after making an edit in a vim file? isn't the file already on your Git, why would you always do this? 
    - Answer: When you do `git add` you are adding the changes to the "staging area" before committing. This allows you to choose which changes you want to include in a particular commit (keeping your commit history clearer.)
        - https://github.com/git-guides/git-add
- One general question. When you pull from the remote repository, is this always from the branch that we have 'switched' to locally? What I mean is, if I am working in a branch, while someone else works in another branch: as long as we both "stay on our own branches", there is no risk of interference?
    
- is it good practice to pull into the main branch on the local repo?
    - Answer: `git pull` will update your local work branch with commits from the remote, and update all remote tracking branches. https://github.com/git-guides/git-pull. 
    
- is this "safely remove branch" part like archiving it? so it is still there, as you can restore it, but it isn't there visually when you're working on it? 
    - Answer: You can restore the branch but the PR will be closed. 

- if I delete a branch on the remote repo, is it automatically deleted locally?
    - Answer: No, local and remote branches are separate so only the remote branch (the GH one) will be deleted. 
    
- We were doing the exersice (it worked :D) but we also noticed that the branch that we "safely deleted" as a last step, that the branch is still there locally after pulling/pushing. Is there a way to also locally get rid of this, like archive/delete or anything? 
    - Answer: To delete locally you can do: 
    `git branch -d <branch_name>`
    This will only delete the branch if it has been merged (so a littler safer). 
    To force a delete: 
    `git branch -D <branch_name>`
    
    If your branch hasn't been deleted remotely then you can fetch the remote branch and rebuild the local one. 

- What is the difference between --bare and --mirror really when copying a repository rather than forking it. 
    - Answer: The difference is mostly that --mirror includes all references, whereas --bare excludes some. I think this stackoverflow answer might be helpful: https://stackoverflow.com/questions/3959924/whats-the-difference-between-git-clone-mirror-and-git-clone-bare/3960063#3960063
    
- I noticed that when working in git bash for example and you do git status, even if github is changed, it can say "it is up to date", as it refers to the local repository. Is there a way to check if you are up to date with that repository without pulling immediately. 
    - Answer:
        - `git ls-remote <origin>` will list the last commit hashes in the remote
        - `git fetch --dry-run` will show what would be pulled, if anything.
    
    
    
## Feedback 

    
### What did we do well
    
- the breakout rooms workes really wel! maybe mention before that sharing screens to each other is an option. And maaaaybe 1 extra person (sometimes a bit rushed) but everything was answered very well. 
- lots of one-on-one help from trainers in the breakout room
- I think I got the general ideas, but I am for sure going to forget again where some of the buttons are in Github. 😅
- Really liked the interaction between collaborators
- Thanks for adding resources to the CD; I'll have a look at them.
- I find very useful the explanations on when each thing is typically used (for example why branches are useful and how to best use their advantages). The main thing I learned today is not so much the commands, but how to use them and good practices in collaborating with others. 
- Nice hands on excercises in break out rooms
- Loved the excercises, they're useful to practice the wrokflow.
- i really like the flow of this course, so "schouderklopje" (don't know an english translation)    
- good and clear instructions in the exercises
- this collaborative document is so fun to watch 
    
### What can we improve
    
- Add an extra exercise, in conflicts would be nice, for those groups that finish the other exercises early. The exercise on conflict could also be done individually, since everyone has their own speed. Great idea, we have created [this](https://github.com/carpentries-incubator/collaborative-git-and-github-lesson/issues/49) issue. Please consider contributing!
- add some more advanced stuff as an extra for people that know git --> Same as above!
- provide flow of code --> We will improve on this!
- goal/use case of forking (why exactly doing it) True, need to provide a motivation. For now, please check resources section.
- i do love/need the merge-conflicts information. so maybe make it a part or at least an optional add on? like the exersice was quite good to work with if it has a little more documentation/explanation Great! See [this](https://github.com/carpentries-incubator/collaborative-git-and-github-lesson/issues/49) issue. Please consider contributing!
- Would like a lesson about the fork part but I understand the balance between the time in exercises and lessons --> We'll spend more time for it next time and/or provide more background info as part of the more advanced exercise. 
- The intro on forking was a bit fast for me. --> True, we will give a quick demo next time.
- Maybe add some documentation about managing conflicts. Even if you don´t go through it explicitly, it would be nice to have it as a resource. --> Thanks, we added it now. 
- Maybe some more homework, I notice that you just have to play around a bit, but also need another account to manage the back and forth interaction. --> When a new exercise on solving conflicts is added, this could also work as homework for participants not able to finish it during the class
- Maybe again a little bit more in detail what the day will be about at the start for people with some experience to help decide whether the topics are new enough to attend the day? --> Good point, we'll start with a quick summary in the next days