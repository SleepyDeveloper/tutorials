Debugging Alexa Skills (AWS Lambda Code) Locally
======

# Who is this tutorial for?

This tutorial is for people who are tired of uploading a .zip file to their Lambda instance.

# Purpose

Set up local debugging for Alexa Skills.
Benefits:

* No need to upload .zip files to lambda each time you want to test locally
* Testing without talking to alexa (don't lose your voice debugging)
* Local access to `Amazon CloudWatch`


# Assumptions
* Exists
 * Your AWS account
 * Your Amazon Developer account
* installed software
  * NodeJS
  * Visual Studio Code
  * AWS Command Line Interface

# Steps

1. Set up testing files [YouTube](https://youtu.be/pKtSe-2HlZc)
  1. Add a test dir
  2. Install node modules
  3. Create test files.
2. Configure AWS [YouTube](https://youtu.be/aSk90ks5gfU)
  1. Create a group in IAM
  2. Attach Policies
  3. Create a user in IAM
  4. Add user to group
  5. Create a role
  6. Attach policies
  7. Trust user
3. Finalize testing environment [YouTube](https://youtu.be/IUpg-dbHuUE)
  1. Run `aws configure`
  2. Replace placeholders with your data
4. Configure and Debug [YouTube](https://youtu.be/xbjRRmw3d0k)
  1. Create `./.vscode/launch.json` file
  2. Set break points
  3. Debug it

Videos
====
##### 1. Set up testing files
---
[![YouTube link for step 1 set up testing files](http://img.youtube.com/vi/pKtSe-2HlZc/0.jpg)](https://youtu.be/pKtSe-2HlZc)

##### 2. Configure AWS
---
[![YouTube link for step 2 configure AWS](http://img.youtube.com/vi/aSk90ks5gfU/0.jpg)](https://youtu.be/aSk90ks5gfU)

##### 3. Finalize testing environment
---
[![YouTube link for step 3 Finalize testing environment](http://img.youtube.com/vi/IUpg-dbHuUE/0.jpg)](https://youtu.be/IUpg-dbHuUE)

##### 4. Configure and Debug
---
[![YouTube link for step 4 Configure and Debug](http://img.youtube.com/vi/xbjRRmw3d0k/0.jpg)](https://youtu.be/xbjRRmw3d0k)
