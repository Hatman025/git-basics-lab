Git Fundamentals Assignment
A hands-on lab covering Git setup, the three-tree workflow (working directory, staging area, repository), and exploring commit history.
Setup
•	Installed Git and verified the version.
•	Configured user identity (name and email) so commits are properly attributed.
•	Created a git-basics-lab folder and initialized it as a Git repository.
Reflection — What happens on git init? Running the init command creates a hidden .git folder inside the directory. This folder is the actual repository: it holds the object database, refs, HEAD pointer, and config that Git uses to track history. The rest of the folder remains an ordinary working directory until files are added.
Part 1 — The Three Areas
1.	Created notes.txt with a single line and checked git status — Git reported it as an untracked file.
2.	Staged the file and checked status again — Git now reported it as a change to be committed.
3.	Committed the file with a descriptive message.
4.	Modified notes.txt by adding a second line, then checked status before staging — Git reported it as modified, not staged for commit.
Reflection — Untracked vs. Modified vs. Staged
•	Untracked: the file exists in the working directory but has never been added to Git, so it isn't part of the history yet.
•	Modified: a tracked file has changed since its last commit, but those changes haven't been staged.
•	Staged: the changes are marked and ready to be included in the next commit.
Git separates staging from committing so you can build a commit deliberately — choosing exactly which changes go together — rather than being forced to commit everything that's changed at once. This makes it possible to split unrelated changes into clean, logical commits.
Attempting to commit the step-7 change without staging first did nothing (Git had nothing staged to commit). Staging the file and committing again completed it properly.
Part 2 — Exploring History
•	Made three additional small, clearly-messaged commits to notes.txt.
•	Viewed the commit history using multiple formats (e.g., full log and a condensed one-line log).
•	Located the hash of the second commit and used it to inspect exactly what changed in that commit.
•	Compared the current working directory against the very first commit.
Reflection — Why hashes instead of sequential numbers?
Each commit hash is generated from the commit's content and metadata, so it uniquely identifies that exact snapshot — any change produces a different hash. Sequential numbers can't offer that guarantee and would collide constantly in a distributed setting where many people commit independently without a central authority assigning numbers. Hashes make Git's history decentralized, collaborative, and tamper-evident: anyone can verify a commit's integrity, and IDs stay globally unique without coordination.

