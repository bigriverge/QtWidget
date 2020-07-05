# Qt控件v1.0.0版本 整体设想初稿

## 版本号参考node插件版本规范：
major.minor.patch

major - 主要版本 (可能与之前版本API不兼容)
minor - 次要版本 (兼容同一个大版本的API)
patch - 补丁版本 (修复bug或细微变更)


## 概述
整理日常用到的Qt控件， 提升开发效率。

## 控件描述
一个控件应包含以下内容：
### 控件说明
    说明控件的用途，包含的特性， 以及使用上的限制条件。
### 控件类别
    QtWidget | Qml 默认（QtWidget）
### 控件效果展示
    一张gif展示效果
    
## 控件规范
### 结构规范
    1. 一个控件一个文件夹， 文件夹名称与需要引用的头文件名称一致。
    举例： 文件夹名称 CSwitchButton
    2. 通过调用接口修改控件的属性， 尽量避免在构造函数中加入过多参数
    3. 一定要提供改变样式的接口 包括不限于更改主题
### 控件命名规范
    所有控件名称以大写字母C为前缀 + 控件名称（或用途） + 控件类型 (每一个部分首字母大写)
    举例：IOS系统的Switch开关控件   CSwitchButton 
### 代码规范
    类成员：（同一个控件不要两种方式混用）
    1. m_类型+名称 方式 m_bxxx m_nxxx m_pxxx
    2. _名称 方式
   
    作用域：
    {
      //花括号另起一行
    }
    
    构造函数：
    xxWidget::xxWidget(QWidget *parent)
        : QWidget(parent)
        , 成员变量(xx)
        , 成员变量(xx)

    接口（函数｜方法）：（以下统称为接口）
    建议： 
    使用 动词 或 动宾短语的 形式
    命名方式：
    (提议)
    1. 以 按钮样式 举例  接口命名  setButtonStyle  getButtonStyle
    2. buttonStyle(xx) 设置按钮样式 buttonStyle() 获取按钮样式

    参数
    1. 驼峰命名 buttonStyle
    2. _连接 button_style

## 默认风格
   主色调 #409EFF
   成功： #5CB87A  警告：#E6A23C  警告： #F56C3C  信息： #8896B3
   字体： #303133  #606266 #909399 #C0C4CC
   Border: #DCDFE6  Border Light: #E$E&ED   Border Lighter: #EBEEF5  Border Extralight: #F2F6FC