**i have a feature branch to be merged but pull request was not merged to main**

**yet i created another feature branch and  and created one other files** 

**added it to staging and then commited - i wanted to create  feature branch on remote same that i created earlier and added files** 

**but instead of running the command**

**git push --set-upstream origin May12**

**I ran this command** 

**git push origin --set-upstream May12**



\---------------------------------------

Your command order is slightly different, but it still works the same way.



These two commands are equivalent:



```bash

**git push --set-upstream origin May12**

```



and



```bash

**git push origin --set-upstream May12**

```



Both mean:



\* push local branch `May12`

\* create remote branch `origin/May12`

\* set upstream tracking



So you likely did \*\*not make a mistake\*\*.



You can verify with:



```bash

git branch -vv

```



or



```bash

git status

```



You should see something like:



```bash

On branch May12

Your branch is up to date with 'origin/May12'

```



To check remote branches:



```bash

git branch -r

```



You should see:



```bash

origin/May12

```



Your earlier branch (`May02`) and its PR are unaffected unless you explicitly merged or rebased them.



\-------------------------------------------------------------------------------------------

**# but 2 files that I created in this branch are not visible** 

\----------------------------------------------------------------------



That usually means one of these happened:



1\. files were not committed

2\. commit was made on another branch

3\. push did not include the latest commit



Run these commands one by one and check the output.



\### 1. Verify current branch



```bash id="7m1z8l"

git branch

```



The active branch will have `\*` beside it.



Example:



```bash id="f3a6oo"

\* May12

&#x20; main

&#x20; May02

```



\---



\### 2. Check whether files are committed



```bash id="xqg0kq"

git status

```



If you see:



```bash id="grq8r1"

nothing to commit, working tree clean

```



then files are already committed.



If files appear under:



```bash id="8m8m9m"

Changes not staged

```



or



```bash id="3wbh4j"

Untracked files

```



then they were never committed.



\---



\### 3. Check latest commits



```bash id="mgh6zw"

git log --oneline -5

```



See whether your commit message exists.



\---



\### 4. Push latest commit again



```bash id="f9m1oo"

git push

```



Since upstream is already set, this is enough.



\---



\### 5. Verify files on remote branch



Fetch latest refs:



```bash id="q7p77w"

git fetch

```



Then compare:



```bash id="5n56pq"

git diff origin/May12

```



If nothing appears, local and remote are same.



\---



Most likely scenario:

You created files, staged them, but commit happened on another branch (often `May02` or `main`).



To confirm:



```bash id="6q6f49"

git log --all --decorate --oneline --graph

```



This shows which branch contains your commit.

\----------------------------------------------------------



&#x20;**a26521d (main) Coding done for Day12**

**| \* 217cb87 (origin/May11, May11)  Day11 Coding done**

**|/**  

**\*   53b7576 (HEAD -> May12, origin/main, origin/May12) Merge pull request #7 from fahad1785/May10**

**|\\**  

**| \* 4b3fec3 Day10 coding practice done**

**|/**  

**\*   ad4d419 Merge pull request #6 from fahad1785/May09**

**|\\**  

**| \* 088cd72 Practiced Day02 coding**

**| \* fed1e42 practiced day01 coding pushing to May09 branch**

**| \* 0a81ce6 Day09 practice done**

**| \* 9f8c9c2 practices remaining code day08**

**|/**  

**\* fd7f314 Day08 practice**

**\*   e1fa014 Merge pull request #3 from fahad1785/May07**

**|\\**  

**| \* a0d0898 practiced coding \& pushing to May07 branch**



\----------------------------------------------------------------------



From your log:



```bash id="q2k7wq"

a26521d (main) Coding done for Day12

```



This is the important line.



Your latest commit (`a26521d`) exists on `main`, NOT on `May12`.



Current situation:



\* `HEAD -> May12` is still at old commit `53b7576`

\* your Day12 files were committed into `main`

\* therefore `origin/May12` does not contain those files



That’s why the 2 files are not visible in the `May12` branch.



You now have 2 options.



\# Recommended Fix



Move the Day12 commit from `main` to `May12`.



\## Step 1 — Switch to May12



```bash id="v3msh3"

git checkout May12

```



**## Step 2 — Cherry-pick the Day12 commit**



```bash id="k9f4f4"

git cherry-pick a26521d

```



This copies the commit into `May12`.



\## Step 3 — Push updated branch



```bash id="w83k66"

git push

```



Now your files will appear in remote `May12`.



\---



\# Optional Cleanup



Currently local `main` has an extra commit not present in `origin/main`.



You can remove it from local main later.



After successfully pushing `May12`:



```bash id="73v4qq"

git checkout main

git reset --hard origin/main

```



This resets local `main` back to remote state.



Do this only after cherry-pick succeeds.





