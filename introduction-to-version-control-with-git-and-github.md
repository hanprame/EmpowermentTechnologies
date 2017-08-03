# Introduction to Version Control with Git and GitHub

OBJECTIVES

At the end of the lesson, students should be able to: 

- Enumerate the advantages of using version control during software development
- Use Git version control on their HTML software development projects:
	- Initialize an empty repository
	- Add content to the repository
	- Remove content from the repository
	- View the repository change history
	- Revert to an earlier version
- Use Visual Studio Code to edit HTML files

## Lecture


## Workshop

This workshop is designed to get you up to speed on the code editing and version control tools you will be using throughout the rest of the course. Try to type at least some of the HTML files, to get yourself acquainted with editing HTML files using Visual Studio Code. But if pressed for time, you can copy-paste the code from this document to the Visual Studio Code editor.

In this workshop, you will:

- create a simple HTML project
- initialize a repository for your project
- upload the repository to GitHub
- make changes to the project and upload them to GitHub
- view the repository history, locally and on GitHub
- revert some of the changes
- learn how to use branches for working concurrently on different features of the project
- fork an existing open-source project and work on your own version

You will be working on HTML pages on this workshop, but the focus of this workshop is version control with Git. If you do not understand some of the HTML tags you use on the workshop, don't worry, we will discuss them in the succeeding meetings.

If you haven't yet done so, please head over to GitHub.com to create your account. User your jbrc.edu.ph email.

### Project Overview

You have been recently hired as the web developer for ACME Corporation. Your first task is to create a brochure web site - a static web site where they can let potential customers know more about their products. For the initial release, you will a web site with:

- A home page that describes the company and lists their two most popular products: 
  - ACME Giant Rubber Band
  - ACME Rocket
- A web page for each of the two products above 

#### SESSION 1

In this session you will create a skeleton of your project, save it to a local Git repository, and upload the repository to GitHub.

#### Tell Git who you are

Before everything, you need to tell git your email and name so that Git will mark your commits accordingly.

_NOTE: When you see "Run [cmd]" read it as "Type [cmd] on the Git Bash window and press [Enter]"_

Run the two commands below:

```
git config --global user.email [youremail]
git config --global user.name [yourname]
```

Example:

```
git config --global user.email rbatnag@jbrc.edu.ph
git config --global user.name "Radamanthus Batnag"
```

#### Create the project

If you don't already have one, create a `projects` folder inside your `Documents` folder. Inside the `projects` folder, create an `acme` folder.

Run Visual Studio Code and open the `acme` folder you created above.

From within Visual Studio Code, inside the acme folder, create these three HTML files:
- index.html
- products/giant-rubber-band.html
- products/rocket.html

Put this content inside the three HTML files:

```
<html>
  <p>This is a stub. I will work on this later</p>
</html>
```

Now that we have the project structure in place this is a good time to save our work into the repository. We'll do that in the next section.

#### Put the project into a local Git repository

Open Git Bash. Press `Start`, type `git bash`, and click the "Git Bash Desktop app".

Inside the Git Bash window, go to the acme folder you created earlier. Type `cd Documents/projects/acme`.

_NOTE: You can use tab completion. Type "cd Doc" then press [tab]. You'll see that the Git Bash window changed the command text to "cd Documents"_

Run `git init`

```
$ git init
Initialized empty Git repository in C:/Users/student/Documents/projects/acme/.git/
```

You now have an empty git repository. Run `git status`

```
$ git status
On branch master

Initial commit

Untracked files:
(use "git add..." to include in what will be committed)

index.html
products/

nothing added to commit but untracked files present (use "git add" to track)
```

Let's add everything we have so far in the project. Run `git add .` 

The `git add` output is empty, but run `git status` again:

```
$ git status
On branch master

Initial commit

Changes to be committed:
(use "git rm --cached..." to unstage)

new file: index.html
new file: products/giant-rubber-band.html
new file: products/rocket.html
```

Our changes have been staged. Time to do our first commit! 

Run `git commit -m "Initial commit"`.

```
$ git commit -m "Initial commit"
[master (root-commit) c3b32fd] Initial commit
3 files changed, 9 insertions(+)
create mode 100644 index.html
create mode 100644 products/giant-rubber-band.html
create mode 100644 products/rocket.html
```

Run `git status` again.

```
$ git status
On branch master
nothing to commit, working tree clean
```

You'll see that the pending changes have already been committed.

#### Explore your local repository

Open Git Bash and run `cd C:/Users/student/Documents/projects/acme`

Run `git log`

```
$ git log
commit c3b32fdc54405d1be76a0b718c70650605345e32 (HEAD -> master)
Author: Radamanthus Batnag 
Date: Sun Jun 25 14:56:13 2017 -0700

Initial commit
```

Let's dissect that output line by line.

```
commit c3b32fdc54405d1be76a0b718c70650605345e32 (HEAD -> master)
```

