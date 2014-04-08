Notes on Problems Getting Tools Working
========================================================

All of this relates to Mac OSX 10.9.2. 

### Problem with getting RStudio (0.98.501) to conect with GitHub account/repositories.

When I tried to PUSH data to GitHub from RStudio, i would get and error message:

error: unable to read askpass response from rpostback-askpass;
fatal: could not read Password for https://github.com/jeffmillard/datasciencecoursera: Device not configured

Workaround appears to be to switch from connecting over https to connecting over ssh (secure shell).  Somewhat easier than that probably makes it sound.

I ended up having to do the follwoing steps:

1. Remove connection to remote.  May not be necessary, may not be an accuracte description of what this command does.  But I did this first:  Go to the directory for the repository ("datasciencecoursera") and execute:

git remote rm origin


2. Delete my local copy of the repository.  I did this in terminal with the following command. Removing .git removes the saved versions of your files.  Deleting the files themselves does not!

rm -rf .git


3. Deleted Rstudio project file (used finder, couldn't see a way in RStudio to delete a project), directory, etc.

4. Using RStudio, 

File > New Project > From Version Control > Git

For the text box repository URL enter

git@github.com:yourgithubusernamehere/datasciencecoursera.git

Hopefully, it is obviuos that you replace yourgithubusernamehere with you GitHub user name.  If you are doing this for a repository other than datasciencecoursera, substitute that as well.

Note, thios used to be something like

https://github.com/yourgithubusernamehere/datasciencecoursera.git

Note, I had done this after generating a second SSH key.  That may be necessary to do first.
