# 简易iOS组件制作

用于小型APP的组件，步骤简单易操作，不用提交到私有Spec库。为了方便国内用户，采用码云git。


### 步骤1 创建简单组件工程

![image](https://gitee.com/shenzhaoliang/STKit/raw/master/Image/image1.jpg)


==注意==
1. 必须添加开源许可证，否则podspec无法验证通过


### 步骤2 创建podspec与组件文件夹

![image](https://gitee.com/shenzhaoliang/STKit/raw/master/Image/image2.jpg)


1. 复制提供的podspec到自己的组件工程中，修改就可以
2. 将组件代码添加对应的文件夹中

### 步骤3 编写podspec
[官方podspec指导](https://guides.cocoapods.org/syntax/podspec.html)

编写完成提交到Git, 并且添加标签

==注意==

1. Git上的标签与podspec文件的version要一致


样例：

```

Pod::Spec.new do |s|
s.name              = 'STKit'
s.module_name       = 'STKit'
s.version           = '1.0.0'
s.summary           = 'STKit is a collection of useful classes, structs and extensions to develop Apps faster.'
s.homepage          = 'https://github.com/STShenZhaoliang'
s.authors           = { 'STShenZhaoliang' => '409178030' }
s.license           = { :type => 'MIT', :file => 'LICENSE' }
s.source            = { :git => 'https://gitee.com/shenzhaoliang/STKit.git', :tag => s.version }
s.swift_version             = '4.1'
s.ios.deployment_target     = '9.0'
s.ios.source_files          = 'STKit/*.swift'
end

```


### 步骤4 验证podspec合法性

![image](https://gitee.com/shenzhaoliang/STKit/raw/master/Image/image3.jpg)

如图所示：
终端输入 

```
pod lib lint STKit.podspec

```

提示下面内容，制作完成，就可以愉快的使用了

```

STKit passed validation

```

### 使用

在工程中的Podfile添加组件的引用，Podfile编写样例

```
platform :ios, '9.0'
target 'STKitTest' do
pod 'STKit', :git => 'https://gitee.com/shenzhaoliang/STKit.git', :tag => '1.0.0'
end

```














