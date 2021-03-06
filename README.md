# Android Studio Git Basic Tutorial

## Git Clone

To clone a Git project using Android Studio, go to **VCS** > **Checkout from Version Control** > **Git**

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc822k446cj30ez0ef76g.jpg)

## Git Add

To add newly created files to the git commit, open the **Version Control** tab (Cmd + 9), select any files in the **Unversioned files** changelist and select **Add to VCS** (Option + Cmd + A)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc8256xyh5j30bq08tjse.jpg)

## Git Commit

To commit files in the current changelist, open the **Version Control** tab (Cmd + 9), press the **Commit** button (Cmd + K), give a commit message and press **Commit**.

**PRO TIP**: Play with the checkboxes and select what is best for you. It can save a lot time that your teammates would end up using by writing trivial PR comments.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc82c28ijgj30m40moq60.jpg)

## Git Pull

To pull the any changes made in the branch, select **VCS** > **Update Project** (Cmd + T)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc82m1yld6j30an059wfa.jpg)

## Git Commit — Amend

To add more changes to the previous commit, you can follow the same process as a new commit, but checking the box to amend the commit. 

**PRO TIP**: If the previous commit had already been pushed before, you will need to **force-push** your amended commit. Force pushing means that git will replace whatever is in the remote with your changes, which can be dangerous if you are not the only one using the given branch. It's fine as long as you know what you're doing.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc82rpy4hpj30ko0amta7.jpg)

## Git Push

To push your changes to the remote server, go to **VCS** > **Git** > **Push** (Cmd + Shift + K)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc82y1th1sj30j90duq72.jpg)

**PRO TIP:** After modifying history (rebasing, squashing, amending, etc) you will need to force push. You can do that by selecting the force push option in the push menu.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc837mmm2zj308k04cjrt.jpg)

**PRO TIP 2**: The master branch is protected from force push or interactive rebasing by default. You should probably keep it that way.

## Git Log

To see the history of commits, go to the **Version Control** tab (Cmd + 9), and select Log. You will see also some filtering options and advanced options when right clicking one particular commit.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc83dhkp99j309f07sq36.jpg)

## Git Rebase

In order to rebase a feature branch with the latest additions from the master branch (or any other branch) do:

1. Checkout the feature branch.

2. Access the Log functionality

3. Right click on the master branch, select **Branch 'master'** > **Rebase Current onto Selected**

   ![](https://tva1.sinaimg.cn/large/0082zybpgy1gc83l1tvepj30i408gq4h.jpg)

**PRO TIP**: The order of the branches is important. Make sure you are currently in the feature branch before executing the operation.

More information on rebase: <https://gyulajuhasz.com/blog/rebasing-in-android-studio/>

## Git Interactive Rebase

To freely modify the commit history, you can go to the **Version Control** > **Log** tab, right click a particular commit and select **Interactively Rebase from here**. There you will be able to select the action you want for each commit between the latest commit (**HEAD**) and the selected commit.

**PRO TIP**: Use this to rename a commit, or squash several commits into one.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc83sk5ze8j30b508u3ze.jpg)

## Git Cherry-Pick

In order to copy one particular commit from one branch into another, you can use cherry-pick. This option is also available by right-clicking the commit you want to cherry-pick and selecting **Cherry-pick** from the **Log** tab.

**PRO TIP**: Cherry-pick is very handy to copy specific commits from master to a particular release branch.

**PRO TIP 2**: Make sure you are in the feature (or release) branch before you cherry-pick.

 ![](https://tva1.sinaimg.cn/large/0082zybpgy1gc842eu0usj308a04cq3c.jpg)

## Solving Merge Conflicts

Once you pull from remote, or rebase into a different branch, **if you modified the same files**, git will complain and ask your help to fix the merge issues. Android Studio offers a great merge tool to fix any merge conflicts that may happen.

After the conflict is detected, AS will present this modal for you:

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc849ejo36j30i40gvjsx.jpg)

By double-cliking the conflicted file, you will see the issues, and a comparison between your version and the version on remote (or the other branch). Your version will be on the left side, the other version will be in the right side, and in the middle Android Studio will display the resulting file after the conflicts are solved.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc84c9xisrj31340pln22.jpg)

Every region marked in red represents a conflict identified. Click the double arrow symbol (**>>**) to copy the region to the resulting file or press **X** to discard a particular version. Once all the conflicts were processed, AS will display an option to **Save changes and finish merging**.

**PRO TIP**: You can also type in the middle (resulting) block to add any necessary logic to fix the merge. Sometimes that proves to be necessary.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc84g7zv1ij30g10blwgk.jpg)