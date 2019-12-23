# **Awesome Mirror** [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

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

- [阿里云](http://mirrors.aliyun.com/pypi/simple/) - http://mirrors.aliyun.com/pypi/simple/
- [清华大学](https://pypi.tuna.tsinghua.edu.cn/simple) - https://pypi.tuna.tsinghua.edu.cn/simple
- [中国科学技术大学](https://pypi.mirrors.ustc.edu.cn/simple/) - https://pypi.mirrors.ustc.edu.cn/simple/
- [豆瓣](https://pypi.douban.com/simple) - https://pypi.douban.com/simple




## nvm

临时使用：
```shell
export NVM_NODEJS_ORG_MIRROR="https://npm.taobao.org/mirrors/node/"
```

长期使用：

```shell
echo 'export NVM_NODEJS_ORG_MIRROR="https://npm.taobao.org/mirrors/node/"' >> ~/.bashrc
```

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
$ cd ~/.cocoapods/repos 
$ pod repo remove master
$ git clone https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git master
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

## Homebrew

### brew && core && cask

设置镜像：
```shell
git -C "$(brew --repo)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

git -C "$(brew --repo homebrew/cask)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git
```

恢复官方：

```shell
git -C "$(brew --repo)" remote set-url origin https://github.com/Homebrew/brew.git

git -C "$(brew --repo homebrew/core)" remote set-url origin https://github.com/Homebrew/homebrew-core.git

git -C "$(brew --repo homebrew/cask)" remote set-url origin https://github.com/Homebrew/homebrew-cask.git
```


#### 可用源

| 名称 | 类型 | 地址 |
| --- | --- | --- |
| 清华 | brew | https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git |
| 清华 | core | https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git |
| 清华 | cask | https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git |
| 中科大 | brew | https://mirrors.ustc.edu.cn/brew.git |
| 中科大  | core | http://mirrors.ustc.edu.cn/homebrew-core.git |
| 中科大  | cask | http://mirrors.ustc.edu.cn/homebrew-cask.git |



### Homebrew-bottles

临时替换：
```shell
export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles
```

长期替换：
```shell
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile
```

#### 可用源

- [中科大](https://mirrors.ustc.edu.cn/homebrew-bottles) - https://mirrors.ustc.edu.cn/homebrew-bottles
- [清华](https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles) - https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles

### homebrew-install

解决`install`脚本无法访问问题，通过镜像加速脚本安装。

使用方法和官方一致：

```shell
/usr/bin/ruby -e "$(curl -fsSL https://cdn.jsdelivr.net/gh/ineo6/homebrew-install/install)"
```

具体食用说明[点此](http://idayer.com/mac-install-homebrew-by-cdn/)
