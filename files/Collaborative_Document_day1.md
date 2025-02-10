![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2025-02-03-ds-cr Good Practices in Research Software Development - Day 1

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://edu.nl/r84aa

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
| 10:15 | Coffee break                             | 
| 10:30 | Introduction to version control with Git |
| 11:30 | Coffee break                             |
| 11:45 | Introduction to version control with Git | 
| 12:45 | Wrap-up                                  | 
| 13:00 | END                                      | 

Note: Today's session will be fundamental, feel free to skip it and come back tomorrow if you are comfortable with the following:

Day 1:
1. Automated Version Control
2. Setting Up Git
3. Creating a Repository
4. Tracking Changes
5. Exploring History
6. Ignoring Things
7. Remotes in GitHub

Day 2:
1. Collaborative Version Control - Centralized
2. Collaborative Version Control - Distributed
3. 
## :icecream: Icebreaker
Describe what you do in only three words.

| Name       | Your Three Words           |
| ---------- | -------------------------- |
| Ole        | monkey press button 🐵👇⌨️  | 
| Anneke     | Acquire run machine        |
| Eric       | Make PC crash :)           |
| Stefan     | trial and error            |
| Mark       | manage develop eWaterCycle |
| Farnaz     | Coding and coding          |
| Anne Floor | fixing analysis code       |
| Daniël     | coding bugfixing repeat    |
| Ana        | lasers and molecules       |
| Baran      | toxic language detection   |
| Chris      | Planets and python         |
| Anna       | plants satellites fortran  |
| Irina      | understand and connect     |
| Gonçalo    | Code, run, repeat          |

## 🔧 Exercises

## 🧠 Collaborative Notes

### Programming vs Software Engineering
- "Software engineering is programming integrated over time"
- Software engineering focuses on sustainability, avoiding "code debt"
    - This takes a bit longer in the beginning, but pays off in the future
    - Investments like version control, code reviews, testing, etc.
- Projects are getting exponentially more complex to manage the more people are involved
- When is the "investment" in best-practices worth it? Rule of thumb:
    
    | lifetime  | use                             |
    | --------- | ------------------------------- |
    | 1-shot    | 🚫                              |
    | week+     | git github                      |
    | 3 months+ | testing                         |
    | 6 months+ | documentation, automate testing |

    | users          | use                              |
    | -------------- | -------------------------------- |
    | 1              | push to main                     |
    | 2+             | branches, merging                |
    | 2+ (+students) | code review                      |
    | 2+ (+external) | release branch & everything else |

- Following best practices saves time in the long-run by
    - Efficiency
    - Reproducibility
    - Reusability
    - Faster debugging
    - Robustness
    - Fewer headaches!

### Version Control
- Documents are a collection of changes
- Collaboration means that there are independent changes (just like in this collaborative doc!) that can be merged
- Version Control tracks changes, gives you unlimited undo (yeah!), and enables work in parallel
- The Holy Realms of Git
    - workspace: your filesystem 📂
    - index: a.k.a. "staging area", files to be committed 🕓
    - local repository: contains branches, commits, history, etc. 🗂️
- Staging area can hold many files and folder
- What's a good commit message?
    - Short, descriptive, imperative
- Common commands
    - `git status` show the state of the repository, you will use this _all the time_
    - `git add` put files in the "index"/"staging area"
    - `git commit` saves the staged content as a new commit to the local repository
- Commit style
    - "atomic", a change (or a set of changes) that cover one specific aspect, like "fixed bug A", or "implement feature B"

### Saying hi to `git`

```
git --version
```

Should return something like:

```output
git version 2.39.3
git version 2.47.1.windows.2
```

### Configuring `git`

#### Mandatory Settings
These two settings are the only ones that are mandatory:

```bash
git config --global user.name "Sam Anonymous"
git config --global user.email "sam@example.com"
```

#### Optional settings

```bash
git config --global core.editor "nano"  # vim, emacs nano ...
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "subl -n -w"  # Sublime Text
```

Good practice:
```bash
git config --global init.defaultBranch main
```

