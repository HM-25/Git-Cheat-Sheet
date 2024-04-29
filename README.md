cd # Git Manual

# Everyday Use

**Initialising Repositories**

git status => reports back the status of the current repository. 

git init => Initialises a new git repository, within the current directory! 
  DO NOT INIT A REPO INSIDE OF A REPO!

**Adding and Committing**

git add file1 file2 => add files to our commit
git add . => to add all changes to the commit at once.
Note: Check if files are added using git status command

git commit -m "message" => to commit changes, using our own message (to skip the text editor)

**Cloning Existing GitHub Repo**

Cloning GitHub Repos using Git

git clone <URL> => clones a repo into a current directory and initializes it as a git repository.

**Uploading Existing Project to GitHub**

Step 1: Create an empty repository on GitHub!

Step 2: Create a git repository on your local machine!

Step 3: Connect the 2 repos, using remote!
      
    Git Remote commands: 

    git remote -v => Lists all existing remotes in a repository.
    note: in the empty git repo we created there will be no output after we run this command, 
    because we still did not set up the remote!

    git remote add <name> <SSH> => command to create a new remote.
    note: standard name for remote is "origin"
    in <SSH> we paste the SSH key of our empty GitHub repo we want to connect.

Step 4: check if we made remote using git remote -v!

Step 5: Move all the files you want into the git repo we created, using mv command:
    Navigate to your website directory: Use the cd command to navigate to the directory where your website files are located.
    For example:

    cd /path/to/your/website/directory

    Move the files: Use the mv command to move all the files from your website directory to your local Git repository     directory.   For example, if your Git repository is located on your desktop, you can move the files like this:

    mv * /path/to/your/local/git/repo

    This command will move all files (excluding hidden files) from your website directory to your local Git repository directory.

    Verify the files: Navigate to your local Git repository directory and verify that the website files are there:

    cd /path/to/your/local/git/repo
    ls


# Installation Manual

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

**GitHub Configuration**

**SSH Config**

https://docs.github.com/en/authentication/connecting-to-github-with-ssh

ls -al ~/.ssh => checks all existing ssh keys on the machine (run it from the main terminal directory)

Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following.

    id_rsa.pub
    id_ecdsa.pub
    id_ed25519.pub

**Generating a new SSH key and adding it to the ssh-agent**

After you've checked for existing SSH keys, you can generate a new SSH key to use for authentication, then add it to the ssh-agent.

Open Terminal.

Paste the text below, replacing the email used in the example with your GitHub email address.

ssh-keygen -t ed25519 -C "your_email@example.com"

Note: If you are using a legacy system that doesn't support the Ed25519 algorithm, use:

 ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

 When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id_ALGORITHM with your custom key name.

At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases."

**Adding your SSH key to the ssh-agent**

Start the ssh-agent in the background.

eval "$(ssh-agent -s)" => to start the agent
> Agent pid 59566 => this should be output if successful

Add your SSH private key to the ssh-agent.

If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

ssh-add ~/.ssh/id_ed25519

**Adding a new SSH key to your GitHub account**

Add the SSH public key to your account on GitHub. : https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

Copy the SSH public key to your clipboard.

If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any new lines or whitespace.

cat ~/.ssh/id_ed25519.pub
Then select and copy the contents of the id_ed25519.pub file
displayed in the terminal to your clipboard

Now go to the GitHub account: 

In the upper-right corner of any page, click your profile photo, then click Settings.

In the "Access" section of the sidebar, click SSH and GPG keys.

Click New SSH key or Add SSH key.

In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".

Select the type of key, either authentication or signing. For more information about commit signing, see "About commit signature verification."

In the "Key" field, paste your public key.

Click Add SSH key.

If prompted, confirm access to your account on GitHub.



