# Example Drops 8 Testing
This is a cloned version of the example-drops-8 project from Pantheon. For information on example-drops-8 see README.orig, the original readme from the project or visit https://github.com/pantheon-systems/example-drops-8-composer. Big thanks the pantheon people. You all rock and I'm really appreciating your platform.

## Why?
The intent is to modify this project in order to turn it into a self building project. 
## The Plan:
We will wrap everything we need into an install script that we will put here in the root directory. This install script will do the following:
    1. create a new git repo.
    2. create a new pantheon repo.
    3. register a webhook with the git repo to ping the pantheon repo everytime a push is made to the git repo.

We will also write a git script for the pantheon repo that when pinged by github it will:
    1. fetch the refs from github - look for changes to common config files like composer.json or package.json or asset files
    2. create a new temporary branch.
    3. pull the github master branch.
    4. compile all necessary build files based on #1
    5. checkout master and force a merge favoring the temporary branch changes