Editing your config directly:
```bash
git config --global --edit
```

Listing your config:
```bash
git config --list
```

If you have global _and_ local settings, you get more info where which settings is defined with:
```bash
git config --list --show-origin
```

Getting help:
```bash
# general help
git --help

# Pattern for specific commands: git [COMMAND] --help
git config --help
git add --help
git commit --help
```

### Hands-On!
#### First Steps

```bash
mkdir planets  # create a directory for our exercise
cd planets  # "change directory" into the new planet folder
git init  # create a new local repository, this is a "hidden" .git folder
ls  # no output, since our .git folder is hidden
ls -la  # extra flags ("-l" list output, "-a" list 'all' (also hidden) files)
git switch -c main  # create a new "main" branch and switch to it
git status  # What's the current state?
```

#### Create Content
Use whichever editor you are comfortable with. For the examples I use `nano`.
```bash
nano mars.txt
```
Put in some text:
> Cold and dry, but overything is my favorite color.

```bash
ls  # shows our new file mars.txt
cat mars.txt  # cat 🐱 outputs the content of `mars.txt`
git status  # How are we doing until now?
```

Git tells us that we have an "untracked" file and suggests what we could do with it now. Thank you, git! :D

```bash
git add mars.txt  # add our new file to the "index"/"staging area"
git status  # What changed, now that we have a file in the staging area?
git commit -m "Start notes on Mars as base"  # Commit to local repository
git status  # What's the repository state after committing?
```

#### Getting an Overview
```bash
git log  # Shows commits and commit messages of the current branch
```
N.B.: The commit "hash" (a sort of fingerprint) is very long. If you need to use it somewhere in a command, copying the first few (6+) characters is sufficient.

#### Changes Upon Changes
```bash
nano mars.txt
```
Put in some more text
> The two moons may be a problem for Wolfman.

```bash
git status  # Use this after every change, it's very instructive
git diff  # Show the "diff"erence between the committed and changed file version
```

Syntax of diff output:
- A space " " at the beginning of a line means "no changes"
- A minus "**-**" at the beginning of a line means that this line is now **removed**
- A plus "**+**" at the beginning of a line means that this line is now **added**

```bash
git add mars.txt  # Add the new changes
git commit  # Without `-m "message"` it will open an editor
```
Put a commit message
> Add concerns about effect of Mars moons on Wolfman

and save the file.

```bash
git log  # Both commits are listed now :-)
```

Add some more content!
```bash
nano mars.txt
```
Put text
> But the mummy will appreciate the lack of humidity
```bash
git diff
git status
git add mars.txt
git diff  # Empty! Huh?
git diff --staged  # Changes between the changed file and staging area!
git log  # Getting an overview again
git log --oneline  # Same, but more compact
git commit -m "Discuss concerns about Mars' climate for Mummy"
git log  # Three commits now
```

:::info
💡
`git` only tracks files, not folders! Files within folders are fine, but empty folders are ignored. If you want to track an "empty" folder, you can put a hidden file inside, e.g. `.gitkeep` and track that one instead. Its parent folder is now tracked as part of the `.gitkeep` file.
:::

## 🗺️ Exploring `diff`
```bash
git diff mars.txt  # show only differences of the `mars.txt` file
git diff HEAD mars.txt  # show diff between HEAD (last commit) and local file
git diff HEAD~1 mars.txt  # show diff between _previous commit_ and local file

# copy a COMMIT_HASH from `git log` (first 6+ or so chars are sufficient), then:
git diff COMMIT_HASH mars.txt  # diff between local file and a specific commit
```
:::info
💡
The dot `.` is an indicator for the _current folder_.
`git add .` adds all files in the current folder. (N.B.: This is not recommended, since you could add files that you don't intend to.)
The `.` dot can also be used in `diff` commands to refer to the current folder.
:::

:::info
## Tangent: Exploring the Different Realms
Please do not follow these commands in your exercise folder, it might get confusing. :-)

- We create a file and make it have different content in all three Realms.
    - workspace (local file system)
    - index/staging area
    - local repository
