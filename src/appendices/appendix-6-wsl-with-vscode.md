# Setting up Visual Studio Code and Git with WSL
> The contents in this section were migrated from the `vs-code.md`, `how-to-sync-github.md`, and `git-and-ssh-keys.md` files from the [IISD-ELA/github-documentation-files](https://github.com/IISD-ELA/github-documentation-files/tree/main/docs) repository.

&nbsp;&nbsp;&nbsp;Windows Subsystem for Linux (WSL) allows you to run a Linux environment directly on Windows. When combined with Visual Studio Code (VS Code), it provides a convenient way to develop and run code using Linux-based tools without needing a separate Linux computer.  

&nbsp;&nbsp;&nbsp;This setup is primarily intended for IISD-ELA Data Team members and other technical staff whose work requires a Linux development environment. Most staff do not need WSL to use Git, GitHub, or VS Code.

### 1. Get set up with WSL on VS Code

* Install the [WSL Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) and set up WSL in VS Code
    * It will open in Visual Studio Code, then click Install
    * Once it's done, close VS Code.
    * Open WSL
    * Note: if WSL was already open and you just installed Visual Studio Code, close it and then reopen!
    * We will install Visual Code Server on WSL with this line:
        * ```code .``` - where `.` is the current folder (you can provide a folder of your choice)
    * WSL will pop open VS Code
    * In the popup "Do you trust the authors of the files in this folder?" (for /home/chay [WSL: Ubuntu]) click the checkbox to "Trust the authors of all files in the parent folder 'home', then click "Yes, I trust the authors"
    * Now VS Code is open with the "Explorer" panel on the left at the home folder of your WSL: UBUNTU (Linux) location
        * For context, when we set up WSL, a native Linux partition is created and it is recommended to use that (and not the Windows partition) for development.
        * On Windows, you can navigate there in File Explorer - the folder path is something like `\\wsl.localhost\Ubuntu\home\chay`
        * On Linux (WSL) the same folder is located under `/home/chay`

### 2. Install Git on WSL
* Install GitHub on WSL
	* In WSL, type this command to install git:
		* ```sudo apt install git-all```
	* When asked "Do you want to continue?" type "Y" to continue
		* ```Y```

### 3. Add an SSH Key to your GitHub account so you can work easily in WSL
* _Background:_
	* _<small>It is proper, secure, and easier to use an SSH key for GitHub, so you can work in WSL (via VS Code) to update repositories instead of just using the browser to upload files. The GitHub documentation says to generate the SSH key in GitBash, but in our case it makes more sense and will work just as well in WSL.</small>_
* Create a new SSH Key
	* We will basically follow instructions from GitHub's Help Doc to [create an SSH key for GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
	* Open WSL if not open already. Enter the command below:
		* ```ssh-keygen -t ed25519 -C "your_email@example.com"```
		* (Replace the email above with the email address you use for your GitHub account)
	* When it asks you to enter the file in which to save the key, you can change the default that looks like `/home/chay/.ssh/id_ed25519` to a more meaningful name like `/home/chay/.ssh/github`
	* We will not set a password... so when it asks for your password and to repeat it, just press Enter (do this twice)
	* It should give you a randomart image (we can ignore this) and be completed (the key files will be in the location you specified).
	* Keep WSL open for later...
* Put the ssh public key into your GitHub account
	* Open your browser and log into GitHub
	* Navigate to Settings > SSH and GPG keys > New SSH Key (button)
	* Title: Chris' IISD-ELA Laptop (something like that)
		* (You want to put the name of the device that you are using the SSH key for. This is what will appear in your GitHub account)
	* Key type: "Authentication Key" (should be the default selection)
	* Key:
		* You must copy the public key from your WSL terminal window and paste into this section
			* Go back to WSL to get your public key via the following command
				* ```cat /home/chay/.ssh/github.pub```
				* It will spit out your public key contents (should be a line or two, starting with "ssh-ed25519..." and ending with your email) - copy that to your clipboard (highlight with cursor and Ctrl+C)
			* Paste the key into the "Key" box in the GitHub window in your browser
	* Click "Add SSH key" button
	* GitHub may ask you to "confirm access" by re-entering you GitHub password - do so and click "Confirm"
	* You should see the SSH key in your list of SSH keys now (in your GitHub settings)

### 4. Implement the SSH key in WSL
* _Background:_
	* _<small>Now we HAVE the SSH key, but we want to actually USE it. It's a pain to add it every time you use GitHub so we will use a trick. In Linux There's a ".bashrc" file in your home folder that is executed every time you start a session in WSL. When we add this ssh key to that file, it will get executed every time we start WSL.</small>_
* We will do this via VS Code
* On the left Explorer panel, assuming you are in your WSL home folder, click to open ".bashrc", then paste at the very end the following:

```	
parse_git_branch() {
git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "

eval $(ssh-agent -s)
ssh-add ~/.ssh/github
```

* But in that final line, change it to your ssh private key location! You will have this from our earlier steps. The final line should look something like this now:
	* ```ssh-add /home/chay/.ssh/github```
* Save the updated ".bashrc" file (Ctrl + S)
* Close WSL if you still had it open
* Re-open WSL and you should see a note at the start that looks something like this:
	* "Identity added: /home/chay/.ssh/github (your_github_email@example.com)"
* This means that now when you use WSL, you should be able to successfully use GitHub

### 5. Use version control with Git on WSL
* First **make sure you are in the root directory,** or at least a root-enough directory to include all your changes
  * If you're not at the root (repository folder), either:
    * Use `cd ..` to keep going up a level until you get there, OR
    * Use `cd data-mgmt-tools` (or whatever the root repo folder name is, after cd) to go straight to the root folder.
* Check if you are up to date with changes:
  * `git status` -> will show you what you changed, if anything, or if you are in sync

* Commit your changes:
  * `git add .` -> to add all changes to your commit (otherwise instead of a dot can specify your files - google it)
  * `git commit -m "name or message for your commit"` -> to prep the commit
* Pull: If your local branch is behind the remote branch, you'll first have to pull
  * You want to bring your local branch up to date, while keeping your changes so far.
  * `git pull --rebase origin master` downloads the commits from GitHub and then puts your local commits on top
* Push: Push your commit
  * `git push origin` -> to actually push the commit
  * `git status` -> should say you are in sync now

**Dealing with GitHub sync issues**  
* If you messed up syncing (e.g. I did this when trying to use the VS Code GUI) and you don't care about losing your changes, you just want GitHub to work so you can pull down the updates and go on fresh from there, you can either:
  * Reset head
    * Ctrl + C if you want to get out of anything you are currently in the middle of. 
    * `git fetch origin` → grabs the latest commits from GitHub.
    * `git reset --hard origin/master` → resets your local branch ("master" here; replace with "main" if that’s your branch name) to exactly match GitHub, discarding local commits/changes.
    * Optional (only if want to remove untracked files & directories, i.e. gitignored stuff): `git clean -fd`
    * Then do a `git status` to confirm it's all good again.
  * Or
  * stash, then pull
    * `git stash push -m "temp"`
    * `git pull --rebase origin master`
    * `git stash pop` brings your changes back - now you can keep working or do your commit and push
* OR use GitHub Desktop when trying to fix issues like this, if that's too complicated.
