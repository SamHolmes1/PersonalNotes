# Command line Tasks

```
Command Line Tasks 
--------------------------
1. Use the command echo to print a message `hello <your-name>` to the terminal
2. Print your current working directory to the terminal
3. Change directory back to your home directory (if you're not already there) and then use `mkdir` to create a new directory called `northcoders`
4. Change directory into the `northcoders` directory and print your current working directory again - always double checking where you are
5. Create some directories inside `northcoders` called `intro-week`, `fundamentals`, `backend`, `frontend` and `projects`
List all the directory contents of `northcoders` - you should be able to see the 5 directories you've just created
6. Change directory into your `intro-week` directory
7. Create a new blank file in your `intro-week` directory called `questions.txt` - look up the commands to do this if you need to: you can find some good documentation online here: [http://oliverelliott.org/article/computing/tut_unix/](http://oliverelliott.org/article/computing/tut_unix/)
8. Use the `cd ..` command in your terminal. Then print your current working directory to work out where you are. What is happening when you run the command `cd ..`? (Bonus: what about when you run `cd ...`?)
9. Run `man ls` command in your terminal. Scroll down through this manual to try and figure out what the difference between `-a` and `-A` as additions to the command `ls` is. Then run the commands `ls -a` and `ls -A` in your home directory
10. Try navigating to your home directory and then run the command `ls -a` again but channel the output of this command into a text file called `directory-contents.txt`. Then use another command to read the contents of the `directory-contents.txt` file to check your work. Remember you'll need to use the re-direct operator `>` to complete this task
11. If you manage to complete all of the tasks above … nice one! Prepare yourself for the next lecture by doing a bit of reading beforehand. Check out this article on version control [https://www.atlassian.com/git/tutorials/what-is-version-control](https://www.atlassian.com/git/tutorials/what-is-version-control)
```


```
Answers
---------------
1. Echo 'Hello Sam'
2. pwd
3. cd /home/oni | mkdir northcoders
4. cd northcoders/ | pwd
5. mkdir {all the directories}
6. ls
7. cd intro-week | touch questions.txt
8. cd .. // Go up a directory each extra dot is one level up
9. -a is all -A is all without the . and ..
10. ls -a | ls -A
11. 

```
# Git Tasks

```
1. Use `pwd` and `ls` to check where you are in your terminal
2. Navigate to the `intro-week` folder you created earlier
3. Make a new folder inside here called `git-practice`
4. Navigate into this folder and run `ls -a`: what does the `.` and `..` refer to?
5. To turn this folder into a git repository, run `git init`
6. Run `ls -a` again to see the `.git` directory which means your repository has been successfully initialised
7. Create a new file called `films.txt` and add a film title here.
8. Run `git status` to see that this change you've made is currently untracked by git
9. Add this file you've created to git's staging area
10. Run `git status` again to see that this file is now is the staging area
11. Commit this change
12. Run `git status` to see that your working directory is now empty, then run `git log` - what does this command seem to show you?
13. Add another film to the `films.txt` file then repeat steps 8-12 to commit this change
14. Add a final film to `films.txt`. Now create another file called `snacks.txt` and add your favourite film-night snacks to it.
15. As the above changes are unrelated, make two separate commits for these changes (remember you will need to add and commit the files individually).
```

```
Answers
---------------
1. pwd
2. cd intro-week
3. mkdir git-practice
4. . is the current directory, .. is the directory above. Used for the cd command
5. git init 
6. ls -a
7. touch films.txt
8. git status
9. git add films.txt
10. git status
11. git commit -m "inital commit, add films.txt"
12. git status, git log
13. repeat
14. repeat
15. repeat
```