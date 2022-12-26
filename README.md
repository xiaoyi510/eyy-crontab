# 易语言 Crontab 模块源码

# 项目简介
使用易语言语言开发的轻量级定时任务模块, 用于支持windows没有crontab的替代产物

## 预览
![image](https://user-images.githubusercontent.com/20254874/201052723-4fe4b983-5ba8-401e-8874-8d12ddc7597e.png)


## 功能特性
  1. 支持通用Crontab时间格式文本
  2. 支持秒年级别规则
  3. 支持多任务管理
  4. 支持任务暂停,继续,停止,开始

## 格式
1. 5位定时任务参数为 分钟级别
2. 6位定时任务参数则是在尾部增加年参数
3. 7位定时任务则在6位的基础上在第一位增加秒格式

## 使用方式
  1. 解析表达式
     `gCrontabParse.Parse (cron, crontabRunner)`
  2. 添加到多任务处理中心
     `mCrontabMulit.AddRunner (crontabRunner, <任务名称 唯一>, 到整数 (&回调方法)`
     回调方法 参数 `nextTime`,`crontabParseHandle`,`nameAddr`,`textAddr` 整数型
```易语言
.版本 2

.子程序 func, , ,  测试回调地址
.参数 nextTime, 整数型, , 触发时间
.参数 crontabParseHandle, 整数型
.参数 nameAddr, 整数型,  , 任务名称地址
.参数 textAddr, 整数型, , 触发索引
.局部变量 text, 文本型
.局部变量 name, 文本型

name ＝ 指针到文本 (nameAddr)
text ＝ 指针到文本 (textAddr)

```

## 更新记录



v3.2
--------
* 修复句柄过多


v3.1 
--------
* 增加多任务监控
* 剥离案例 剔除模块中的案例


v3.0
--------
* 第一版 支持单个任务 多个任务需要自行实例化多个类

