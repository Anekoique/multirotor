



# multirotor

<hr>

## The first day ——12.10

* install vmware-workstation and ubuntu

* swap sources and 换输入法

* learn git

* github关联远程仓库

* install and use Typora

### Git

|code|meaning|
|:------|:-----------|
|mkdir test|创建目录|
|cd test|进入目录|
|git init|初始化仓库|
|ls ；ls -ah|查看目录|
|touch test.c|新建项目|
|add|添加到缓存|
|commit -m "words"|提交到库|
|log|提交历史|
|status|查看仓库状态|
|checkout -- file|回到最近修改状态|
|rm ；rm -rf file|删除|
|reset+checkout|恢复文件|
|checkout -b dev|创建分支+切换|
|merge|合并|
|branch -a|查看分支|
|branch -D|删除分支|
|branch -m|修改分支名|
|clone|远程仓库关联到本地|
|push origin branch|修改提交|


<hr>


## The second day——12.11

### 1. install and learn g++

- question1: unable to install g++
- sovle1:swap sources;

### 2. c++ printf  "hello world"

- question2:unable to edit helloworld.cpp
- sovle2:learn vim


- question3:unable to compile and run
- sovle3:learn g++ about linking cpp files

### G++

#### some command：

|command|meaning|
|-------------|-------------|
|-o outputfile file.cpp|编译为可执行文件|
|-c|编译为对象文件|
|-o outputfile file1.o file2.o|链接对象文件|

#### about .o files and .exe files：
对象文件和可执行文件的主要区别在于链接的程度：对象文件包含了部分链接的代码，而可执行文件包含了完全链接的代码。在一些大型项目中，源代码可能被分割成多个文件，然后分别编译成对象文件，最后再链接成一个可执行文件。这样的做法可以提高编译的效率，因为当某个源文件被修改时，只需要重新编译那个文件，而不需要重新编译整个项目。

```c++
g++ -o test1 hello.cpp helloworld.cpp
```
```c++
g++ -c hello.cpp
g++ -c helloworld.cpp
g++ -o test2 hello.o helloworld.o
```
```c++
g++ -o test3 hello.o helloworld.cpp
```
```c++
g++ -o test4 hello.cpp //wrong
```



<hr>

### vim
_默认命令模式_

|command|meaning|
|:-------------|:---------|
|ESC|命令模式|
|gg / G/ 5+G|首行/末行/第五行|
|yy / p/ dd|复制/粘贴/剪切|
|u / ctrl + r|撤销/取消撤销|
|+i / +a|编辑模式|
|：/ wq/ q！|末行模式/保存退出/强制退出|