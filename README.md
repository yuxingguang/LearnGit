# LearnGit
# everyone like git
理解git中的HEAD指向问题:
1.既然切换分支前需要提交当前分支,那么使用git checkout -b <new_branck> , 即使当前工作区/暂存区有修改,但还是可以在新老分支之间自由切换
 回答:首先切换分支只是HEAD指针在动,所以创建并切换到新分支,HEAD指向了新分支,但新分支指向的commit object没有变;并且新老分支工作区/暂存区变化,
     并不会改动commit object,只有commit操作才会影响commit object.
2.如何理解切换分支前必须提交当前分支
因为切换分支时,分支名和HEAD一样也是指针,并且指向的也都是commit object(其实HEAD指向的是分支名),假设不提交当前分支就切换,那分支名指向的就不一定是
一个commit object,所以可以理解stash其实相当于伪commit object
3.合并分为两类(faster-forward和公共祖先合并)
