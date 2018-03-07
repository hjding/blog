#git底层命令plumbing
[TOC]

##使用步骤
1.保存修改了的文件的 blob
2.更新索引
3.创建 tree 对象
4.最后创建 commit 对象

##常用命令
|命令|说明|
|-|-|
|find .git/objects -type f|查找文件|
|echo 'version 1' > test.txt|创建一个新文件|
|git cat-file -p d670460b4b4aece5915caf5c68d12f560a9fe3e4|取回数据内容|
|git cat-file -p master^{tree}|最新提交指向的tree对象|
|git hash-object -w test.txt|把文件内容存储到数据库|
|git update-index --add --cacheinfo 100644 \<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;83baae61804e65cc73a7201a7252750c76066a30 test.txt|将test.txt文件的首个版本加入到一个新的暂存区域中|
|git write-tree|将暂存区域的内容写到一个tree对象|
|git read-tree --prefix=bak d8329fc1cc938780ffdd9f94e0d364e0ea74f579|将tree对象读到暂存区域，--prefix将一个已有的tree对象作为一个子tree读到暂存区域|

##参考资料
[Git-内部原理-底层命令和高层命令](https://git-scm.com/book/zh/v2/Git-内部原理-底层命令和高层命令)
[Git--底层原理](http://http://devsnow.net/2015/01/25/git-principle/)