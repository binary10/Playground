# Git Tips

The best way to learn something is to teach it (or write about it), so here are the things I've learned from using and reading about Git.
Everyone knows how to save. But,
* What if you want to save multiple copies?
* What if you want to know how something looked like at any moment in time?
* What if you wanted to experiment and try something completely different without breaking functionality?
* What if you want to collaborate with others and bring in changes made by other people?

Git allows you to save with a purpose/reason/commit message and do all the things listed. 
Here are some ways of thinking about and using Git that I've gained climbing the learning curve.

##1. A repository is a folder with special powers.
A repository is a folder that keeps a journal of your changes and knows exactly how to make itself look like it did at any point that you created a checkpoint/snapshot in your journal. It is the history of all the work you did. It can also be branched (see below).
##2. Commit changes to your "journal" often and in units of related work
The point of committing changes is to be able to go back to a point in time when everything worked. By waiting for long periods of time and allowing multiple changes to build up, you won't know which piece broke what. It’s also good to “stage” the files you want to commit in related pieces. For example, if you create two files that relate to each other and a third unrelated file, you should make a commit with the first two files separate from the third.
##3. Each commit is a snapshot of your work.
By checking out a commit/branch, you are moving from snapshot to snapshot. The files you see on your drive will change to reflect this. Each snapshot has a cryptographic SHA ID that acts as a barcode for your snapshot.
##4. A branch is a label for a snapshot...
A branch points to a snapshot and labels it. The branch name master is a name for a given snapshot. As you add commits to this snapshot, the label moves to the most current one. All branches start out pointing to a commit in another line of development. As you add to it, it will move forward. 
##5. Merging takes two snapshots and combines changes... or fast-forwards.
There are fast-forward merges and three-way merges. You must be “in a branch” and merge another into that branch. Your current branch will advance while the other stays put on the commit it pointed to.
##6. Revert, don't reset (unless you want to sync your folder with the last commit).
Resetting deletes history. Don't do this. Even your mistakes are worth keeping in your history because you can go back and learn from them. Reverting the mistaken commit will bring you back to the commit prior. 
##7. Moving files and renaming is confusing.
Still working on this one...
##8. The working copy is what you see in your folder.
Your working copy is what is in the latest commit you checked out and the uncommited modifications you’ve made.
##9. "Unadded" changes/files are the things you haven't yet commit.
##10: Create a branch and rename it if you want to go back in time.
##11: Abandoned branches can be tagged so that the branch isn't deleted.

## 12: A tag is like a branch, but...
A branch and tag are both labels of a commit, however a branch is an active line of development and will move forward with each commit. A tag will always point to the same snapshot. It is an alias for a commit ID.
##13: Use .gitignore to avoid tracking certain files.
A good example is when you are compiling a program and do not want each compilation to cause many files to show up in the status. 

--- 

In summary, this system enforces good programming -- and engineering -- habits and supports the development cycle that can be broken down into the following pieces:
### Code development process
* Development team writes code, unit tests, and possibly some of the acceptance tests.
* QAs check for defects and write more acceptance tests.
* Application is deployed to test environments.
* Application undergoes performance and integration testing on deployed environments.
* Application is promoted to stage (preproduction) environment.
* Smoke tests are run against the stage environment to ensure components work together correctly. (See later in this chapter for more details.)
* Application is deployed to production environment.

### Growing code bases
* Use TDD to ensure new changes don't break old functionality (Think of America's Test Kitchen)
* Use Version control to make sure changes can be reverted and collaboration can occur
* Regression testing
* Code coverage (testing)
* Lint checker (style guide)
