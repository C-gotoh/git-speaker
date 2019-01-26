# git-speaker
Watch a git repository and listen to recent commit messages


## Why?
When working together on a project in real-time, you may want to get notified automatically when someone has pushed a commit.

git-speaker parses your git history, extracts author and commit message information, and pipes it into espeak.


## Usage
Create another local clone of your git repo (to avoid interfering with your work).

    git clone <url> watching-repo

Enter this new repo start a watcher that periodically pulls from your upstream branch.
You need to set your copy to use ssh-authentification and have an ssh-agent running for this to work without additional user input.

    watch -n 5 git pull

Run *watchexec* to trigger git-speaker when the directory changes (updates were pulled).

You may want to add the git-speaker script to your $PATH instead of calling it by its full path.

    watchexec git-speaker

## Dependencies

* [watchexec](https://github.com/watchexec/watchexec)
* espeak