`c3b32fdc54405d1be76a0b718c70650605345e32` is the commit hash. This is a unique identifier for the commit. You can run `git show c3b32fdc54405d1be76a0b718c70650605345e32` to view the details of the commit (what files were changed, what lines were added and removed for each file). You can also shorten the `git show <hash>` and use only the first few characters of the hash. For example, type `git show c3b3`. As long as there is only one match for that commit hash, it should work just the same. 

```
Author: Radamanthus Batnag 
```

This is the name we used when we ran `git config --global user.email [youremail]` earlier. This part is useful when there are multiple developers committing to the project.

```
Date: Sun Jun 25 14:56:13 2017 -0700
```

This is the timestamp (date, time and timezone) when the commit was made.

```
Initial commit
```

This is the commit title. This can be useful when searching across multiple changes. We will talk about guidelines on the commit title and description later.

#### Save the project into GitHub

You want to put your project on GitHub so that you can work on it from another computer. You can also collaborate on the project with another teammate.

Log in to GitHub.com and go to [https://github.com/new](https://github.com/new) to create a new repository. Name your repository `acme`. Follow the instructions under `push an existing repository from the command line`:

```
cd C:/Users/student/Documents/projects/acme
git remote add origin https://github.com/radamanthus/acme.git
git push -u origin master
```

You will be prompted for your GitHub username and password. If everything is successful, you'll see something like this:

```
$ git push -u origin master
Counting objects: 4, done.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 385 bytes | 0 bytes/s, done.
Total 4 (delta 0), reused 0 (delta 0)
To https://github.com/radamanthus/acme.git
* [new branch] master -> master
Branch master set up to track remote branch master from origin.
```

Open [https://github.com/yourusername/acme](https://github.com/yourusername/acme) to view your project in GitHub

Open [https://github.com/yourusername/acme/commits/master](https://github.com/yourusername/acme/commits/master) to view the commit history.

#### Download the project from GitHub

Now that our acme project is safely stored in GitHub, you can download it even if your local copy gets borked. Let's try that.

Exit Git Bash and Visual Studio Code.

Delete the `Documents/projects/acme` directory from File Explorer.

Open Git Bash again. Go to the `Documents/projects` directory (Run `cd Documents/projects`).

Clone the repository. Run `git clone https://github.com/yourusername/acme.git`.

```
$ git clone https://github.com/radamanthus/acme.git
Cloning into 'acme'...
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 4 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
```

Open Visual Studio Code again. You'll see that the ACME project and the HTML files inside are back there.

In the next session we'll fill our HTML pages with real content and practice reverting some of our changes.

#### SESSION 2

#### Create the home page

Replace the contents of `index.html` with:

```
<html>
  <head>
    <title>ACME Corporation</title>
  </head>
  <body>
    <h1>ACME Corporation</h1>
    <hr>
    <p>We're the leading makers of must-have desert gadgets.</p>
    
    <p>Our latest products:</p>
    <ul>
      <li><a href="products/giant-rubber-band.html">ACME Giant Rubber Band</a></li>
      <li><a href="products/rocket.html">ACME Rocket</a></li>
    </ul>
  </body>
</html>
```

Save the file in Visual Studio Code. 

Verify that you have a valid, working HTML page. From Visual Studio Code, right-click index.html and click `Reveal in Explorer` from the pop-up menu. From File Explorer, double-click index.html to open it in the Edge browser.

After verifying `index.html`, commit it to the local repository. Run:

```
cd Documents/projects/acme
git add index.html
git commit -m "Update the Home page"
```

The output should look like:

```
student@Rad-VM MINGW64 ~/Documents/projects/acme (master)
$ git add index.html

student@Rad-VM MINGW64 ~/Documents/projects/acme (master)
$ git commit -m "Update home page"
[master 5e7c107] Update home page
1 file changed, 16 insertions(+), 3 deletions(-)
rewrite index.html (89%)
```

#### Create the Giant Rubber Band Page

Replace the contents of `products/giant-rubber-band.html` with:

```
<html>
  <head>
    <title>ACME Giant Rubber Band by ACME Corporation</title>
  </head>
  <body>
    <h1>ACME Giant Rubber Band</h1>
    <p>Catch fast road runners by catapulting yourself. Guaranteed 100% safe.</p>
	 <p><a href="../index.html">[Back to Home Page]</a></p>
    <hr />
    <img src="https://i.ytimg.com/vi/CpGfzrkNL5w/hqdefault.jpg" />
    <p>$89.99</p>
    <input type="submit" value="Buy Now" />
  </body>
</html>
```

Just like with `index.html`, verify the HTML in your browser and then commit your changes to the local repository.

```
cd Documents/projects/acme
git add products/giant-rubber-band.html
git commit -m "Update the Giant Rubber Band page"
```

The output should look like:

```
student@Rad-VM MINGW64 ~/Documents/projects/acme (master)
$ git add products/giant-rubber-band.html

student@Rad-VM MINGW64 ~/Documents/projects/acme (master)
$ git commit -m "Update the Giant Rubber Band page"
[master 31416ed] Update the Giant Rubber Band page
1 file changed, 14 insertions(+)
create mode 100644 products/giant-rubber-band.html
```

#### Create the Rocket Page

Replace the contents of `products/rocket.html` with:

```
<html>
  <head>
    <title>ACME Rocket by ACME Corporation</title>
  </head>
  <body>
    <h1>ACME Rocket</h1>
    <p>Upgrade from the <a href="./giant-rubber-band.html">ACME Giant Rubber Band</a> into this more powerful solution. For serious desert warriors.</p>
    <p><a href="../index.html">[Back to Home Page]</a></p>
    <hr />
    <img src="http://orig09.deviantart.net/0be2/f/2015/121/0/e/coyote_rocket_by_mreiof-d5va4sl.jpg" />
    <p>$189.99</p>
    <input type="submit" value="Buy Now" />
  </body>
</html>
```

Again, verify the page in your browser and then commit your changes.

```
cd Documents/projects/acme
git add products/rocket.html
git commit -m "Update the Rocket page"
```

The output should look like:

```
student@Rad-VM MINGW64 ~/Documents/projects/acme (master)
$ git add products/rocket.html

student@Rad-VM MINGW64 ~/Documents/projects/acme (master)
$ git commit -m "Update the Rocket page"
[master 2dc5fac] Update the Rocket page
1 file changed, 14 insertions(+), 3 deletions(-)
rewrite products/rocket.html (89%)
```

#### Push to GitHub

At this point your changes are in your local repository but not yet in GitHub. Compare the output of `git log` with what you see in [https://github.com/yourusername/acme/commits/master](https://github.com/yourusername/acme/commits/master)

Run:

```
git push origin master
```

Output:

```
$ git push origin master
Counting objects: 11, done.
Compressing objects: 100% (11/11), done.
Writing objects: 100% (11/11), 1.66 KiB | 0 bytes/s, done.
Total 11 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/radamanthus/acme.git
   c3b32fd..2dc5fac  master -> master
```

After running `git push`, what do you see in [https://github.com/yourusername/acme/commits/master](https://github.com/yourusername/acme/commits/master)?

#### Add another product page

The Marketing department asks you to add a new product to the web site.

Inside your project directory, create the page for the new product in `products/rocket-skates.html`.

```
<html>
  <head>
    <title>ACME Rocket Skates by ACME Corporation</title>
  </head>
  <body>
    <h1>ACME Rocket Skates</h1>
    <p>Catch your prey using these rocket-powered roller skates</p>
    <p><a href="../index.html">[Back to Home Page]</a></p>
    <hr />
    <img src="https://camo.githubusercontent.com/3898f52da67c9e11ef12be75f2b3dfbc31f70f6a/68747470733a2f2f6970762e73782f726f636b65742d736b617465732f726f636b65742d736b617465732e706e67" />
    <p>$149.99</p>
    <input type="submit" value="Buy Now" />
  </body>
</html>
```

Modify the list of products in `index.html` and add a link to the Rocket Stakes page.

HINT: Add `<li><a href="products/rocket-skates.html">ACME Rocket Skates</a></li>` inside the `<ul>` block:

```
    <p>Our latest products:</p>
    <ul>
      <li><a href="products/giant-rubber-band.html">ACME Giant Rubber Band</a></li>
      <li><a href="products/rocket.html">ACME Rocket</a></li>
    </ul>
```

Run `git status`. How many files were modified? How many files are untracked? 

Verify that only one line was modified in `index.html`. Run `git diff index.html`.

Commit your changes and push to GitHub.

```
git add index.html
git add products/rocket-skates.html
git commit -m "Add the Rocket Skates page"
git push origin master
```

#### Revert to the previous version

Breaking News! We received reports from field testers that the Rocket Skates product is unsafe to use.

<img src="https://i.ytimg.com/vi/S2VXOd3uXh8/hqdefault.jpg">

The Marketing department asked you to remove the Rocket Skates page from the web site.

Fortunately that was the last change you did, so all you have to do is revert it.

Run `git log` to get the commit hash of your most recent commit, then run `git revert [commit hash]`.

TIP: On the Git Bash terminal, you can double-click a word to select it. Then right-click and select "Copy" from the pop-up menu.

You will see an edit screen like this:

```
Revert "Add the Rocket Skates page"

This reverts commit [commit hash]

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Your branch is up-to-date with 'origin/master'
#
# Changes to be committed:
#       modified:   index.html
#       deleted:    products/rocket-skates.html
```

This is a `vi` editor for editing the revert message. Leave everything as-is, and press ESC, then type `:wq` (shorthand for "save changes, then quit").

Check the products directory. Is the rocket-skates.html file still there? 

Check the index.html file. Do you still see the reference to the Rocket Skates page in the products list?


### Wrap Up

These are the git commands you used in this workshop:

git init

git remote add

git push

git clone

git add

git commit

git revert

Go to the [Git documentation home page](https://git-scm.com/docs) and read the documentation for each of the above commands.