- Then we `diff` betwee all of those to see how they differ. 
```bash
$ nvim file.txt

$ cat file.txt
I’m in the repo

$ git add file.txt

$ git commit -m "commit file to local repo"
[main (root-commit) 7d7e84d] commit file to local repo
 1 file changed, 1 insertion(+)
 create mode 100644 file.txt

$ nvim file.txt

$ cat file.txt
I’m in the "index"/"staging area"

$ git add file.txt

$ cat file.txt
I’m in the "index"/"staging area"

$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   file.txt

$ nvim file.txt

$ cat file.txt
I’m in the workspace (your filesystem)

$ git diff file.txt
───────────────────
modified: file.txt
───────────────────
@ file.txt:1 @
-I’m in the "index"/"staging area"
+I’m in the workspace (your filesystem)

$ git diff --staged
───────────────────
modified: file.txt
───────────────────
@ file.txt:1 @
-I’m in the repo
+I’m in the "index"/"staging area"

$ git diff HEAD
───────────────────
modified: file.txt
───────────────────
@ file.txt:1 @
-I’m in the repo
+I’m in the workspace (your filesystem)
```
:::

## ⏳ Time Travelling
```bash
nano mars.txt  # add a new line, or make any disposable change you like
git status  # Git tells us what we can do next, e.g. `add/rm` or `restore`
git restore mars.txt  # undo the changes you did above
git status  # all clean! :D
```

Alternative:
```bash
git restore -s COMMIT_HASH mars.txt # to get the changes from a specific commit
git restore mars.txt  # to get back the most recent content from the local repo
```

## 🙈 Ignoring Files
```bash
mkdir results  # create a `results` folder
touch a.csv b.csv c.csv results/a.out results/b.out  # create empty files
git status  # check what's up
vim .gitignore  # create and edit a (hidden) `.gitignore` file
```
Put the content here you want to be ignored.
> ```
> # any file that ends in .csv
> *.csv
> 
> # the whole content of the results/ folder
> results/
> ```

Save and quit the editor. Then tell git about the new rules:

```bash
git add .gitignore
git commit -m "Ignore csv files and results folder"
```

::: info
💡
The `.gitignore` file does not remove files you already added/committed!
:::

### 📝 Testing the Rules
```bash
git add a.csv  # not allowed, unless you `-f` force git
```

## Connecting to the Outside World
Create a new repository called "planets" on github.com, then copy the URL (make sure to copy the SSH address!) and come back to the terminal.
```bash
# git remote add ALIAS URL
git remote add origin git@github.com/YOUR_USERNAME/planets.git
```

::: info
💡
`origin` is the standard alias for a remote repository.
:::

```bash
git remote -v  # checking if the remote is indeed added

# pushing all your committed changes to the remote repo
git push  # Fails! Oh no! But git tells us how to proceed.
git push --set-upstream origin main  # we only need to do this the first time
```


## 🏋 Exercise: Committing Multiple Files

The staging area can hold changes from any number of files
that you want to commit as a single snapshot.

1. Add some text to `mars.txt` noting your decision to consider as a base
2. Create a new file `venus.txt` with your initial thoughts about Venus as a base for you and your friends
3. Add changes from both files to the staging area, and commit those changes.

### Solutions
1) nano mars.txt
2) Add the text in the file.
3) Save the file.
4) nano venus.txt
5) Add the text in the file.
6) git add mars.txt venus.txt
7) git commit -m "Added thoughts on Venus as a base and updated Mars file"


1.git add mars.txt
2.git add venus.txt
3.git commit -m "commit message"
or 1. + 2. -> git add .
or 1. + 2. -> git add *.txt

git add venus.txt mars.txt ; git commit -m "edited two files, venus.txt and mars.txt"
git log (check commit numbers)

change mars.txt
touch venus.txt and add some info
git add mars.txt venus.txt
git commit
```output
[main bcf13af] Added Venus as potential location for a base.
 2 files changed, 2 insertions(+)
 create mode 100644 venus.txt
```


git add mars.txt venus.txt
git commit -m 'message'

