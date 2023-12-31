---
title: CMakelists基础指令
date:
tags: 
- C++
- CMakelists
categories:
- [C++, CMakelists]
description:
top_img: false
---

# CMakelists基础指令 

## （1）include_directories 

用于设置头文件的相对路径。全局路径默认是功能包所在目录，一般会放在功能包根目录下的include文件夹中，所以此处需要添加该文件夹。此外，该配置项还包含ROS catkin编译器默认包含的其他头文件路径${catkin_INCLUDE_DIRS}，比如ROS默认安装路径、Linux系统路径等。在本例中，所用的是ROS默认安装路径下的头文件。 

##  （2）add_executable 

用于设置需要编译的代码和生成的可执行文件。第一个参数为期望生成的可执行文件的名称，后边的参数为参与编译的源码文件（cpp），如果需要多个代码文件，则可在后面依次列出，中间用空格进行分隔。 

##  （3）target_link_libraries 

用于设置链接库。很多功能需要使用系统或者第三方的库函数，通过该选项可以配置 执行文件链接的库文件，第一个参数是可执行文件的名称，后面依次列出需要链接的库。此处编译没有使用其他库，添加默认链接库${catkin_LIBRARIES}即可。 

##  （4）add_dependencies 

用于设置依赖。在很多应用中，我们需要定义语言无关的消息类型，消息类型会在编译过程中产生相应语言的代码，如果编译的可执行文件依赖这些动态生成的代码，则需要使用add_dependencies添加${PROJECT_NAME}_generate_messages_cpp 配置，即该功能包动态产生的消息代码。该编译规则也可以添加其他需要依赖的功能包。 