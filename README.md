# gwc_hello_git
## An introduction to git, github, and open source! 

Today, we will be learning about some basic, low-level concepts that often aren't taught in school. 

1) Open your **terminal**.

"Open my what??"

***MacOS pro-tip detour!! Try pressing command-spacebar on your keyabord. This will open the Mac searchlight bar. Type "Terminal" in the search bar and hit return on the first result. This will open your terminal. You can also drag the terminal onto your Mac's dock, since you'll probably use it a lot.***

Ok. Now you have the terminal open. You can customize your terminal too, there's a link in "Further reading."

2) Now that you have your terminal open, the first thing we're going to do is configure git. Git has already been installed on your latptops. Of course, use your name and email address instead of the examples below. Congratulations! You're now a git user. 

```git config --global user.name "FIRST_NAME LAST_NAME"```

```git config --global user.email "MY_NAME@example.com"```

3) Next we're going to pair up and make your first git repo. We're going to do what's called **pair programming**, where you both work at one workstation (laptop.) Often, developers do this because a second set of eyes catches bugs faster while the code is still being written. Today, we're doing it so you can learn how git is used to share code between two (or more) programmers. 

On laptop #1, type the following linux commands into your terminal 

```cd ~/Desktop```

```Mkdr my_first_repo```

```cd my_first_repo```

```git init```

Yay! You've made an empty repository. 

"A what?" 

A **reposistory** is where you can upload code. For today's demo, we're going to be using github.com for our repository, but there are other services that serve the same function. 

4. Lets add some content to our repository! Still using laptop #1, type the following: 

```touch hello.txt```
```open hello.txt```

This will open the new file in your text editor. You'll see a blank page.

Write the following

```Hello, my name is [YOUR NAME]```

Hit save. 

5. Now we're going to commit our new code. 

Go back to the terminal and type ```ls```. This command lists all the files in the folder you're working in. 

You should see hello.txt. Excellent. So, just like you saved the text document, now you're going to **commit** it. Sounds serious right? Committing code is when you add it to your repository, and also add it to the git history of your entire codebse. Once you've committed code, that version of that code will always exist. You can go back to it if you have to. Why would you have to? Maybe your code gets so complicated it stops working, and no matter how hard you try to fix it, it only get's worse. You may just want to go back to "a known good state." Comitting is the ultimate "save" for your code.

Type the following: 

```git add -A .```

```git commit -m "My first commit"```

***Detour 2: What does the "-m" mean? The "m" here stands for message, and it can be any text you want it to be. A good message should describe your changes, so a programmer reading the git messages can understand your thoughts while you were writing your code. ***

Congratulations! You committed. But nothing looks different. Try typing 

```git log```

Now you should see the author, date, commit message, and a long text string (we'll talk about the text string later.) 

If you want to, now try making a second change to your .txt file, and commit that with the same commands above. Don't forget to change your message!

6. This is great, we've got our code saved locally, but how do we share it. It's time to learn about **pushing code** and to do that, we'll sign up for github.com. 

https://github.com/

Everyone in the team should do this on their own laptop: pick a username and password, and use your email address. You're all set! Later you can customize your new github.com account with a picture and biography. 

Now, go back to laptop #1 Click the green "NEW" button in the upper left corner. Agree on a name for your repository, keep it public, and check the box to include a README. Then click the green "Create Repository" button. 

Now, in your web browser, you'll see instructions for **adding a remote**. You have an existing repository already, so we'll use the second set of instructions ("... or push an existing repository") You've already run "init" and made a couple of commits, so all that's left to do is add the remote URL and send your code off to github. Copy the entire "git remote add" command exactly from the github web apge. 

Example: 

```git remote add origin git@github.com:LizCira/test.git```

Now, push the code: 

```git push -u origin master```

Now, refresh your browser, and you'll see your file!

Even crazier, switch to laptop #2 and type in the github URL for your new repository. You should see the same thing. Anyone on the internet can you see your hello.txt now. Congratulations, you've shared code! This is so exciting, let's just take sixty second to celebrate our greatness. 

7. Whew! That was fun, but we're back. We used laptop #1 to write a file, and share it. Now we're going to use laptop #2 to **pull** the code, and contribute. 

Laptop #2 should already be open to the github repository we created. On the right of the page, you should see a "Clone or download" button. Click that button, and you'll see a URL. If it's not already done, select "Use HTTPS." Copy the https: URL, and run the following command (using your own URL, of course):

```git clone https://github.com/LizCira/test.git```

Now, look on your computer's desktop, and you'll see a new folder. What is this?? It's the repository! 

# Further Reading

## Bash commands
http://www.informit.com/blogs/blog.aspx?b=2e1a39cd-e73b-4f8d-82f2-5f9b769132e1

## More about git history
https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History

## Markdown
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

## Bash Prompt
http://osxdaily.com/2013/02/05/improve-terminal-appearance-mac-os-x/
