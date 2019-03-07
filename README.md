# XcodeBuild-
傻瓜式教程自动化打包上传至App Store

前言
---
  APP完成时需要打包上传至APP Store, 在打包的时候多多少少都需要半小时左右,最主要的是如果用的是xcode打包需要有人看守,在接触到自动化打包后觉得真是个偷懒的好方法,
 .只要一条命令,xcodebuild 就会自动的将APP打包成ipa文件,并上传至app store connect
 
## 前期准备
---
1. 下载此shell脚本
2. 将文件拖入至项目根目录下
3. 修改脚本中的一下基本配置
4. App Store Connect 创建需要发布的版本
5. 打开终端 cd到项目根目录下 执行./shell.sh 

## 分步流程
### 第一步 导入文件
下载后 将XcodeBuild文件夹中的3个文件拷贝至项目的根目录中(exportAppstore.plist,exportTest.plist,shell.sh)
### 第二步 修改配置
打开shell.sh 文件
按照注释 修改共4处 文件中注释已标明 修改后保存关闭
打开exportAppstore.plist 文件
修改 provisioningProfiles字典里的 key 和value
key:项目的Bundle Id
value:生产证书的名字
修改后保存关闭
### 第三步 App Store Connect 创建版本
在[App store Connect 官网](https://itunesconnect.apple.com/login)创建需要发布的版本
### 第四步 开始打包 
打开终端 cd 到项目的根目录下
执行
```CPP，monokai
$ ./shell.sh
```
选择 发布到的地方 1 为App Store
### 查看导出的文件
打开项目根目录脚本运行结束或或多出两个文件件一个是IPADir 一个是build
IPADir:存放ipa文件
build:存放dsym等文件
## 主要事项
1.再次运行脚本 需要将根目录下的build 和ipadir文件夹删除 否则会清理失败
## 结束打王者荣耀去吧
  ### 参考文章
https://www.jianshu.com/p/121fe6fdc4e9
https://www.jianshu.com/p/4f4d16326152






