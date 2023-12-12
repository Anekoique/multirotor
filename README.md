



# multirotor

***

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


***


## The second day——12.11

### 1. install and learn g++

- question 1: unable to install g++(软件包有未依赖的关系)
- solve :swap sources;

### 2. c++ printf  "hello world"

- question 2 :unable to edit helloworld.cpp
- solve :learn vim (  --,--  ;   gedit is better  )
***
- question 3 :unable to compile and run
- solve :learn g++ about linking cpp files
***
- question 4 :push helloworld 文件夹到github 时 error: 源引用规格 helloworld 没有匹配
- solve :创建本地仓库和分支没有add 文件
***
- question 5:本地上传helloworld文件到远程github仓库后，本地修改readme上传git hub出现问题—> git pull 整合远程变更又出现问题—>偏离分支：当本地的分支落后于远程分支时，本地分支又自行修改项目文件生成了新的提交
- solve : git config pull.rebase false  # 合并  +  git pull

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

***

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

***

## The third day——12.12
### 1. install opencv
_怎么会有装起来这么麻烦的东西_

1. install cmake
2. use gedit 
3. install pkg-config

- question 1 : 装着装着虚拟机就死机了？
- solve : 强制重启，太智能了我直接执行下一个操作居然帮我帮上个死机没完成的操作自动执行
- question 2 : 检验时执行 pkg-config opencv --modversion 报错
- solve : 手动创建opencv.pc

```c++
cd /usr/local/lib
sudo mkdir pkgconfig && cd pkgconfig
sudo gedit opencv.pc
```
```c++
prefix=/usr/local
exec_prefix=${prefix}
includedir=/usr/local/include
libdir=/usr/local/lib
 
Name: OpenCV
Description: Open Source Computer Vision Library
Version: 4.4.0
Libs: -L${exec_prefix}/lib -lopencv_stitching -lopencv_superres -lopencv_videostab -lopencv_aruco -lopencv_bgsegm -lopencv_bioinspired -lopencv_ccalib -lopencv_dnn_objdetect -lopencv_dpm -lopencv_face -lopencv_photo -lopencv_freetype -lopencv_fuzzy -lopencv_hdf -lopencv_hfs -lopencv_img_hash -lopencv_line_descriptor -lopencv_optflow -lopencv_reg -lopencv_rgbd -lopencv_saliency -lopencv_stereo -lopencv_structured_light -lopencv_phase_unwrapping -lopencv_surface_matching -lopencv_tracking -lopencv_datasets -lopencv_text -lopencv_dnn -lopencv_plot -lopencv_xfeatures2d -lopencv_shape -lopencv_video -lopencv_ml -lopencv_ximgproc -lopencv_calib3d -lopencv_features2d -lopencv_highgui -lopencv_videoio -lopencv_flann -lopencv_xobjdetect -lopencv_imgcodecs -lopencv_objdetect -lopencv_xphoto -lopencv_imgproc -lopencv_core
Libs.private: -ldl -lm -lpthread -lrt
Cflags: -I${includedir}
```
- question 3:编译时出现 fatal error ：opencv2/opencv.hpp:没有那个文件或目录
- solve : 将/usr/local/include/opencv4/opencv2扔到/usr/local/include/下

***

- question 4 ：上面的 solve 没有 solve
- quesiton ........
- sovle :卸载

***

### 2. learn to use opencv and code to invoke the webcam