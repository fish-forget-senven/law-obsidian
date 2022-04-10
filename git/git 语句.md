当然我们在github创建项目是免不了的，创建好了之后，我们要做的就是**把本地的文件夹和远程的这个刚建好的仓库关联起来**。首先，我们在本地的文件夹当中运行git init，在本地初始化一个git仓库。

```bash
git init
```

下面我们要做的就是关联本地的仓库和远程的仓库，并且把本地的仓库当中的内容push到远程去。为了做到这一点，我们运行git remote add origin命令**给本地的git仓库增加一个远程的源**，这里后面跟着的链接是我们刚才在github里创建好的仓库的地址。

```bash
git remote add origin git@github.com:moutsea/git-tutorial.git
```

由于这个git-tutorial是我们自己创建的，所以是没有问题的，如果add别人的repo可能会报错。添加完成之后我们需要拉取远程的改动，因为我们在创建repo的时候创建了一个readme文件，这也算是一个改动，我们需要把这个改动拉下来，和远程保持同步之后再推送更新。

记住这一点，我们**在push代码到远程之前，一定要先通过git pull和远程先保持同步之后再进行推送**。

但是我们直接git pull是不行的，会报错，因为虽然本地和远程关联起来了，但是**分支没有关联**，它根本不知道该去pull哪个分支。我们需要把本地的master分支关联远程的master分支，但是这又迎来一个新的问题。我们本地暂时还没有任何改动，这个master分支实际上是不存在的，所以我们需要先提交本地的文件到git仓库。

这里的两个命令很常规，首先是git add .这里的.表示**添加全部变更**，使用.的时候要小心，因为有时候不是所有文件都需要添加的。大家知道就好，细节我们以后再说。然后是git commit -m提交到git仓库，由于我们配置了alias，所以可以使用ci代替commit。-m是message的意思，后面需要传入一个字符串，表示这个改动的备注，方便以后查看。

注意这里的commit操作并不是提交到远程，而是提交到本地的git仓库。terminal当中会把git添加的文件名都输出出来，由于我用的是中文，所以出来的是乱码，不过这没有关系，至少我们add成功了。

之后我们用命令把本地的master和远程的master分支关联起来，其实也就是给本地的master分支添加一个上游：

```bash
git branch --set-upstream-to=origin/master master
```

现在一切都已经就绪了，按理说我们直接git pull之后在git push就可以了。但还有一个小问题是你会遇到这么一个报错：fatal: refusing to merge unrelated histories.

这个报错的意思是说**不能够将两个没有关系的历史记录合并起来**，原因是我们commit到本地git仓库的时候，本地的master还没有和远程的master分支取得关联。git默认是不允许将没有关联的记录进行合并的，不过这个问题也很好解决，我们只需要加上参数强制让它允许就可以了：

```bash
git pull --allow-unrelated-histories
```

这样我们就会发现它已经成功了，远程的readme文件已经被拉取了下来。之后我们再运行git push即可。由于我们已经将本地的master和远程的master取得了联系，我们只需要git push就可以了，不需要git push origin master了。