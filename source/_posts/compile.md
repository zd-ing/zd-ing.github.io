---
title: rcore 编译基础
date: 2024-07-03 14:53:25
tags: rcore os
---

## 编译知识

##### 交叉编译：

在一种计算平台上编译另外一种计算平台上运行的程序，叫做交叉编译。

##### 现代编译流程（C/Rust编译器为例）

-  源代码——>预处理器——>宏展开的源码
- 宏展开的源码——>编译器——>汇编程序
- 汇编程序——>汇编器——>目标代码
- 目标代码——>连接器——>可执行文件

##### rust编译目标三元组（cpu-操作系统-运行时）

- **X86 :** x86_64-unknown-linux-gnu

- **RISC-V :** riscv64gc-unknown-none-gnu   riscv64gc-unknown-none-elf

  *备注：其中 RISC-V 的指令集描述是，riscv32 是32位，riscv64 是64位*
  *RV32/64I 是所有RISC-V必须实现的基本整数指令集*
  *M扩展是乘除法扩展，A扩展是 原子指令和内存锁扩展，F/D扩展 是支持浮点运算，C扩展 是压缩指令扩展*
  *G是MAFD的集合*
  *elf 是指没有标准的运行时库*

- **aarch64（arm架构）:**  aarch64-unknown-linux-gnu



## rust 裸机编译环境

##### 移除std库

1. 在命令中指定目标平台

   ```rust
   cargo run --target riscv64gc-unknown-none-elf
   ```

2. 在配置文件中指定