## 🏋 Exercise: Understanding Workflow and History

What is the output of the last command in

```bash
$ cd planets
$ echo "Venus is beautiful and full of love" > venus.txt
$ git add venus.txt
$ echo "Venus is too hot to be suitable as a base" >> venus.txt
$ git commit -m "Comment on Venus as an unsuitable base"
$ git restore venus.txt
$ cat venus.txt #this will print the contents of venus.txt to the screen
```

1. 
```output
Venus is too hot to be suitable as a base
```
2. 
```output
Venus is beautiful and full of love
```
3. 
```output
Venus is beautiful and full of love
Venus is too hot to be suitable as a base
```
4. 
```output
Error because you have changed venus.txt without committing the changes
```

### Solutions

Is it answer 1, 2, 3, or 4?

- 3
- solution B
- 2
- 2
- 2
- 1
- ...
- 2
- 2: Last change was not staged and therefore not committed.
- 2
- 2


## 📚 Homework (some additional exercises if you want to practice!)
### `bio` Repository

- Create a new Git repository on your computer called `bio`.
- Write a three-line biography for yourself in a file called `me.txt`,
commit your changes
- Modify one line, add a fourth line
- Display the differences
between its updated state and its original state.

### Recovering Older Versions of a File

Jennifer has made changes to the Python script that she has been working on for weeks, and the
modifications she made this morning "broke" the script and it no longer runs. She has spent
\~ 1hr trying to fix it, with no luck...

Luckily, she has been keeping track of her project's versions using Git! Which commands below will
let her recover the last committed version of her Python script called
`data_cruncher.py`?

1. `$ git restore`

2. `$ git restore data_cruncher.py`

3. `$ git restore -s HEAD~1 data_cruncher.py`

4. `$ git restore -s <unique ID of last commit> data_cruncher.py`

5. Both 2 and 4

### Reverting a Commit

Jennifer is collaborating with colleagues on her Python script.  She
realizes her last commit to the project's repository contained an error, and
wants to undo it.  Jennifer wants to undo correctly so everyone in the project's
repository gets the correct change. The command `git revert [erroneous commit ID]` will create a
new commit that reverses the erroneous commit.

The command `git revert` is
different from `git restore -s [commit ID]` because `git restore` returns the
files not yet committed within the local repository to a previous state, whereas `git revert`
reverses changes committed to the local and project repositories.

Below are the right steps and explanations for Jennifer to use `git revert`,
what is the missing command?

1. `________ # Look at the git history of the project to find the commit ID`

2. Copy the ID (the first few characters of the ID, e.g. 0b1d055).

3. `git revert [commit ID]`

4. Type in the new commit message.

5. Save and close

### Ignoring Nested Files

Given a directory structure that looks like:

```bash
results/data
results/plots
```

How would you ignore only `results/plots` and not `results/data`?

### Including Specific Files

How would you ignore all `.csv` files in your root directory except for
`final.csv`?
Hint: Find out what `!` (the exclamation point operator) does

### The Order of Rules

Given a `.gitignore` file with the following contents:

```bash
*.csv
!*.csv
```

What will be the result?


## 📢 Feedback 
### What went well?
- good explanation of commands
- love the collaborating document. Took a minute to figure it out, but it helps a lot real time.
- collaborating document is a good way to communicate and interact, also to look back at some commands in the future.
- Having all the commands in the collaborative document helps a lot
- Collab doc is nice, coding along is also nice
- Colab Doc is great, and the day was very easy to follow, great individualised help as well!
- nice colab doc and good solution with the breakout rooms to address individual questions. i think the online format is very beneficial for these kind of programming workshops
### What could be improved?
- I passed 3/4 of the git questions whether I could skip this day, so was adviced to come today, but in hindsight I think a 15 min recap by looking at this doc at the end of the day would have been fine --> We will review this! What concepts were unknow? Or you just needed a refresher?
    - Commands I would have to look up to use (please add anything else unknown if you wrote below and have things to add): some of the git config commands and git remote add origin \<ssh link\> 
