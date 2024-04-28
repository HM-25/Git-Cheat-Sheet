**Git Manual**

**Installation**

**Setting up user name**

git config user.name => Check what is the currently set user name.
git config --global user.name "User-Name" => Set up a new user name.
note: if there is an existing user name, there is no need to delete it, simply add a new one. 
note: use the same user name as the GitHub profile you will be using.

**Setting up email:**

git config user.email => Check what is the currently set email.
git config --global user.email email@example.com => Set up a new user name.
note: if there is an existing email, there is no need to delete it, simply add a new one. 
note: use the same email as the GitHub profile you will be using.

**Initialising Repositories**

git status => reports back the status of the current repository. 

git init => Initialises a new git repository, within the current directory! 
  DO NOT INIT A REPO INSIDE OF A REPO!

**Adding and Committing**

git add file1 file2 => add files to our commit
git add . => to add all changes to the commit at once.
Note: Check if files are added using git status command

git commit -m "message" => to commit changes, using our own message (to skip the text editor)

**GitHub**

**Cloning GitHub Repos using Git**

git clone <URL> => clones a repo into a current directory and initializes it as a repository.


**SSH Config**

https://docs.github.com/en/authentication/connecting-to-github-with-ssh

ls -al ~/.ssh => checks all existing ssh keys on the machine (run it from the main terminal directory)

Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following.

    id_rsa.pub
    id_ecdsa.pub
    id_ed25519.pub


Generating a new SSH key and adding it to the ssh-agent

After you've checked for existing SSH keys, you can generate a new SSH key to use for authentication, then add it to the ssh-agent.


