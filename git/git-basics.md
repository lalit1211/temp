

# 2. Setting Up Git
    - Installing Git (Linux, macOS, Windows)
    - Configuring Git (username, email, editor)

    ```git config --global user.name “[firstname lastname]”
        set a name that is identifiable for credit when review version history
    ```
    ```
    git config --global user.email “[valid-email]”
    set an email address that will be associated with each history marker
    ```
    ```
    git config --global --list
    Displays all globally configured Git settings stored in your system.
    ```



# 3. Basic Git Commands

    ```
    git init
    initialize an existing directory as a Git repository
    ```

    ```
    git clone <repository-url>
    Cloning a repository:retrieve an entire repository from a hosted location via URL
    ```


    ```
    git status
    Checking the status of the repository
    ```

    ```
    git add <file-with-extension> -> only single file
    git add . -> this will add all the changes to the staging area
    add a file as it looks now to your next commit (Adding files to the staging area)
    ```

    ```
    git reset [file]
    unstage a file while retaining the changes in working directory
    ```

    ```
    git commit -m “[descriptive message]”
    commit your staged content as a new commit with a message
    ```


## 4. Branching Basics

    ```
    git branch
    Lists all local branches in the repository.
    ```

    ```
    git branch -r	
    Lists all remote branches.
    ```

    ```
    git branch <branch-name>
    Creates a new branch with the given name.
    ```

    ```
    git checkout <branch-name>	
    Switches to the specified branch.
    ```

    ```
    git checkout -b <branch-name>	
    Creates a new branch and switches to it immediately.
    ```

    ```
    git checkout <branch-name>	
    Switches to the specified branch.
    ```

    ```
    git branch -d <branch-name>	
    Deletes the specified branch if it has been merged.
    ```

    ```
    git branch -D <branch-name>	
    Force deletes the specified branch, even if it hasn’t been merged.
    ```



## 5. Undoing Changes
```
> Undo Unstaged Changes (Working Directory)
```
    ```
    git checkout -- <file>	
    Discards changes in a specific file (before staging).
    ```

    ```
    git restore <file>	
    Alternative to checkout (recommended in newer Git versions).
    ```

    ```
    git restore .	
    Discards all unstaged changes in the working directory.
    ```



```
> Undo Staged Changes (Before Commit)
```
    ```
    git reset <file>	
    Unstages a specific file (keeps changes in working directory).
    ```

    ```
    git reset	
    Unstages all staged files.
    ```

    ```
    git restore --staged <file>	
    Another way to unstage a specific file.
    ```

```
> Undo a Commit (Before Pushing)
```
    ```
    git reset --soft <commit>	
    Moves to the specified commit but keeps changes staged (ready for commit).
    ```

    ```
    git reset --mixed <commit> (default)	
    Moves to the specified commit, unstages changes, but keeps them in the working directory.
    ```

    ```
    git reset --hard <commit>
    Moves to the specified commit and removes all changes (both staged and in the working directory).
    ```


```
> Undo a Commit (After Pushing)
```
    ```
    git revert <commit-hash>
    Creates a new commit that undoes a specific commit (safe for shared branches).
    ```

    ```
    git reset --hard <commit-hash>	
    Resets to a specific commit, removing all changes after it (not recommended if already pushed).
    ```

    ```
    git push --force	
    Forces changes to the remote repository (use with caution).
    ```

```
>  Undo Changes with Stash
```
    ```
    Git stash is used to temporarily save changes without committing them, allowing you to switch branches or work on something else without losing progress.
    ```