- I agree with the above --> Same as above.
- The setup instructions were easy to miss, I found them last week, but the email could have a subject line that's more like 'DO THIS SETUP BEFORE THE COURSE' --> Good idea! We will make sure to highlight it next time.
- Installing from Windows power shell, doesn't really go well, probably because of admin rights or Windows settings. Better to install using direct download through graphical interface (like msi). In powershell, when you think your installing, nothing happens, so you wait for long time. With the MSI you see that it is installing right away. --> Thanks!! I have created [this](https://github.com/carpentries-incubator/collaborative-git-and-github-lesson/issues/44) issue. Would you like to get involved? :smile: -> Sure, I subscribed to the thread
- Maybe also give a link to some basic VIM commands or other editer which is used in the examples/showcases. People got stuck with opening/editing/saving the files and got a bit behind.--> Great idea! Added [this](https://github.com/carpentries-incubator/collaborative-git-and-github-lesson/issues/45) issue. 
::: info
__Basic Tutorial: How to Create, Edit, Save, and Exit a File Using Vim__

__Step 1__: Open or Create a File with Vim
Open your terminal.To create or open a file, type:
```vim filename.txt```
__Step 2__: Enter Insert Mode to Edit the File
When you open Vim, you start in Normal Mode (used for navigation and commands).
To start editing, press `i` to enter Insert Mode. You'll see `-- INSERT -- ` at the bottom of the screen. Now you can type and edit the file as needed.

__Step 3__: Save Your Changes
To save your changes, first exit Insert Mode by pressing     `Esc`. This returns you to Normal Mode.
Type `:w` and press `Enter`. This writes (saves) the file to disk. You'll see a message like `"filename.txt" [New] 1L, 10C ` written at the bottom.

__Step 4__: Exit Vim
After saving, you can exit Vim by typing `:q` and pressing `Enter`.
If you haven't saved your changes and try to quit, Vim will warn you. To force quit without saving, type `:q!`.

__Step 5__: Save and Exit in One Command
If you want to save and exit in one step:
Press `Esc` to ensure you're in Normal Mode.
Type `:wq` and press `Enter`. This saves the file and quits Vim.

:::

- it was not immediately clear to me how to use this CodiMD document, but perhaps I  missed the instruction... --> Good point, we could have explained it better.
- Tip: history > my_command_history.txt (so people can review what they typed during the day, would be great to also have the output of git bash, but than you have to start a log probably)

## 📚 Resources
- NL-RSE network: https://nl-rse.org
- _The_ git manual: https://git-scm.com/book/en/v2
- The "realms" of git explained visually: https://ndpsoftware.com/git-cheatsheet.html
- `.gitignore` rules overview: https://www.w3schools.com/git/git_ignore.asp
- More online `git` exercises: https://www.w3docs.com/exercise/git
- Setting up a SSH with GitHub: https://carpentries-incubator.github.io/collaborative-git-and-github-lesson/

## ❓ Questions?

- difference between git add and git stage?
    - `git add` adds files to the "index"/"staging area", `git commit` then commits one or more changes to the local repository
    - I did not know the `git stage` command, thanks for that question! ;-)
- So this is still local repo, not on Github yet, so like a copy?
  - Yes, correct! :-) The local repository is still on your own machine, with all changes recorded.
  - It's actually even more powerful than a copy, you can have multiple "branches" (we'll explain that later) at the same time and jump between them
- Commit and push are different actions, correct?
    - Yes, `git commit` commits to the local repository, whereas `git push` pushes the latest changes from your local repository to a remote repository, like GitHub
- Is local repository also on your local machine/ computer?
    - Yes it is. It is actually a hidden folder ".git" within your project folder. All commits, branches, etc. are stored within that folder.
- there are so many terminals, now just powershell?
    - Yes, there are a lot of different ones. They work mostly the same, so for this course it does not matter which one you choose..
- if global configuration was already set and you set it again, will it just be overwritten?
    - Yes, setting it _global_ again overwrites previous global info. Setting it _locally_ (without the `--global` flag) in a project folder will only override the settings in that folder/project.
