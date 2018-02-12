# P2常见问题汇总

**1. Conda更新很慢/包下载很慢**

用以下任一种方法可以解决：

- 翻墙（自行搜索软件下载，或者和助教联系）；
- 使用清华大学提供的镜像源，具体操作方式见[此链接](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/)

**2. 如何同时安装Python3和Python2？**

Conda支持安装多个Python环境，具体操作方式见[此链接](https://conda.io/docs/py2or3.html)

**3. 为什么装了多个环境，Jupyter Notebook还是只能使用一个版本的Python？**

请检查你是否在所有环境中安装了Jupyter Notebook，具体方式如下：

1. 打开Anaconda Navigator
 ![](https://i.imgur.com/xHULooG.png)

2. 在Navigator中做如下操作
 ![](https://i.imgur.com/6vi81LS.png)

3. 重新打开Notebook，即可使用两个版本的环境


**4. 命令行是什么？如何在命令行转换目录？**

由于命令行不是本课程的教学内容，所有命令行相关的疑问均请参见[此链接](https://blog.henix.info/blog/windows-cmdbasic/_.html)

**5. Titanic数据集各字段的含义。**

请参阅此[数据字典链接](https://www.kaggle.com/c/titanic/data)

**6. 在命令行和Anaconda Prompt中都无法使用Conda命令的所有解决方案。**

- 检查系统版本。Anaconda已经不支持Windows XP；同时查看自己电脑是32位还是64位（本页面视频有说明），不要装错了；
- 检查自己是否原来安装过Python，如果安装过请彻底删除Python（同时要删除环境变量）后重装Anaconda；
- 检查自己是否将Conda命令添加到了环境变量，操作方法见[本页面](https://stackoverflow.com/questions/28612500/why-anaconda-does-not-recognize-conda-command)；
- 确保你的Anaconda安装路径不包含中文或其他非英语常用字符；
- 经过以上步骤还是没有任何改善，请卸载Anaconda重装一遍；
- 重装一遍后还是没有改善，说明助教也不知道原因，无法帮助你，所以不用在群里@助教了，直接使用微软出品的[Azure Notebook](https://notebooks.azure.com/)作为替代方案完成课程和项目。

**7. Mac系统下无法安装matplotlib，提示“Failed building wheel for subprocess32”**

安装[Xcode](https://developer.apple.com/xcode/)

**8. 安装Anaconda时显示UnicodeDecodeError。**

- 如果Python是2.7版本的，请确保安装路径没有中文或者其他非英语常用字符；
- 如果安装路径不存在上述问题，请参考[此链接](http://www.cnblogs.com/kangronghu/p/6154919.html)解决。

**9. 如何正确下载Notebook？**

1. 右键另存为，将文件存入任一文件夹；
2. 更改文件夹后缀名为.ipynb。如果无法修改，请在文件管理器中勾选下图的“文件扩展名”，再对文件重命名，直接修改后缀。最终你的文件名为“xxxx.ipynb”

![](https://i.imgur.com/IYUCKqb.png)


**10. 两个简明的[Anaconda](https://www.zhihu.com/question/58033789/answer/254673663)和[Jupyter Notebook](https://www.zhihu.com/question/46309360/answer/254638807)使用教程（感谢学员悟空和知乎用户“猴子”提供的链接及教程内容）**

**11. 在Jupyter Notebook中按Tab键无法自动补全代码。**

请尝试安装pyreadline包，命令如下：

```cmd
conda install pyreadline
```

再打开Notebook重试补全代码功能。

**12. 明明已经使用命令安装了某个包（比如Unicodecsv），在Notebook导入时却显示No module named XXX错误。**

目前还没有根本性的解决办法，可能是环境变量的问题导致。一个可行的方案是创建新环境，并与Notebook关联，所有代码都在新环境中运行。具体步骤如下：

假如你第一次安装Anaconda，系统会自动创建一个默认环境，Notebook中也只有默认环境。默认环境中包无法导入时，请尝试如下命令（假设你的Python版本为2.7）：

```cmd

conda create -n py27 python=2.7 anaconda #创建环境，py27可以是其他名称
conda install nb_conda
acitvate py27 #进入新环境
conda install unicodecsv #在新环境中安装模块

```

然后再启动jupyter notebook，做如下操作：

![](https://i.imgur.com/hb1iqv0.png)

点击Python [conda env: py27]，切换到py27环境，再运行代码看下能否导入模块。

请注意，以后进入所有notebook的时候，都需要切换到py27环境。你安装所有包时，都需要先使用activate py27命令，在新环境中安装。

**13. 在Mac环境下运行Jupyter Notebook报如下错误：**

![](https://i.imgur.com/z5IRAeV.jpg)

解决办法：使用此命令启动Jupyter Notebook：

```cmd
jupyter notebook --NotebookApp.iopub_data_rate_limit=10000000000
```

**14. 运行Conda命令时出现“Missing write permissions”错误：**

请使用如下方式打开Anaconda Prompt，再次运行Conda命令：

![](https://i.imgur.com/V5HdRn2.png)

**15. 如何将上一节练习生成的数据导入到下一节的Workspace中？**

请参考本页面的.mp4视频文件“Workspace中导入上一节生成的数据.mp4”。

**16. 有没有其他数据分析相关的书籍和学习资料？**

链接：https://pan.baidu.com/s/1eUfFebK 密码：wio6

网盘内容会不定期更新。注意，**请不要用微信自带的浏览器打开**，否则会显示链接不存在。



