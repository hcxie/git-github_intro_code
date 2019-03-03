<!-- MDTOC maxdepth:6 firsth1:1 numbering:0 flatten:0 bullets:1 updateOnSave:1 -->

- [quick introduction to use github and github](#quick-introduction-to-use-github-and-github)   
   - [install and initialization](#install-and-initialization)   
   - [some common commands in shell:](#some-common-commands-in-shell)   
   - [create a repostroy on the local machine](#create-a-repostroy-on-the-local-machine)   
   - [create a repostory on github and clone it to local machine](#create-a-repostory-on-github-and-clone-it-to-local-machine)   
   - [check status](#check-status)   
   - [add file to staging index](#add-file-to-staging-index)   
   - [ingore files](#ingore-files)   
   - [commit file](#commit-file)   
   - [check your commit](#check-your-commit)   
   - [check what changes has been made](#check-what-changes-has-been-made)   
   - [add remote github](#add-remote-github)   
   - [upload your commit to github](#upload-your-commit-to-github)   
   - [add/delete tag](#adddelete-tag)   
   - [branch](#branch)   
      - [create a branch](#create-a-branch)   

<!-- /MDTOC -->

# quick introduction to use github and github
this repostory contains some basic git commands and tutorials to get things to work. Just in case, in future, if I forgot everything, I can always come back here to pick it up.

## install and initialization

1. go to https://git-scm.com/downloads
download the software for Windows
install Git choosing all of the default options
2. open the git terminal
  type the following code:
```
# sets up Git with your name
git config --global user.name "<Your-Full-Name>"

# sets up Git with your email
git config --global user.email "<your-email-address>"

# makes sure that Git output is colored
git config --global color.ui auto

# displays the original state in a conflict
git config --global merge.conflictstyle diff3

git config --list

# use atom as editor
git config --global core.editor "atom --wait"
```

## some common commands in shell:
1. list the document in folder `ls`
2. make directory `mkdir` `mkdir -p udacity-git-course/new-git-project && cd $_`
3. change folder `cd`
4. remove folder or directory `rm`
5. quit from current descrition `q`
    for example, you use `git log -p`, it gives you a list of all the changes,
    you want to quit, just type `q`

## create a repostroy on the local machine
create a folder to store the repostory
in the folder, right click and choose _git bash here_
type:
`git init`

## create a repostory on github and clone it to local machine
login to github, create a new repostory, copy the link of the repostory
type:
'git clone https://github.com/jbdx6307/git-github_intro_code.git'
after that make sure you cd to the folder of this cloned reporstory
`cd git-github_intro_code`

## check status
`git status`
for example, I just added a readme.md file in to my repostory folder
use `git status`, it will show:
`On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        README.MD

nothing added to commit but untracked files present (use "git add" to track)`
since the file is just placed in this foder , it has not been added to staging,
it has not been committed either

## add file to staging index
`git add <file name>`
`git add README.MD`

after running this commands, check status:
`On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)`

you can also use `git add .`
this will include everyfile in the folder to staging

## ingore files
if you use `git add .`, you may put everything in folder to staging, if you do
not want certrain files to staging, you can create a _.gitignore_ file in folder
(the same directory that the hidden .git directory is located).

Globbing lets you use special characters to match patterns/characters.
In the .gitignore file, you can use the following:

blank lines can be used for spacing
``#`` - marks line as a comment
``*`` - matches 0 or more characters
        for example: `samples/*.jpg` every .jpg file in samples folder will not
        be committed
``?`` - matches 1 character
        for example: `"be?rs"` bears, beers will all be ingored
``[abc]`` - matches a, b, _or_ c
``**`` - matches nested directories
      for example `a/**/z` matches a/z or a/b/z or a/b/c/z

## commit file
`git commit -m "Initial commit"`
this will commit the files in staging to the reporstory
the -m followed by a string wil aded a short descprtion to this commit.

if you just type `git commit`, it will open the bonded text editor, you can
put description in there

## check your commit
`git log`
this will check the descprition of your each commit

wanna see how the commit change? type:
`git log -p`

wanna quick exam all the descriptions? type:
`git log --oneline`

## check what changes has been made
if you made some change and save the file, and save it. use
`git diff` to see what you have changed

if you commit your file, you can also use `git log -p`

## add remote github
`git remote add origin https://github.com/jbdx6307/git-github_intro_code.git`
now this link is named origin

## upload your commit to github
`git push -u origin master`
upload everything in your master branch to github-origin(code name with the
  repostory describe by the link above)

## add/delete tag
`git tag -a v1.0`
this will add  an annotated flag named v1.0. you can put descprtion in this tag

`git tag -d v1.0`


## branch
### create a branch
`git branch sidebar`
after you create this branch, the command prompt still in master. We need to
switch to it if we want
