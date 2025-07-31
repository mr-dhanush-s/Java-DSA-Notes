# Git and GitHub

### Def:
Git and GitHub is used to maintain the history of the project at which time, which user name the change where in the project and when.

Some of the alternatives of Github are  
- Git Lab
- Git Bucket

Git is the version control system where other developers can contribute for our project all over the world.


### Repository
It is folder


history --> commits
red part --- this part of code was deleted
green part --> this part of code was added


## How to download Git
[link](https://git-scm.com)
don't download the GUI istead downlad CLI for windows.

# Basic commands:

### Commit Commands
- ```ls```
- ```mkdir \<folder-name>```
- ```ls -a```
    - \- a is used to see the hiden file
- ```cd \<folder-name>```
    - change directory

In our project folder the ==.git== file created.
- ```git init```
- ```ls -a```
    - ==.git== folder it constains
        - HEAD, descriptioin, info, config, hooks, objects

- ```touch \<file-name.extions>```
    - it is used to create the file


- ```rm -rf \<file-name>```
    - it is used to remove the file.

- ```git status```

some file there and git says it is not tracked.

it is not private adn know one knows about the created file.

we can create it easily

Untracked files
    - the file is not added to the git repository

tracked files
    - the file is added added to the git repository
- ```git add \<file-name>```
- ```git status```
    - changes to be commited

- ```git commit -m "names.txt file is added"```
    - \-m provide a message

- ```vim names.text```
    - A text editor used to edit data inside the file

- ```cat names.txt```
    - it used to display what is inside the file on the terminal

- ```git status```
    - modified names.txt

- ```git add .```
- ```git status```
    - modified names.txt

- ```git restore --staged names.txt```
    - Used to get the previous stage/state of file.

- ```git log```
    - Used to see the history.





### How to recover the deleted file

- ```git recover <particular-commit-hash-value>```

    - 3 commit
    - 2 commit \<here the file deleted>
    - 1 commit

Copy the hash of previous commit and use it in the restore command
The commits are works based on the stack Where the commits are made build on top of the previous commit

If we need to bring the file and make it wait on back of the stage.
- ```git stash```
![](Images/Screenshot%20(11).png)

Hey people from back stage come back to the stage area.
- ```git stash pop```
![](Images/Screenshot%20(13).png)

Your photo is not taken (back stage people) to the back stage people go away from the stage
- ```git stash clear```
![](Images/Screenshot%20(14).png)



### How to share our project to github

- create a new project(repository)
- to connect the local folder to the git hub repo.
    - ```git remote add orgin \<url-of-particular-repo>```

    - ```git remote -v```
    - ```git push orgin main```
        - pushing(sending) file from local to the main branch of the github repo
![](Images/Screenshot%20(16).png)



## Branching:
New branch is created and used when there is new feature, debug, etc.. happening in the project.

Don't commit to the main branch because it the standard or stable for the users those who are using the project.

`git branch feature(branch-name)`  
used to create the new branch called feature.

`git checkout feature(branch-name)`  

Used to point the head to the feature branch(Now all the commit are affected on the feature branch)

![](Images/Screenshot%20(17).png)

we can to add or move the commit from other branch to main branch

The flow of main will go seperately and working(dev) on other branches are also parallely going

- we can merge the \<other-branch> to the main branch where the user can access it.

![](Images/Screenshot%20(18).png)

`git checkout C5(commit-name)`
The head pointing to the commit-5

![](Images/Screenshot%20(19).png)


`git push orgin master`
To push the commits from local to the github repo

![](Images/Screenshot%20(20).png)

![](Images/Screenshot%20(21).png)


### How to work with the open source projects

like commclassroom(how to contribute)

go to `fork` make a copy of commclassroom to our account

`git clone <url>`
- to download the particular repo to our local folder

upstream url --> where we have forked it from the original project.

orgin url --> forked url in our orgin

`git remote add upstream <upstream-url>`

`git remote -v`  
orgin is ours  
upstream is where we forked it

### what is pull request 
Create our own code sample and then we can ask them to put in their project, teh person will receive the pull request form us.


One branch has only one pull request(ours to project person)


How to fetch the commits of upstream  
fetched all the changes


step-1
`git fetch --all --prune`

\-- all --> all the commits
\-- prune --> they can fetch deleted also
![](Images/Screenshot%20(23).png)

step-2
`git reset --hard upstream/main`

![](Images/Screenshot%20(24).png)

this is not updated in fork we need to push from the local folder  

`git push orgin main`
