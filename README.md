# Sample Project for Learning jsp and servlet Web Development

This project is a working "stub" application for learners to use to get 
started.  

## To use this stub

1. Fork this project on github.com, so you have your own copy.
Look for the Fork button in the upper right of the web page.
2. In mid-page, or the lower right, find the "SSH" or "HTTP" button
next to a URL, with a "Copy to Clipboard" button next to it.
3. Push "Copy to Clipboard"
4. In a terminal window (mac) or git-bash (windows), `cd` to
change directory to the folder where you want your project to appear.
5. Then run git clone (paste) (Notice your username in that address - not mine!) :

     `git clone git@github.com:yourusername/codergirl-project-stub.git`


## How do I rename this project to something like web-pet-store?

You've already done a fork and clone.  You have a copy of the code.  But the project name
isn't to your liking, and you'd like to separate from my git naming entirely.  How do you
do it?

### Step 1: Renaming
1. Exit Eclipse.  You don't want this open while you fix things.
2. Navigate to the folder `codergirl-project-stub` using the folder explorer (windows) or finder (mac).
3. Delete the .git directory - this will make it "forget" the history of the project and disconnect
it from github.
4. Rename the codergirl-project-stub directory to your project name.
5. Use a text editor (sublime, wordpad, whatever) to modify the `.project` file and the `pom.xml` file,
to change the name inside there.  The names appear multiple times in each file; any place you see `codergirl-project-stub` you
should replace that with your project name. Save your changes.
6. Open the `.settings/org.eclipse.wst.common.component` file and change the name in there. Save your changes.
7. Get a command prompt (terminal on mac, git-bash on windows) and change directory into your project dir.
8. Type: `mvn package` and make sure it succeeds at compiling.

### Step 2: Eclipse Import

1. Open Eclipse.
2. File menu > Import > From existing workspace > Browse to your project folder and click Open.  It should
recognize the project and have a checkbox next to it in the white dialog box in the middle of the wizard.
3. Tell it ok, and your project should be listed on the left in Eclipse; after a minute, any compile errors
should go away.

### Step 3: Back to Github with a new name

1. In terminal or git-bash, change directory into your project dir (you might already be there).
2. Type and run: `git init`
3. Type and run: `git add --all .`
4. Type and run: `git commit -m "Changed project name"`
5. Go to your web browser, and go to github.com
6. Go to Repositories for your user
7. Create New Repository
8. Give it a name to match your project name
9. DO NOT add a readme or a license file.  Click ok.
10. Look at the info on the web browser.  It will have a section like "…or create a new repository on the command line".
This contains some commands for you to run (but you've already done some of them).  Look for the one with `git remote add origin`
and copy-paste that into git bash to run it.  It's already customized with your project name.
11. Type and run: `git push -u origin master`
12. Type and run: `git push --set-upstream origin master`
13. Refresh the page in your web browser and you should be able to see your code.
14. Go back to Eclipse and right-click the project, choose Refresh, and the icons should change to indicate git success.

You're done!  You now have an empty project with your preferred name.


## What does development workflow look like?

You will create servlets in `src/main/java/your.package.name/` and jsps in `src/main/webapps/*.jsp` (or
optionally in folders within that).  

You will start jetty running, 

    test/main/java/org.codergirl/Start.java (right click, Run as Java Application)

and then go to:

     http://localhost:8080/

in a web browser of your choosing.  As you modify servlets and jsps, jetty will automatically
pick up most changes, if you just reload the web page.  If it fails to pick up a change, you
can stop and restart jetty to see your change.  (Do make sure your code is compiling first; if
it's not recompiled, then jetty won't pick up the change.)

As you add new servlet urls, you may need to edit `web.xml` to match pretty urls with the
servlet classes that support them.

You may also wish to add Java classes that aren't servlets, but which instead help with 
database access, or represent data entities, or whatever.  You can create any packages
and classes you want within `src/main/java/` and they will be included in the web app.

You may also want to write unit tests; those go in `test/main/java/` instead.  Anything 
in `test/` is not available from jetty (except Start.java that runs jetty itself).  The
test folder is meant for unit tests that are only needed by the developer, not in a
running web app.

Periodically, as you finish a feature, you will want to save your progress:

     git add --all .
     git status
     git commit -m "Added feature blah blah blah" 
     git push

## So, what's in this project?

`src/main/java` - contains the Java code

`src/main/resources` - contains properties files when needed

`test/main/java` - contains the jetty Start application for local testing, and may contain unit tests.

`src/main/webapp/` - contains html content and jsps, plus the `WEB-INF/web.xml` file

`target/` - contains compiled code (excluded from git)

`pom.xml` - maven configuration file that controls what library dependencies are included

This project is modeled from https://github.com/jennybrown8/edu-java-jsp and uses the same project
layout and configuration.  Read its README for more details.

