# test1

# Version control 

## First push and pull tests
- A line added via laptop
- A line added via git

## An introduction with recipes 
- https://github.com/dianaiusan/recipe-book
- The project description is in md.
- All titles reflect contents, and edits, and you can always go back to this specific version.
- Removed lines are red, added lines are green.

### Assignment on recipes
- Tally changes in guac recipe: go to it, history, 5 edits
- Which recipes have salt: use upper search field, determine word and repo, 5 recipes
- Knowing who did what: go to guac, blame
- Are you allowed to reuse the book: go to LICENSE in main folder
- Then, there was something with issues and pull requests which I haven't figured out

## Forking
- Check notes
- Creating a fork is creating a sort of branch of an extant repo (own copy).

## Creating repo's
- https://github.com/UtrechtUniversity/simple-r-project
- Create new repo, use template of UU, this is a repo in your personal space (test2_repo_create)
- There's a really nice slide differentiating the two
- You can make edits in your new repo
- AND COMMIT THEM
- AND THEN MAKE AVAILABLE LOCALLY by cloning: repo > code > copy ssh key
- check your directory in the terminal, I've made a mistake and placed test2 in test1

## Connect with R
- You can connect R with Git but it's a figuring out process (which we don't do in class).
- Maybe I need to reinstall R for this? 

## Some notes
- Use git status in abundance.
- Are there temp files you don't want to track, add to gitignore

# Version control - advanced materials
- Branches are very useful, but you can only merge if you are certain it will work. Otherwise, your whole code breaks.
- We try it out by forking the recipe book and adding branches.
- When doing so, the main gets copied to main. You can then work in the new branch without touching main.
- You will see an option to merge and check pull requests, where you can explain what you did with words:
'# Title / words / code block with ```` and at the bottom too.'
- Use Create a merge commit (don't necessarily rebase), if you use squash, all your updates will be squashed to one file and added - useful for long changes.
- Merging won't remove the branch.

## In terminal

### You need to also pull your merge in the shell to add it locally: 

_Just for clarity:_
5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (4/4), 1.81 KiB | 88.00 KiB/s, done.
From github.com:annhal/test2_repo_create
   d17b9d8..a7bbd57  main       -> origin/main
 * [new branch]      cakes      -> origin/cakes
Updating d17b9d8..a7bbd57
Fast-forward
 cake recipe | 6 ++++++
 1 file changed, 6 insertions(+)
 create mode 100644 cake recipe

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ ls
 CITATION.cff   R/         'cake recipe'   docs/      simple-r-project.Rproj
 LICENSE        README.md   data/          results/

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git branch
* main

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git branch -a
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/cakes
  remotes/origin/main

### Creating branches in terminal
We create a branch in the terminal, on our local computer. We make 'morecake' branch, from 'main' (all locally).
Note that you: 
(a) we create the branch morecake locally
(b) in it, we create morecakefile.txt
(c) we then want to commit our file to 'main' on git (we ignore the branch we created; we know it works and want to merge directly into 'main')
(d) before we push, we need to switch to 'main' as that's where we want to push our morecakefile.txt to
(e) in github, there won't be a new branch just a new file

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git branch morecake main

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git branch -a
  cakes
* main
  morecake
  remotes/origin/HEAD -> origin/main
  remotes/origin/cakes
  remotes/origin/main

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git switch morecake
Switched to branch 'morecake'

5537304@UU105242 MINGW64 ~/test2_repo_create (morecake)
$ git add morecakefile.txt

5537304@UU105242 MINGW64 ~/test2_repo_create (morecake)
$ git commit -m "added a morecakefile to morecake branch"
[morecake aa4123d] added a morecakefile to morecake branch
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 morecakefile.txt

5537304@UU105242 MINGW64 ~/test2_repo_create (morecake)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git merge morecake
Updating 7ee8e3e..aa4123d
Fast-forward
 morecakefile.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 morecakefile.txt

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git branch -a
  cakes
* main
  morecake
  remotes/origin/HEAD -> origin/main
  remotes/origin/cakes
  remotes/origin/main

5537304@UU105242 MINGW64 ~/test2_repo_create (main)
$ git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 307 bytes | 307.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:annhal/test2_repo_create.git
   7ee8e3e..aa4123d  main -> main



  
