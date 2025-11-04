CA1 – Version Control Assignment


Part 1 – Working on Main Branch 


1.Clone and Set Up the Repository

First, I created a new folder called CA1 inside my Projects directory and cloned the Spring PetClinic repository into it.
After cloning, I removed the original .git folder and reinitialized Git to start my own repository.
Then I added the project and made my first commit.

![alt text](<Imagine WhatsApp 2025-11-03 la 22.32.56_99254ae1.jpg>)

This created version 1.1.0, marking the initial state of the app.


2.Add a New Field to the Vet Class

I added a new field called professionalLicenseNumber to the Vet.java file, updated the database schema, and added support for it in the HTML templates and data files.

Vet.java – new field, getter, and setter

![alt text](<Imagine WhatsApp 2025-11-04 la 00.15.56_23c398ca.jpg>)

SQL schema and data updates
![alt text](<Imagine WhatsApp 2025-11-04 la 00.18.49_d39f0b81.jpg>)
![alt text](<Imagine WhatsApp 2025-11-04 la 00.32.21_4e460cd7.jpg>)

VetList.html

![alt text](<Imagine WhatsApp 2025-11-04 la 00.21.57_47031121.jpg>)


After implementing and testing, I committed and tagged this version:

![alt text](<Imagine WhatsApp 2025-11-04 la 00.48.01_dc1bbc6b.jpg>)


4.View commit history with different git log formats

I explored git log with several useful options to customize the output:

![alt text](<Imagine WhatsApp 2025-11-04 la 00.52.53_6c1b3389.jpg>)
What I looked for:

-oneline: quick overview of the history
-graph: branches and merges drawn in the terminal
-decorate: shows where HEAD, origin/main, and tags are
-pretty=format: colors and fields (hash %h, relative date %cr, author %an, message %s)

4.Reverting Changes

Next, I had to revert a commit (08f9e36) that normalized line endings

![alt text](<Imagine WhatsApp 2025-11-04 la 11.40.30_09694705.jpg>)
![alt text](<Imagine WhatsApp 2025-11-04 la 19.56.06_9bcbae4d.jpg>)


Then I used different commands to explore my repository details and be able to view latest commit and show how many distinct contributors made commits

![alt text](<Imagine WhatsApp 2025-11-04 la 19.56.30_e95bfd3f.jpg>)

At the end of Part 1, I created a tag to mark the completion:

![alt text](<Imagine WhatsApp 2025-11-04 la 11.47.20_d8130d3f.jpg>)


Part 2: Working with Branches

1️.Create Feature Branch (Email Field)

Following the Git workflow, I created a new branch named email-field and added a new field for the veterinarian’s email address

![alt text](<Imagine WhatsApp 2025-11-04 la 12.01.53_82c495f8.jpg>)

I updated Vet.java to include email,schema.sql and data.sql and vetList.html to display emails

After verifying it worked (by running on localhost and seeing the new email column in the web app):

![alt text](<Imagine WhatsApp 2025-11-04 la 12.49.26_888c785b.jpg>)


I committed and merged the feature back into main afterwards

![alt text](<Imagine WhatsApp 2025-11-04 la 12.52.45_3c9e9c25.jpg>)

2.Create and Resolve Merge Conflicts

I created two new branches (feature-A and feature-B) and made conflicting edits to the same line in Vet.java.

![alt text](<Imagine WhatsApp 2025-11-04 la 12.58.54_01877795.jpg>)


When merging feature-A and feature-B back into main, Git reported a merge conflict:

![alt text](<Imagine WhatsApp 2025-11-04 la 13.00.54_4b66c33d.jpg>)
![alt text](<Imagine WhatsApp 2025-11-04 la 13.04.24_946a5569.jpg>)


I manually resolved the conflict in VS Code by combining both comments:

![alt text](<Imagine WhatsApp 2025-11-04 la 13.01.44_6b485376.jpg>)


Then I staged and committed the resolved file:

![alt text](<Imagine WhatsApp 2025-11-04 la 13.06.54_63182e4e.jpg>)

Finally, I tagged this as the completion of Part 2:

![alt text](<Imagine WhatsApp 2025-11-04 la 13.08.50_8fa36599.jpg>)



Alternative Version Control Solutions

For the final part, I researched an alternative to Git: Apache Subversion (SVN).

Comparison: Git vs SVN
-Git is distributed while SVN is centralized
-In Git you can make local commits while in SVN you commit to the server
-Offline work is fully supported	in Git while in SVN is limited
-Branching and merging are lightweight and fast	in Git while in SVN they are heavier and slower.
-Speed in Git is very fast while in SVN	slower due to central server
-Collaboration is easier in Git while in SVN it	requires coordination with server

How SVN Could Be Used Here:
If I used SVN for this project then the PetClinic repository would live on a central SVN server and each student would check out the repository and make local changes.
To simulate branching, I’d use SVN’s directory-based branches (/branches/email-field).
After testing, I’d merge changes back into /trunk (main) and commit the resolved files.

While SVN is simpler for centralized control, Git provides better flexibility for collaboration, branching, and version tagging, so Git is a more modern and powerful choice for this assignment.

