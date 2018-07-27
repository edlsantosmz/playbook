# GIT ESSENTIAL TRAINING
## Getting Started
### Performing your first commit


```
git add .
git commit -m "<comment>"
```

Git process
* Make changes
* Add changes
* Commit changes to the repository with a message

### Writing commit mesages 

What you really want to do is have a commit message that describes the changes that you're making in that commit set, so added file to project, that would be more descriptive saying that we added this first file. We are labeling what we were doing in this change set so when we come back and look at it later, we can just look at the commit message and know what's inside, what's contained in that set.

Commit message best practices
* short single-line summary, less than 50 characters
* Optionally, we can follow that by a blank line and then a more complete description
* keep those additional lines to less than 72 characters
* write commit messages in the present tense, not in the past tense, you are labeling what this commit does, not what you--as the creator--were doing. Label what it does. This fixes a bug, not I fixed a bug. It's not about you, it's about what this commit is.
*  bullet points that describe what happens you usually use asterisk or hyphens
* Add ticket tracking numbers from bugs or support requests or develop a shorthand for your organization
* Can develop shorthand for your organization
** "[cs,js]"
** "bugfix:"
** "#8981 - " 

Label

* Be clear and descriptive
** Bad: "Fix typo"
** Good: "Add missing > in project section of HTML" 
** Bad: "Update Login code"
** Good: "Change user authentication to use Blowfish"

Example
```
t23094 - Fixes bug in admin logout.

When an admin logged out of the admin area, they could not log in to the members area because their session :user_id was still set to the admin ID. This patch fixes the bug by setting session :user_id to nil when any user logs out of any area.
```

`Notice that it describes what the problem was and then describes what the solution was as well.``

### Viewing the commit log
```
git log
commit f247c20fe52a6fb0acf1d2773cb7b6699058461c (HEAD -> master)
Author: Eduardo <eduardos@spotify.com>
Date:   Fri Jul 27 21:57:21 2018 +0200

    Initial commit
```
Where
* commit: unique ID
* author: pulled from the global configuration

`git help log`

See number of commits
`git log -n <number>`

See commits in a specific period of time
```
git log --since=YY-MM-DD
git log --until=YY-MM-DD
git log --author="<name>"
```

Regular eexpression search in the commit message
`git log --grep="<regex-string>"`

## Git concepts and architecture
### Exploring the three-trees architecture


* Working copy: where we have our changes that we've made, and we've saved, and saved to our hard drive, but we have not yet committed them to the repository, we haven't told Git to make this a changed set and to track it.
* Staging index, which is where we prepare things, we stage them for the commit, and then after they've been staged, we commit them to the repository so that they are permanently tracked and they now have a commit message attached to them.