- how to just view all global settings?
    - `git config --list`, or if you want to know what is defined where, then use
    - `git config --list --show-origin`
- When I typed git config --global --edit, I got this message: 
    ``` 
    E325: ATTENTION
    Found a swap file by the name "~/.gitconfig.swp"
              owned by: baranbarbarestani   dated: Mon Feb 03 10:09:38 2025
             file name: ~baranbarbarestani/.gitconfig
              modified: YES
             user name: baranbarbarestani   host name: iPad-van-Gwen
            process ID: 93297
    While opening file "/Users/baranbarbarestani/.gitconfig"
                 dated: Mon Feb 03 10:06:43 2025
    
    (1) Another program may be editing the same file.  If this is the case,
        be careful not to end up with two different instances of the same
        file when making changes.  Quit, or continue with caution.
    (2) An edit session for this file crashed.
        If this is the case, use ":recover" or "vim -r /Users/baranbarbarestani/.git
    config"
        to recover the changes (see ":help recovery").
        If you did this already, delete the swap file "/Users/baranbarbarestani/.git
    config.swp"
        to avoid this message.
    
    Swap file "~/.gitconfig.swp" already exists!
    [O]pen Read-Only, (E)dit anyway, (R)ecover, (D)elete it, (Q)uit, (A)bort: 
    ```
    - When you open a file with the `vim` editor, a "swap file" (in this case `~/.gitconfig.swp`) is created. This makes sure that no two processes/users can edit a file at the same time and create conflicts. Sometimes one of those "swap files" gets left behind by mistake. Two approaches to solve this:
        1. Make sure you don't edit the same file twice. Close duplicate editors, if necessary.
        2. If you are sure that you only edit the file _once_, then you have a left-over "swap file". Here's a the safe approach to solving your error message:
            - Make a copy of your config file
                - `cp ~/.gitconfig ~/.gitconfig.copy`
            - Open the config file again, this time choose (`R`)ecover and save it
                - `git config --global --edit`
            - Open the copy in another editor and compare both. Make sure that your original file is how you want it to be.
            - Close both editors
            - Now you can safely delete the swap file and the copy:
                - ```bash
                  rm ~/.gitconfig.swp
                  rm ~/.gitconfig.copy
                  ```
- When I do git diff it gives me diferent output than just one line added
    ```bash
    diff --git a/mars.txt b/mars.txt
    index d08b101..66599a2 100644
    --- a/mars.txt
    +++ b/mars.txt
    @@ -1 +1,2 @@
    -Cold and dry, but everything is my favourite colour
    \ No newline at end of file
    +Cold and dry, but everything is my favourite colour
    +The two moons may be a problem for Wolfman
    \ No newline at end of file
    ```
    - This depends on the editor you are using. Yours does not put a "newline" character at the end of the last line (a matter of choice, I guess). When you now add something at the end, the (previously) last line has now an extra character (the "newline") at the end. So this is more of an editor quirk than a git thing.
    - 
- As soon as you -f force a file, do you have to do that every time if you update it? or can you ignore just that specific file in some way?
    - You only have to force it once, then git knows you a serious about it. However, I would avoid `-f` here in general, since it's not very transparent anymore what's happening. I'd rather take it out of the `.gitignore` file instead.

- add on on previous: but can you do something like *.csv except whatever?
    - Yes, there are ways to be really specific about what to ignore and what not. Here's a more detailed overview of the `.gitignore` rules: https://www.w3schools.com/git/git_ignore.asp
    - Example to ignore a folder (and everything in it), but _do_ include a specific file inside it.
      ```bash
      # .gitignore content:
      results/
      !results/i_want_this_file_tracked.txt
      ```
- what is the difference between the echo xxx > option, and the echo xxx >> option (so the amount of > signs?)
    - `echo "abc" > file.txt` writes "abc" to the file `file.txt`, overwriting its content
    - `echo "def" >> file.txt` _appends_ "def" to the file `file.txt` _after all the existing content_.
    - Content of file.txt is now:
      ```bash
      $ cat file.txt
      abc
      def
      ```
- new question here