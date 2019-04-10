# 一、 了解Git和Github
## 1. 什么是Git
Git 是一个免费、开源的版本控制系统
## 2. 什么是版本控制系统
版本控制系统是一种记录一个或若干个文件内容变化，以便将来查看阅特定版本修订情况的系统
+ 系统具有功能
    + 记录文件所有变化
    + 随时可以恢复任何一个历史状态
    + 对人协作开发或修改
    + 错误恢复
## 3. 什么是Giuhub
Github是全球最大的社交编程及代码托管网站（https://github.ocm/)
Github可以托管各种git库，并提供一个web界面（用户名。github.io/仓库名）
## 4. Github和Git是什么关系
Git 是版本控制系统
Github是项目代码托管的平台，借助git来管理代码
## 5. 为什么学习github
* 学习优秀的开源项目
* Github是项目代码托管的平台，借助git来管理项目代码
---
# 二、基本概念
## 1. 仓库（repository）
仓库用来存项目代码，每个项目对应要给仓库，多个开源项目则有多个仓库
## 2. 收藏（star)
收藏项目，方便下次查看
## 3. 复制克隆项目（Fork)
注：该forkde 项目是独立存在的
## 4. 发送请求（Pull Request)
通俗说，小白fork了大佬的代码并做了修改，小白PR，希望能大佬能同意，让修改的代码能整合到源代码里面。
## 5. 关注（Watch）
关注了某个项目，如果那个项目更新了，你会第一时间收到通知提醒 
## 6. 事务卡片（Issue)
 发现代码BUG,但是目前没有成型的代码，需要讨论时用。
## 7. Github主页
该页左侧主要显示用户动态及关注用户或关注仓库的动态，右侧显示所有的库
## 8. 仓库主页
仓库主页显示项目的信息，如：代码、版本、收藏、关注、fork情况等
## 9. 个人主页
个人信息：头像、个人简介、关注我的人、我关注的git库、我的开源项目、我贡献的开源项目等
***
# 三、github
## 1. 创建仓库/创建新项目
**说明***
## 2.仓库管理
1. 新建文件
2. 编辑文件
3. 删除文件
4. 上传文件
5. 搜索文件库（快捷键t）
6. 下载/检出项目
## 2.Github issues
作用： 发现BUG,但是目前没有成型代码，需要讨论时用，或者使用开源项目出现问题时使用

 * ==一个git库（仓库）对应一个开源项目==
 * 通过管理git管理git库
## 3.开源项目贡献流程
### 新建issue
提交使用问题或者建议或者想法
### Pull Request
步骤

    1. fork项目
    2. 修改自己仓库的项目代码
    3. 新建Pull Request
    4. 等待作者操作审核
---
# 四、git基本工作流程
## 1.三个区域
1.  git repository(git仓库)
    * 最终确定的文件保存到仓库，成为一个新的版本，并且对他人可见
2. 暂存区
    * 暂存已经修改的文件最后统一提交到git仓库中
3. 工作区（working directory)
    * 添加、编辑、修改文件等动作
    
## 2. 向仓库中添加文件流程
1. git status (查看文件状态)
2. git add hello.py(从工作区提交到暂存区)
3. git status(查看文件状态)
4. **git commit -m "description"**
5. git status
---
# 五、Git 初试化及仓库创建和操作
## 1. 基本信息设置
**1. 设置用户名**
    
```
 git config --global user.name 'onceone'
```

2. 设置用户名邮箱
    
```
 git config --global user.email '1301016428@qq.com'
```

**注**：该设置在github仓库主页显示谁提交了该文件
***
## 2. 初始化一个Git仓库
1. 创建文件夹
    + 右击>新建
* 或者：
```
 mkdir test
```

2. 在文件内初始化 git（创建git仓库）

```
    cd test
    git init
```
----
3. 向仓库添加文件
    * 创建文件
    * 提交文件到暂存区
    * 提交到git仓库
```
touch test_python1.py
git status
git add test_python1.py
git status
git commit -m "此处为描述信息"
git status
```

4. 修改仓库文件
    + 用vim （linux 命令）
    
5. 删除文件

 * 先删除本地文件
 * 再删除git中的文件

```
rm  hello.py
git rm hello.py
git commit -m "提交描述"
```
----
# 五、Git管理远程仓库
### 目的 ：
    备份、实现代码共享集中化管理
## 1.Git 克隆操作
### 目的：
    将远程仓库（github对应的项目）复制到本地
### 代码：
    
```
git clone "仓库地址"
```
### 查询是否已经初始化

```
git config --list
```

## 2. 同步到远程仓库
### 代码
1. 先按上述方法同步到本地git仓库（一共三步）
2. 再同步到远程仓库 

```
git push
```

## 3. 解决git push 错误
如：The requeseted URL returned error:403 Forbidden while accessing
答：私有项目，么有权限，输入用户名和密码，或者远程地址采用这种类型：

```
vi .git/config
```
将--> 

    [remote "origin"]  url = https://github.com/用户名/仓库名.git
    
修改为：

    [remote "origin"]  url = https://用户名：密码@github.com/用户名/仓库名.git
---
# 六、Github Pages搭建网站
## 个人站点
### 访问 
https://用户名.github.io
### 搭建步骤
1. 创建个人站点 -> 新建仓库（注：仓库名必须是[==用户名.github.io
2. 在仓库下新建index.html的文件即可

**注**
 1. github pages 仅支持静态网页
 2. 仓库里面是.html文件
 3. 个人主页可是设置主题
## project pages 项目站点
### 访问
https://用户名.github.io/仓库名
### 原理
gh-pages 用于构建和发布
### 搭建步骤
1. 进入项目主页，点击settings
2. 在settings页面，点击【lanucn automatic page generator】来自动生成主题页面
3. 新建站点基础信息设置
4. 选择主题
5. 生成网页