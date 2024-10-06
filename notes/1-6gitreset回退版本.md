git reset 可以回退到之前的某种状态
    模式1
        git reset --soft
    模式2
        git reset --hard
    模式3
        git reset --mixed


查看工作区
ls
查看暂存区
git ls-files

git log --oneline 查看版本信息
git reset --soft 676c88d 回退到制定的版本

回退到上一个版本git reset --hard HEAD^
slociv@gg ~/D/repo-hard (master)> git reset --hard HEAD^
HEAD 现在位于 676c88d 2
使用git reset --hard HEAD^ 之后工作区和暂存区的file3.txt都会被清空。如下所示
slociv@gg ~/D/repo-hard (master)> ls
file1.txt  file2.txt
slociv@gg ~/D/repo-hard (master)> git ls-files
file1.txt
file2.txt

git reset --mixed 工作区有，暂存区没有

slociv@gg ~/Downloads> cd repo-mixed/
slociv@gg ~/D/repo-mixed (master)> ls
file1.txt  file2.txt  file3.txt
slociv@gg ~/D/repo-mixed (master)> git reset HEAD^
slociv@gg ~/D/repo-mixed (master)> git log --oneline
676c88d (HEAD -> master) 2
6f06b9b 1
slociv@gg ~/D/repo-mixed (master)> ls
file1.txt  file2.txt  file3.txt
slociv@gg ~/D/repo-mixed (master)> cat file3.txt 
3
slociv@gg ~/D/repo-mixed (master)> git ls-files 
file1.txt
file2.txt

git reflog  所有操作都是可以回溯的
git reset --hard b294003d`