# gitredux
###This project is nascent and in a state of flux!

I started this project because `git log --no-pager` gives an error. Apparently I wanted `git --no-pager log`. This was the last straw.
*So I decided to "fix" the git CLI.*

This project takes inspiration from [gitless](http://gitless.com/) and [legit](https://github.com/kennethreitz/legit), and is
influenced by this [blog post](http://www.saintsjd.com/2012/01/a-better-ui-for-git/) and this [fantastic diatribe](http://stevebennett.me/2012/02/24/10-things-i-hate-about-git).
However, I feel all of these tools are either underdeveloped or too opinionated. I want a tool that gives me all the
same control as git but without the headache of its impossible to remember commands.

### Goals
* CONSISTANCY
* Fewer, more orthogonal commands
* More useful built-in behaviors

### Commands
(bound to get out of date quickly)

get | git
------------- | -------------
get stage | git add -u :/
get stage %FILES% | git add %FILES%
get unstage | git reset HEAD
get unstage %FILES% | git reset HEAD %FILES%
get reset | git checkout -f HEAD
get reset %FILES% | git checkout %FILES%
get commit %MESSAGE% | git commit -m %MESSAGE%
get branch %BRANCH% | stashes working tree, creates or switches branch, and checks out branch
get rmbranch %BRANCH% | git branch -d %BRANCH% *TODO: rename?*
get fetch | Fetches all remotes and fast-forwards local branches when possible
get status | git status
get review | git diff --cached
get diff | compare working tree with HEAD (git diff HEAD)
get diff STAGE | compare working tree with stage (git diff)
get diff %REF% | compare working tree with %REF% (git diff %REF%)
get diff STAGE %REF% | compare stage with %REF% (git diff --cached %REF%)
get diff %REFA% %REFB% | compare %REFA% with %REFB% (git diff %REFA% %REFB%)

### TODO
Now that I've added tab completion, I think "stage" and "status" are too similar.
Also, I have three commands that start with "r" which is a problem.

### Changelog
- I renamed "update" to "fetch" to avoid completion conflicts with "unstage".
Also, it really is just fetch + fast-forward. One of my goals is NOT to use
different terminology than git, because that makes StackOverflow less useful.
