**How to setup a Jenkins production and testing pipeline using
docker??**

Assumptions: Jenkins And Docker are installed in RHEL OS

Jenkins is added in sudoers file.

User has a Github Profile and Git Bash is Installed

\#NOTE THIS Document is in 2 Parts for those who know how to use git can
directly skip to that

1\. Create a folder on your preferred place

2.Create a index.html file and write something in it .

![](./myMediaFolder/media/image1.png)

This is my Index.html file for testing

3.Open Git bash where your file is located

![](./myMediaFolder/media/image2.png)

4\. Create a git repository

![](./myMediaFolder/media/image3.png)

5.Paste the command on the git terminal you opened in previous step
(step 4)

6\. Now create development branch by typing:

Git branch development

![](./myMediaFolder/media/image4.png)

To check this branch type git checkout \<branch name\>

Here my branch name is developer

![](./myMediaFolder/media/image5.png)

Screen will look something like this

![](./myMediaFolder/media/image6.png)

7\. Edit the code in this branch

![](./myMediaFolder/media/image7.png)

8\. Add and commit the code

Git add .

Git commit -m "message"

Git checkout master

9\. Git push --all (this will push all branches into github)

![](./myMediaFolder/media/image8.png)

**FOR THOSE WHO KNOW THE ABOVE BASICS**

**PART 2**

Now we need to setup Jenkins for the job

Fire up Jenkins

I will be doing the this task in 4 Steps

Step 1:

Create Job1 with following configuration

![](./myMediaFolder/media/image9.png)

![](./myMediaFolder/media/image10.png)

![](./myMediaFolder/media/image11.png)

Save the job

STEP 2:

Create another job for production server

![](./myMediaFolder/media/image9.png)
![](./myMediaFolder/media/image12.png)
![](./myMediaFolder/media/image13.png)

Save the job

STEP 3

For Development Environment

Create a job name gitup-test.

***\#NOTE REPLACE the master with your development branch below.***

![](./myMediaFolder/media/image9.png)

![](./myMediaFolder/media/image10.png)

![](./myMediaFolder/media/image14.png)

Step 4

Create a job QA-approved

Don't forget to give your credentials here

![](./myMediaFolder/media/image15.png)

\# go to post build section

![](./myMediaFolder/media/image16.png)

![](./myMediaFolder/media/image17.png)

KUDOS YOU ACHIEVED IT

This is how the index page in production looks like

![](./myMediaFolder/media/image18.png)

This is what development server looks like

![](./myMediaFolder/media/image19.png)

Once the QA team test the code they will start the QA-test job white we
configured at PART2: STEP 4

![](./myMediaFolder/media/image20.png)

This will update the Ip , you can also do the jobs using HOOKS

This is what Docker looks like after this process

![](./myMediaFolder/media/image21.png)
