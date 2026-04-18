# GitExercise_Conflicts

1. Clone this repo to your datahub or local computer (your choice)
1. Merging ex1 branch into main branch... the difference here is a simple line of text conflict\\
   1. first look at the diff
  
   2. 
  
   3. 
   1. now merge e1 into main; note how the conflict gets shown to you...
   1. resolve the conflict in whichever way you choose,
   1. add and commit the changes on main
1. Merging ex2 branch into main branch... the difference here is metadata and binaries from a plot
   1. first look at the diff
   1. now checkout e2.
   1.  remove the metadata and outputs by clearing all cell output
   1. add and commit the changes on e2
   1. now merge e2 into main
   2. the bottom of the git panel you can see there are three categories of files that could be the subject of git operations <br>
    "Untracked" for new files you create that are not yet in the repo  <br>
    "Changed" for files already in the repo, but you changed something  <br>
    "Staged" which tracks all the changes you've asked to be grouped together into a commit  <br>
-  Look at the "Changed" section, `Project.ipynb` is there... hover your mouse over it.  You will see icons for opening the file, for making a diff summary of the changes, for discarding the changes, and one for staging the changes for a commit (a + symbol).  Stage the changes!
-  Now that `Project.ipynb` is in the "Staged" category you can scroll down to the bottom of the git panel and commit the changes.  Add a summary (<50 characters), something like "improved code readability".  There is also a space for longer description if necessary.  Press the "Commit" button, and you're done with Part I!

Part II - Merge ex1 into main
-  On the git panel there's a place at the top where it says "Current Branch: main"; click on that menu item to see a list of all the branches available. When you cloned the repository you only got a copy of the default branch (called "main")... there were other branches but they are still only on the remote repo up on GitHub.  Remote branches are marked with the keyword "origin". So "main" is a local branch, "origin/main" is the main branch on GitHub and likewise "origin/ex1" is on Github.  Click on that last branch... 
-  Previously you had only "origin/ex1" and not "ex1", but now you do!  By clicking on "origin/ex1" git made a local branch "ex1" and set it up to track the remote branch "origin/ex1".  Now that we have local copies of both main and ex1 we can merge the branches.  ex1 will be merged into main!
-  OK here's the task: we want to merge the change in branch ex1 (a change of title on the graph) into main, erasing the old title.  But we want to keep our explicit `ax.grid('on')` change which is only on main and not ex1. 
-  Here's how to do it... click on "main" to make sure we are currently on the main branch.  We want to be on the branch that is the destination of the merge.
-  Hover over the local "ex1" branch and a button icon that looks like 3 dots with connecting lines will appear.. when you hover over the button it says "merge this branch into the current one"... go ahead and click it!
-  You will get an error message "Failed to merge ex1 into main".  And now there is a new category "Conflicted" just above "Staged"!  Our file `Project.ipynb` is in that heading as expected!  Hover over the file, and click on the icon to "diff this file" that appears.
-  You will now see the diff panel... where there are conflicts you have from left to right three possiblities: <br>
    "Current" (what was in main before the merge) <br>
    "Common Ancestor" (what the file looked like when ex1 split off from main) <br>
    "Incoming" (what was in ex1 before the merge) <br>
    Underneath the triple column you will see a panel where you can manually change the conflict zone to make the outcome what you want.  Whatever you put in this lower panel is what the outcome of the merge will be!
- Make the outcome of the merge to be the ex1 title and the main ax.grid('on') command!  Save it by clicking the button on the top right that says "Mark as resolved". You will see that `Project.ipynb` moved from "Conflicted" to "Staged"
- Go look at the notebook and make sure it is what you wanted it to be.  It is also useful at this stage to run-all to ensure that the Frankenstein's monster of code from both branches is actually functional as a combo.  You will get a warning that you have made changes that are unsaved because every time a notebook runs it changes metadata stored inside it. Ignore that... if you press save again you will add a new set of changes that need to be staged and committed, but those changes are USELESS... its just increments to the run counter of the cells and the exact binary data of the plot generated.
- Let's commit the merge!  On the git panel give it a summary (something like "merged ex1 into main") and press the commit button.
   
Finally
- All the changes you've made so far only exist in the local copy on Datahub. We need to push the changes from the local copy to your forked copy.
- On the top left are a set of cloud icons, one with the arrow pointed down (that's pull) and one with the arrow pointed up (that's push).
- If there's a red dot on one of the clouds you need to do that action.  In this case you only need to push. Once you've pushed your exercise is done... the changes you've made have appeared on GitHub and are visible to other people including our auto-grading scripts.
- **IF YOU DON'T PUSH AT THE END OF THE EXERCISE YOU WILL LOSE POINTS ON THE AUTOGRADER** 
  
Congrats!! You've dealt with a simple version of the notebook conflict problem. This workflow will happen in your projects all the time, when person A and person B need to merge their seperate parts of the project together into the final project. 

Another common project workflow is if there's a red dot on pull (down arrow) that means someone else made changes to the remote that you don't have.  Pull operations need to be done before push operations... so if someone changed the remote after your clone but before your push you will have to pull first, merge, and resolve any conflicts before you are allowed to push your changes to remote.  We didn't have to do that here, but its a very normal workflow for your projects.

   1. resolve the conflict in whichever way you choose,
   1. add and commit the changes on main
