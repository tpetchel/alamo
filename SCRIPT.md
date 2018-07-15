## Scenario

You want to capture the lyrics to _Deep in the Heart of Texas_ in this GitHub repo. You'll store the lyrics in a file named `lyrics.txt`.

You remember the first stanza, but forget the second. You'll open a GitHub issue to track the work. 

Two collaborators will offer different versions of the second stanza, which in the end will produce a merge conflict.

By the end, you'll resolve the merge conflict and the GitHub issue.

## Setup

1. Each participant should have a GitHub account, Git installed, and Git [set up for development](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup).
1. Each participant should have a text editor ready. I suggest Visual Studio Code.
1. Identify someone who will run the exercise. That person will walk the group through the steps below. We'll call this person PersonA.
1. Identify two people who will act as collaborators. We'll call these people PersonB and PersonC.
1. Ensure the `master` branch is reset such that `lyrics.txt` is an empty file.
1. Enure the repo has no active issues.
1. Have each person open a terminal or PowerShell window. If you have Git for Windows, I recommend you try Git Bash.
1. Move to a working directory to practice in, such as `/tmp` or `C:\Temp`.

## Steps

1. Have PersonA, PersonB, and PersonC each clone the repo.
    ```
    $ git clone https://github.com/tpetchel/alamo.git
    ```
1. Have PersonA create a branch to hold the initial lyrics. Here's an example.
    ```
    $ git checkout -b tp/lyrics
    ```
    `tp` are my initials. This is a common convention used to identify who created the branch. You can follow this if you like.
1. Have PersonA add these contents to `lyrics.txt`.
    ```
    The stars at night
    Are big and bright
    Deep in the heart of Texas
    ```
    PersonA isn't sure what the next stanza is. Have PersonA commit work, push it to GitHub, merge it, and ask for help.
1. Stage changes to `lyrics.txt`
    ```
    $ git add lyrics.txt
    ```
1. Commit staged changes to the current branch.
    ```
    $ git commit -m "First stanza"
    ```
    The `-m` argument is optional. If you omit it, you'll be prompted to enter a commit message through the default editor.
1. Push up your changes. Here's an example. Replace the branch name you see here with yours.
    ```
    $ git push origin tp/lyrics
    ```
1. From a browser, navigate to `https://github.com/tpetchel/alamo`. Create a Pull Request from your branch.
1. Merge the PR.
1. Create an issue with these contents.
    1. **Title**: Second stanza missing
    1. **Body**: Can someone help me fill in the second stanza? Thanks! :thumbsup:
1. Have PersonB and PersonC each fetch the latest `master`.
    ```
    $ git pull origin master
    ```
    Optionally, see how `lyrics.txt` has the first stanza.
1. Have PersonB create a branch. Here's an example.
    ```
    $ git checkout -b pb/second
    ```
1. Have PersonB add the second stanza to `lyrics.txt`, making the entire file look like this.
    ```
    The stars at night
    Are big and bright
    Deep in the heart of Texas
    
    The eagles fly
    Across the sky
    Deep in the heart of Texas
    ```
1. Have PersonB view, stage, commit, and push the changes. Here's an example.
    ```
    $ git diff
    $ git status
    $ git add lyrics.txt
    $ git commit -m "Second stanza"
    $ git push origin pb/second
    ```
1. Have PersonB create a PR and add a note to the issue. You can reference your PR like this example.
    > Added second stanza. Resolved by #2.
1. Have PersonA review the PR, merge it, and close the issue. Be sure to thank PersonB for their help! :star:
1. Let's say at the same time, PersonC was also working on the issue, not knowing about PersonB's work. Have PersonC create a branch. Here's an example.
    ```
    $ git checkout -b pc/second
    ```
1. Have PersonC add the second stanza to `lyrics.txt`, making the entire file look like this.
    ```
    The stars at night
    Are big and bright
    Deep in the heart of Texas
    
    The prairie sky
    Is wide and high
    Deep in the heart of Texas
    ```
1. Have PersonC view, stage, commit, and push the changes. Here's an example.
    ```
    $ git diff
    $ git status
    $ git add lyrics.txt
    $ git commit -m "Second stanza"
    $ git push origin pc/second
    ```
1. Have PersonC create a PR. Then have PersonC notice that the issue was resolved & closed. Have PersonC reopen the issue and a note. You can reference the owner to get their attention.
    > Hey, @tpetchel, I think the second stanza is incorrect. See corrected second stanza in #3.
1. Have PersonA review the PR and try to merge it. You'll discover that there's a merge conflict that prevents this from happening.
1. Have PersonA pull down PersonC's branch and resolve the merge conflict. 
1. Have PersonA push up the branch with the resolved conflict and merge it.
1. Have PersonA add a note to the issue, thank PersonC for their help, and close the issue. :star:
1. Rejoice.

## Discussion

What is PersonB did have the correct solution? What should you do with PersonC's Pull Request?