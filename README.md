# 西工大计算机学院计算机操作系统实验报告 - 运行用户态程序

## 实验概述

本资源提供了西安工业大学计算机学院2022年度计算机操作系统课程的实验报告样本，专注于指导学生如何在操作系统项目环境中实现用户态程序的加载与运行。报告详尽解析了操作步骤、关键代码示例，并附有实验成果的屏幕截图，旨在为学习此课程的同学提供实用的参考材料。

## 实验目标

本实验基于已有的操作系统项目框架（Project2），重点在于增强对用户态程序执行机制的理解与实践能力。主要任务包括在特定的内核模块（如`user.c`, `elf.c`, `userseg.c`, `kthread.c`, `sysall.c`, 和 `main.c`）中做出必要的调整，确保能够从用户态启动可执行文件。此外，报告还涉及编译选项的微调，具体包括移除 `-Werror` 选项避免将警告视为错误以及添加 `-fno-stack-protector` 以兼容特定的开发需求。

### 关键修改点概览：

1. **用户进程生成**：更新 `src/GeekOS/user.c` 中的 `Spawn()` 函数，负责创建新的用户级进程。
   
2. **用户上下文切换**：修订 `Switch_To_User_Context()` 函数于同一文件中，用于在调度新进程之前切换到相应的用户地址空间。

3. **ELF文件解析**：保持 `src/GeekOS/elf.c` 文件中 `Parse_ELF_Executable()` 函数的功能性，与Project1相似，可以直接引用或调整相关代码以支持可执行文件的正确解析。

4. **Makefile调整**：文档详细说明了如何编辑 `Makefile`，去除 `-Werror` 限制，并引入 `-fno-stack-protector` 编译标志，简化调试过程并适应实验环境的特殊配置。

## 使用指南

1. 下载本资源包后，首先需按照报告中提供的步骤对指定的源码文件进行修改。
2. 注意检查并应用编译选项的调整，确保编译流程顺利无阻。
3. 实践过程中，对照报告中的代码片段和说明，逐步理解每个改动背后的原理。
4. 完成代码修改后，根据实验指导完成测试，利用报告中的截图和描述作为结果验证的参照。

通过深入此实验，学生们不仅能掌握操作系统内部管理用户进程的关键技术，还能深化对ELF格式及程序加载机制的认识，进一步提升解决实际问题的能力。

请注意，本实验报告旨在辅助学习，实验中遇到的具体技术细节和实现逻辑应结合课堂讲授和个人研究综合理解。

## 下载链接
[西工大计算机学院计算机操作系统实验报告-运行用户态程序分享](https://pan.quark.cn/s/96efc70872f9) 

(备用: [备用下载](https://pan.baidu.com/s/1hJHw9e9LAONRpiT6MKIUjA?pwd=1234))

## 说明

该仓库仅用于学习交流，请勿用于商业用途。
