---
title: 不懂就问系列-为什么git有暂存区这一层
date: 2019-10-21 16:01:19
categories: 
- Git
tags:
- 暂存区
- git add
- git commit
- 不懂就问
---

> 虽然每天用，但是git为啥有暂存区这一层呢，每次都得先git add, 然后git commit，好麻烦的说。

Git 本地数据管理，大概可以分为三个区，工作区,暂存区和版本库。

- 工作区（Working Directory）
是我们直接编辑的地方，例如 Android Studio 打开的项目，记事本打开的文本等，肉眼可见，直接操作。
- 暂存区（Stage 或 Index）
数据暂时存放的区域，可在工作区和版本库之间进行数据的友好交流。
- 版本库（commit History）
存放已经提交的数据，push 的时候，就是把这个区的数据 push 到远程仓库了。


跟传统的版本控制工具，如SVN，最大的不同就是多了一个暂存区的概念，加了它有什么用呢
- 提交原子化
如：同时修改了 a.js,b.js ,但其实他们分别属于两个featrue，可以分别add a 和 b 进行commit。

- 提交阶段性
如： 先修改了a.js的一句话，git add 添加到暂存区，这时候后续对a.js的修改可能还是可以加到暂存区，然后一起提交commit，可以认为对a.js进行了一个递进的操作，但是是一起commit的。

- 回溯
多了一层区域，也给历史回溯增加了更多可能，根据自己的实际情况，选择回溯的位置。

