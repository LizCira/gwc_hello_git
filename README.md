# gwc_hello_git
## An introduction to git, github, and open source! 

Today, we will be learning about some basic, low-level concepts that often aren't taught in school. 

### 1) Open your **terminal**.

"Open my what??"

***MacOS pro-tip detour!! Try pressing command-spacebar on your keyabord. This will open the Mac searchlight bar. Type "Terminal" in the search bar and hit return on the first result. This will open your terminal. You can also drag the terminal onto your Mac's dock, since you'll probably use it a lot.***

Ok. Now you have the terminal open. You can customize your terminal too, there's a link in "Further reading."

### 2) Now that you have your terminal open, the first thing we're going to do is configure git. 

Git has already been installed on your latptops. Of course, use your name and email address instead of the examples below. Congratulations! You're now a git user. 

```git config --global user.name "FIRST_NAME LAST_NAME"```

```git config --global user.email "MY_NAME@example.com"```

### 3) Next we're going to pair up and make your first git repo. 

We're going to do what's called **pair programming**, where you both work at one workstation (laptop.) Often, developers do this because a second set of eyes catches bugs faster while the code is still being written. Today, we're doing it so you can learn how git is used to share code between two (or more) programmers. 

On laptop #1, type the following linux commands into your terminal 

```cd ~/Desktop```

```mkdir my_first_repo```

```cd my_first_repo```

```git init```

Yay! You've made an empty repository. 

"A what?" 

A **repository** is where you can upload code. For today's demo, we're going to be using github.com for our repository, but there are other services that serve the same function. 

### 4. Lets add some content to our repository! Still using laptop #1, type the following: 

```touch hello.txt```

```open hello.txt```

This will open the new file in your text editor. You'll see a blank page.

Write the following

```Hello, my name is [YOUR NAME]```

Hit save. 

### 5. Now we're going to commit our new code. 

Go back to the terminal and type ```ls```. This command lists all the files in the folder you're working in. 

You should see hello.txt. Excellent. So, just like you saved the text document, now you're going to **commit** it. Sounds serious right? Committing code is when you add it to your repository, and also add it to the git history of your entire codebse. Once you've committed code, that version of that code will always exist. You can go back to it if you have to. Why would you have to? Maybe your code gets so complicated it stops working, and no matter how hard you try to fix it, it only get's worse. You may just want to go back to "a known good state." Comitting is the ultimate "save" for your code.

Type the following: 

```git add -A```

```git commit -m "My first commit"```

***Detour 2: What does the "-m" mean? The "m" here stands for message, and it can be any text you want it to be. A good message should describe your changes, so a programmer reading the git messages can understand your thoughts while you were writing your code.***

Congratulations! You committed. But nothing looks different. Try typing 

```git log```

