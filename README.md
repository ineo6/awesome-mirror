# **Awesome Mirror** [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

## nvm

安装`nvm`：

```sh
export NVM_SOURCE=https://gitlab.com/mirrorx/nvm.git
curl -o- https://gitlab.com/mirrorx/nvm/-/raw/master/install.sh | bash
```

设置`node`镜像：

临时使用：
```shell
export NVM_NODEJS_ORG_MIRROR="https://npmmirror.com/mirrors/node"
```

更多内容请查看：[https://github.com/ineo6/nvm](https://github.com/ineo6/nvm)

## Homebrew

安装脚本：

```shell
/bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"
```

如果你已经安装好`brew`，只是想更换镜像，也可以访问下面的站点获取设置脚本。

详细介绍&&帮助，请访问：

- [https://brew.idayer.com/](https://brew.idayer.com/)
- [https://zhuanlan.zhihu.com/p/90508170](https://zhuanlan.zhihu.com/p/90508170)

## pypi

临时使用：
```shell
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```

长期使用：

升级 pip 到最新的版本 (>=10.0.0) 后进行配置：
```shell
pip install pip -U
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

如果您到 pip 默认源的网络连接较差，临时使用本镜像站来升级 pip：

```shell
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U
```

### 可用源地址

- [阿里云](https://mirrors.aliyun.com/pypi/simple/) - https://mirrors.aliyun.com/pypi/simple/
- [清华大学](https://pypi.tuna.tsinghua.edu.cn/simple) - https://pypi.tuna.tsinghua.edu.cn/simple
- [中国科学技术大学](https://pypi.mirrors.ustc.edu.cn/simple/) - https://pypi.mirrors.ustc.edu.cn/simple/
- [豆瓣](https://pypi.douban.com/simple) - https://pypi.douban.com/simple

## Ruby Gems

### gem
```shell
# 添加 TUNA 源并移除默认源
gem sources --add https://mirrors.tuna.tsinghua.edu.cn/rubygems/ --remove https://rubygems.org/
# 列出已有源
gem sources -l
# 应该只有一个
```
 
### Gemfile 和 Bundler 的项目

```shell
bundle config mirror.https://rubygems.org https://mirrors.tuna.tsinghua.edu.cn/rubygems/
```

### 可用源地址

- [清华](https://mirror.tuna.tsinghua.edu.cn/help/rubygems/) - https://mirrors.tuna.tsinghua.edu.cn/rubygems/
- [中科大](https://lug.ustc.edu.cn/wiki/mirrors/help/rubygems) - https://mirrors.ustc.edu.cn/rubygems/ 
- [ruby-china](https://gems.ruby-china.com/) - https://gems.ruby-china.com/

## CocoaPods

旧版使用方式:

```shell
pod repo remove master
pod repo add master https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git
pod repo update
```

新版的`CocoaPods`不允许用`pod repo add`直接添加`master`库了，但是依然可以通过下面方式：

```shell
cd ~/.cocoapods/repos 
pod repo remove master
git clone https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git master
```

最后在`Podfile`第一行加上:

```
source 'https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git'
```

### 可用源地址

- [清华](https://mirror.tuna.tsinghua.edu.cn/help/CocoaPods/) - https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git

## Flutter

`Flutter`是一款跨平台的移动应用开发框架，由`Google`开源。用`Flutter`开发的应用可以直接编译成`ARM`代码运行在`Android`和`iOS`系统上。

`Flutter`安装时需要从`Google Storage` 下载文件，如您的网络访问`Google`受阻，需要使用镜像。

临时使用：
```shell
export FLUTTER_STORAGE_BASE_URL="https://mirrors.tuna.tsinghua.edu.cn/flutter"
```

长期使用：
```shell
echo 'export FLUTTER_STORAGE_BASE_URL="https://mirrors.tuna.tsinghua.edu.cn/flutter"' >> ~/.bashrc
```

此外`Flutter`开发中还需要用到`Dart`语言的包管理器`Pub`，其镜像使用方法参见`Pub` 镜像安装帮助。

## Pub

`Pub`是`Dart`官方的包管理器。跨平台的前端应开发框架`Flutter`也基于`Dart`，并且可以使用大部分`Pub`中的库。

临时使用：
```shell
PUB_HOSTED_URL="https://mirrors.tuna.tsinghua.edu.cn/dart-pub/" pub get # pub
PUB_HOSTED_URL="https://mirrors.tuna.tsinghua.edu.cn/dart-pub/" flutter packages get # flutter
```

长期使用：
```shell
echo 'export PUB_HOSTED_URL="https://mirrors.tuna.tsinghua.edu.cn/dart-pub/"' >> ~/.bashrc
```
