CA1– Version Control Assignment


Part 1: Working on Main Branch 


1.Clone and Set Up the Repository

First, I created a new folder called CA1 inside my Projects directory and cloned the Spring PetClinic repository into it.
After cloning, I removed the original .git folder and reinitialized Git to start my own repository.
Then I added the project and made my first commit.

![imgg1 1](https://github.com/user-attachments/assets/cf549a30-6757-4011-bf1e-01dc0bd2280c)

This created version 1.1.0, marking the initial state of the app.


2.Add a New Field to the Vet Class

I added a new field called professionalLicenseNumber to the Vet.java file, updated the database schema, and added support for it in the HTML templates and data files.

Vet.java – new field, getter, and setter
![imgg1 2](https://github.com/user-attachments/assets/261358b9-49ca-4855-81f6-6434da13f3d6)

SQL schema and data updates
![imgg1 3](https://github.com/user-attachments/assets/fc3983f3-b8c8-4cd6-9c9a-394313b3f371)
![imgg1 4](https://github.com/user-attachments/assets/8753b1f5-9309-458d-8e2f-5b6c59dad73c)

VetList.html
![imgg1 5](https://github.com/user-attachments/assets/f4a719fd-8b44-47c6-a067-97a6cc23f18e)

After implementing and testing, I committed and tagged this version:
![imgg1 6](https://github.com/user-attachments/assets/59e2b4a0-7128-44b0-a9ab-3cbfa3ac3810)


4.View commit history with different git log formats

I explored git log with several useful options to customize the output:
![imgg1 7](https://github.com/user-attachments/assets/867c8e46-1920-4259-8b95-2e5b1c2f4516)


What I looked for:

-oneline: quick overview of the history
-graph: branches and merges drawn in the terminal
-decorate: shows where HEAD, origin/main, and tags are
-pretty=format: colors and fields (hash %h, relative date %cr, author %an, message %s)

4.Reverting Changes

Next, I had to revert a commit (08f9e36) that normalized line endings

![imgg1 8](https://github.com/user-attachments/assets/e8c86f16-7aa7-44da-afd8-36291127cacc)
![imgg1 9](https://github.com/user-attachments/assets/d221a723-5192-4bbf-9f82-5242dd4c2818)

Then I used different commands to explore my repository details and be able to view latest commit and show how many distinct contributors made commits
![imgg1 10](https://github.com/user-attachments/assets/0938f81a-b037-4f82-a938-bccac6811b0c)


At the end of Part 1, I created a tag to mark the completion:

![imgg1 11](https://github.com/user-attachments/assets/5e6919ea-cffa-41ca-837b-449a6ea40025)


Part 2: Working with Branches

1️.Create Feature Branch (Email Field)

Following the Git workflow, I created a new branch named email-field and added a new field for the veterinarian’s email address

![imgg1 12](https://github.com/user-attachments/assets/4aec2c0b-760f-4918-91ac-3135016c51b9)

I updated Vet.java to include email,schema.sql and data.sql and vetList.html to display emails

After verifying it worked (by running on localhost and seeing the new email column in the web app):

![imgg1 13](https://github.com/user-attachments/assets/33dfa187-172f-4623-808f-9e4a4435be24)


I committed and merged the feature back into main afterwards

![imgg1 14](https://github.com/user-attachments/assets/7433bc2f-39db-4a51-bb5e-aafaba46009f)

2.Create and Resolve Merge Conflicts

I created two new branches (feature-A and feature-B) and made conflicting edits to the same line in Vet.java.

![imgg1 15](https://github.com/user-attachments/assets/3dc209df-35fd-4b0e-92fe-0e122a35a4fb)


When merging feature-A and feature-B back into main, Git reported a merge conflict:

![imgg1 16](https://github.com/user-attachments/assets/d847755e-d0a4-4a41-91af-2dd2f84eac97)
![imgg1 17](https://github.com/user-attachments/assets/a8fe9746-9d35-4157-a45f-0cf58e9e3330)

I manually resolved the conflict in VS Code by combining both comments:

![imgg1 18](https://github.com/user-attachments/assets/4973a4da-fb15-4ff2-9f51-1c36d7522f59)

Then I staged and committed the resolved file:

![imgg1 19](https://github.com/user-attachments/assets/903f9302-1bab-4e7c-889e-ff723358c66e)

Finally, I tagged this as the completion of Part 2:

![imgg1 20](https://github.com/user-attachments/assets/fe723d0f-aa53-4d02-bd1b-41b170f59665)



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