Now you should see the author, date, commit message, and a long text string (we'll talk about the text string later.) 

If you want to, now try making a second change to your .txt file, and commit that with the same commands above. Don't forget to change your message!

### 6. This is great, we've got our code saved locally, but how do we share it. It's time to learn about **pushing code** and to do that, we'll sign up for github.com. 

https://github.com/

Everyone in the team should do this on their own laptop: pick a username and password, and use your email address. You're all set! Later you can customize your new github.com account with a picture and biography. 

Now, go back to laptop #1 Click the green "NEW" button in the upper left corner. Agree on a name for your repository, keep it public, and leave the README box unchecked. Then click the green "Create Repository" button. 

Now, in your web browser, you'll see instructions for **adding a remote**. You have an existing repository already, so we'll use the second set of instructions ("... or push an existing repository") You've already run "init" and made a couple of commits, so all that's left to do is add the remote URL and send your code off to github. Copy the entire "git remote add" command exactly from the github web apge. 

Example: 

```git remote add origin git@github.com:LizCira/test.git```

Now, push the code: 

```git push -u origin master```

Now, refresh your browser, and you'll see your file!

Even crazier, switch to laptop #2 and type in the github URL for your new repository. You should see the same thing. Anyone on the internet can you see your hello.txt now. Congratulations, you've shared code! This is so exciting, let's just take sixty second to celebrate our greatness. 


### 7. Whew! That was fun, but we're back. We used laptop #1 to write a file, and share it. Now we're going to use laptop #2 to **pull** the code, and contribute. 

For this exercise, both users will need to be collaborators. You'll see a few tabs at the top of your github page. On laptop #1 (the github account holder), go to "Settings" and then click "Collaborators" on the left sidebar. Type User #2's github name, and click "Add collaborator." Now both users can contribute to the repository directly (we'll talk about other ways of contributing to a repository later.) We may not get to cover it during the talk, but I've included links about using **pull requests** in your development workflow--this is one a developer requests review and approval of their code before they can add to a repo. 

Laptop #2 should already be open to the github repository we created. On the right of the page, you should see a "Clone or download" button. Click that button, and you'll see a URL. If it's not already done, select "Use HTTPS." Copy the https: URL, and run the following command (using your own URL, of course):

```git clone https://github.com/LizCira/test.git```

Now, look on your computer's desktop, and you'll see a new folder. What is this?? It's the repository! You just **cloned** your first repo. 

Make a change to hello.txt (or even add a new file!) Run the git commands to Add, Commit, and Push again. Now you'll see the changes on github.

You're now collaborating on an open source project. WOoOoooooh! 

### 8. Bonus rounds! So now, what happens if laptop #1 wants to add or change something more? Can you just go ahead and commit a new file? 

Spoiler: NO! 

Before laptop #1 can add more code, you'll need to **pull changes**. Right now, the github repository is **ahead** of laptop #1. If you try to push code from laptop #1, you'll get an error message. 

Run the following command to resolve it: 

```git pull origin master```

Now laptop #1 and laptop #2 are both in sync with what's on github, and you can continue working.

### 9. Branching, merging, reverting, merge conflicts... hey look, we're out of time!

j/k lol. We might not be out of time. If we're not, here's a few more things to try. 

**Make a branch**: Branching is for working on a feature without changing the original ("master") code. Often, a development team will work on different features, for example, "Add a log-in screen" or "Update the fonts." So that the master code is always in working condition, they create a second code branch. Try this: 

```git branch login_screen```

```git checkout login_screen```

Create a second file, with whatever content you want. 

```git add -A .```

```git commit -m "Lookit my branch!```

```git push origin login_screen```

On github, in the upper left, you'll see a grey box with "Branch:Master" in it. Now, that box will have a second drop-down option when you click it; it's your new branch! You'll see now there are two versions of your code. The master code is in a **known good state**, and a cool new feature ("login screen") is being developed and tested. 

**Merge your branch**: So what happens when the login screen is done?? It's like we have two versions of the same code right now. Try this: 

```git checkout master``` (Now you're back on the master branch)

```git merge login_screen master```

You just combined your login_screen code and your master code. Run ```git log```, and it should be looking pretty interesting now. 

**Uh-oh! A merge conflict :(** There will probably come a time as you work together that you'll find a merge conflict. This happens when two programmers try to change the exact same line. 

Try it yourselves within your group and see what happens. First run

```git checkout master```

```git pull origin master```

Overwrite the first line of hello.txt. Then try to commit and push it back to master. You should get an error message. You should also see two versions of your text in your text editor. Choose the correct version (presumably the more recent change) delete the rest, and try to commit and push again. 

**What if you want to undo?** Every now and then, you'll find you code yourself into such a bad place you just need to throw away a couple of hours work and start over. It's ok! Just as long as you don't have to throw away the whole project. Git lets you do this. That's why you should always commit everything; it gives you more places you can go back to. 

The full list of git commands is more than I can cover today (that's what the documentation link is for) but we will look at this one. It is very usful and very powerful, so be very careful. Take the commit number you'd like to go back to from your git log. 

```git reset --hard ########```

```git reset --soft HEAD@{1}```

```git commit -m "Reverting to ######```

As I said, be very careful with this since it will completely erase the work you did after commit ######. Read the git documentation for other ways to revert commits. 

### 10. Open source

So why are we sharing all of this code, anyway? If you put all this work into something, wouldn't you want to keep it for yourself? Open source is as much a philosophy as it is a programming practice. With an open source tool like github, you can test other people's code and fix bugs in other people's code. You can provide cool new tools for your community. You can do pretty much anything! Linux, the operating system MacOS is based on, couldn't exist without open source. A big tech company like Facebook or Google develops an amazing code testing framework, and instead of keeping it, they open source it and let anyone use it--the result is everyone has better tested code :D 

Think about contributing to open source. If you want to learn more, github has a "Good first issue" tag
https://github.com/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22

Also, a "Help wanted" tag:
https://github.com/issues?page=3&q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22

Although both of those can be pretty advanced, so don't get discouraged! 

### Whew! We really are done. Thank you for reading!

![alt text](https://media.giphy.com/media/l3q2zVr6cu95nF6O4/giphy.gif "Party!")


## Further Reading

### Full github documentation
https://git-scm.com/doc

### Bash commands
http://www.informit.com/blogs/blog.aspx?b=2e1a39cd-e73b-4f8d-82f2-5f9b769132e1

### More about git history
https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History

### More about merge conflicts
https://help.github.com/en/articles/about-merge-conflicts

### More about forking code & using pull requests 
https://help.github.com/en/articles/fork-a-repo

https://gist.github.com/Chaser324/ce0505fbed06b947d962

### Markdown
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

### Bash Prompt
http://osxdaily.com/2013/02/05/improve-terminal-appearance-mac-os-x/

### The history of Linux open source
http://www.unterstein.net/su/docs/CathBaz.pdf
