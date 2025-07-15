This article is a brief summary of my git and version control setup and understanding today in class. Our instructor, Mr Bankat did justice to all we need to know as newbies in our getting started with git. But before then let's look at some terminologies.

1. What is Version Control?

Version control is a system that records changes made to files over time, so you can track modifications, revert to previous versions, and collaborate with others without losing progress.

2. Importance of Version Control

It helps manage project history.

It enables collaboration on code with multiple people.

It allows you to revert to previous versions if something breaks.

It supports experimentation with new features safely.

It helps in display the head and branches in a project.

3. What is Git?
   Git is a distributed version control system used to track changes in code and collaborate with others. It runs locally on your computer and allows you to manage project versions efficiently.

4. What is Git?
   Git is a distributed version control system used to track changes in code and collaborate with others. It runs locally on your computer and allows you to manage project versions efficiently.
   It can also be seen as a type of version control that helps store our files remotely.

5. Difference Between Git and GitHub

Git GitHub  
 A tool installed locally to manage version control. An online platform to host and share Git repositories.  
 Works offline. Requires internet access.  
 Manages code history. Enables collaboration, pull requests, and project management.

6. Git and GitHub Setup for Beginners (Ubuntu)
   Using SSH with GitHub makes authentication more secure and convenient. Here’s how I set it up:

Step 1: Install Git

```
sudo apt update  
sudo apt install git
```
Step 2: Create a GitHub account

Go to https://github.com and sign up.

Step 3: Configure Git with your identity

```
git config --global user.name "Your Name"  
git config --global user.email you@example.com
```

Step 4: Generate SSH Key
This creates a public and private SSH key pair.
```
ssh-keygen -t ed25519 -C "you@example.com"
```
Press Enter to accept the default file location. Then enter a passphrase or leave it blank.

Step 5: Add SSH Key to the SSH Agent
```
eval "$(ssh-agent -s)"  
ssh-add ~/.ssh/id_ed25519
```
Step 6: Add Your SSH Key to GitHub
Copy your public key:
```
cat ~/.ssh/id_ed25519.pub
```
Go to GitHub:

Click your profile → Settings → SSH and GPG keys → New SSH key

Paste the copied key and save.

Step 7: Test SSH Connection with GitHub
```
ssh -T git@github.com
```
Step 8: Create a New Repository on GitHub
Go to GitHub → New Repository → name it and create.

Step 9: Initialize Git in Your Project Directory

```
cd your-project-folder  
git init
```
Step 10: Link Local Folder to GitHub Using SSH URL
Get your SSH URL from GitHub (it looks like git@github.com:username/repo.git), then:

```
git remote add origin git@github.com:username/repo.git
```
Step 11: Add, Commit, and Push Code

```
git add .  
git commit -m "Initial commit"  
git branch -M main  
git push -u origin main
```


Now your project is securely connected to GitHub using SSH!
