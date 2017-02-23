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

# Steps

1. Set up testing files
  1. Add a test dir
  2. Install node modules
  3. Create test files.
2. Configure AWS
  1. Create a group in IAM
  2. Attach Policies
  3. Create a user in IAM
  4. Add user to group
  5. Create a role
  6. Attach policies
  7. Trust user
3. Add AWS keys
  * Run `aws configure`
4. Finalize test environment
  * Replace placeholders with your data
5. Configure Debugger
  1. Create `./.vscode/launch.json` file
  2. Set break points
  3. Debug it
