
# Welcome to GIT

Git is a version control system. It helps us collaborate and back things up in case things go badly. This simple group project will let you explore the essential functions and flow of Git and Github without worrying about any actual code issues. You're expected to work together to understand the concepts and get everyone through the process. Instructors will not be walking you through this, but please reach out if you're stumped with a problem or have a question that nobody in the room can answer. One of us will come to your breakout room to help you.

# Set up the Repository on Github

One person, navigate to github.com, log in and create a repository in the Nashville Software School organization. Be sure it is public, and check the checkbox to include a readme.md file

Click the **create** button, and it should set up a repository and navigate to the page, where you will see it has a readme file. That file is included as an overview of the project, and currently it just shows the project's name.

Each member of the group should visit the repository url, click on the green **CODE** button, then under SSH, copy the git URL.

Open your terminal and navigate to your workspace. On the command line, type: `git clone {pasted_git_url_goes_here}`

CD into the new folder and note that there's a readme.md file there. Now everyone is set up to collaborate with this repo.

# Add the Original Poem

One teammate, create a poem.txt file in your project folder and paste this lovely poem into that file:
```
Roses are red.
Violets are blue.
Github is beautiful
And so are you.
```

Type `git add .` in your terminal (while in the project folder) to have git track all your latest changes

Type `git commit -m "added a poem"` to tag this revised version of the project and provide a brief description of changes.

Type `git push origin main` to upload these changes to the online repository. Now everyone should be able to see the file on github.

All other teammates, type `git pull origin main` to sync your local files up with the latest version.

# Make a Change

We have just updated our project and pushed the new version directly to our shared repository. But when collaborating, this can get very messy. What we really want to do is make our own **branch** for whatever task we're working on - a separate version of the project that's forked off the main branch. Then we make all our changes in that branch, and when we're finished and we've confirmed that everything is OK, then we merge the branch back into the main branch.

One teammate, type `git branch make-roses-pink` in the terminal, which will create a new branch. Then type `git checkout make-roses-pink` to switch into that branch. Note: you could combine these steps with the single command `git checkout -b make-roses-pink`.

Next, replace the word "red" in the first line with "pink" and save the file. In the terminal type `git add .`, then `git commit -m "roses are now pink"`, then `git push origin make-roses-pink` to add, commit and then push the changes, still staying within our new branch.

Now, anyone should be able to view the new branch with its changes. Refresh the github page (with the **code** tab selected at the top) and you should have a dropdown with **main** selected. Clicking that dropdown, you can now select the new `make-roses-pink` branch to view the files, and click on the story.txt file to see its updated contents. 

Also, at the top of the code overview page, there should be a new message with a green **Compare and Pull Request** button. One teammate (typically whoever made these changes) should click this button to look over all the changes. This page shows a **diff** view, which uses color-coded formatting to compare the differences between the versions. If this looks OK, click **Create Pull Request** to start merging these changes back to the main branch.

Next, another teammate should review the changes and confirm that these are acceptable before we merge them. In github, there is a **Pull Requests** tab, which should now have a **1** beside the text. Click that, then click on the list item for this update. You can review these changes by clicking on the **Files Changed** tab, which will show the same diff view we saw earlier. But since there are no conflicts, we can just click the **Merge Pull Request** button and then click **Confirm Merge**. 

At this point, you can delete this branch with that button. And if you return to the **Code** tab view and select **main** branch, you can see the latest changes are now applied there. Also, any other teammates can type `git pull origin main` to get the latest version on their local copy.

# Create a Conflict

Working in branches really helps avoid conflicts, but it can still happen. If two teammates branch around the same time, then one commits some changes and merges, then when the second teammate merges changes, there can be conflicts. 

Two teammates should each create a new branch. One should name it `make-violets-violet` and the other should name it `make-violets-orange`. Then they should each modify the code accordingly. 

One teammate should add, commit, push and merge just as we did above. Then the next teammate should. When they try to do a pull request, there will be a conflict. Git can't decide which of these changes to use, so we will have to resolve this manually before we can merge it into main. 

You can still create the next pull request as usual, but you'll have to resolve conflicts before merging. under the pull requests tab, select the appropriate item in the list. Then click **resolve conflicts**

You'll see an inline text editor with some strange stuff added to the file. One version of the change is between <<<< and ====, and the other is between ==== and >>>>. Make change to the file, removing these special characters and leaving only the exact text that we want to use. Then click **mark as resolved** and you'll be able to **commit merge**, then click the merge button as we did before. Now, the version in **main** is whatever you decided is the correct version. And we can continue pulling, branching, working and pushing as we have before.


