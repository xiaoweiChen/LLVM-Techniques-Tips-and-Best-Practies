# LLVM Techniques, Tips, and Best Practices 

Clang and Middle-End Libraries

Design powerful and reliable compilers using the latest libraries and tools from LLVM

(*Clang和中端库 - 使用最新的LLVM库和工具设计强大且可靠的编译器*)

* 作者：[Min-Yih Hsu 許民易](https://github.com/mshockwave)

* 译者：陈晓伟

* 首次发布时间：2021年4月22日([来源](https://www.amazon.com/Techniques-Practices-Clang-Middle-End-Libraries/dp/1838824952))

> 翻译是译者用自己的思想，换一种语言，对原作者想法的重新阐释。鉴于我的学识所限，误解和错译在所难免。如果你能买到本书的原版，且有能力阅读英文，请直接去读原文。因为与之相较，我的译文可能根本不值得一读。
>
> <p align="right"> — 云风，程序员修炼之道第2版译者</p>

## 本书概述

编译器将高级编程语言转换为低层机器可执行的代码，所以每个程序员或工程师，在职业生涯的某个时刻，都会与编译器一起优化应用程序。LLVM为开发者提供了基础设施、库和(开发人员构建自己的)编译器所需的工具。使用LLVM的工具集，可以有效地为不同的后端生成代码，并进行优化。

本书将探索LLVM编译器的基础结构，并介绍如何来解决问题。我们从查看LLVM重要组件的结构和设计理念开始，逐步使用Clang库来构建分析高级源代码的工具。随着了解的深入，本书将向介绍如何处理LLVM IR——用以转换和优化源码。了解了这些，就将能够利用LLVM和Clang创建编程语言工具，包括编译器、解释器、IDE和源代码分析程序。

本书的最后，可以使用LLVM框架创建强大的工具技能，以应对现实中的各种挑战。

#### 关键特性

- (以务实的方式)探索Clang，LLVM的中端和后端
- 点亮LLVM的各个技能点，并掌握各种常见用例
- 通过示例应对实际的LLVM开发

#### 内容纲要

- 了解LLVM的构建系统是如何工作的，以及如何减少构建资源
- 掌握使用LLVM的LIT框架运行自定义测试的方法
- 为Clang构建不同类型的插件和扩展
- 基于Clang自定义工具链和编译器标志
- 为PassManager写LLVM Pass
- 了解如何检查和修改LLVM IR
- 了解如何使用LLVM的配置文件引导优化(PGO)框架
- 创建自定义(编译器)消毒器



## 适读人群

本书适用于所有具有LLVM工作经验的软件工程师，本书会提供了简明的开发指南和参考。如果你是一名学术研究者，这本书将助你在短时间内学习有用的LLVM技能，使你能够快速构建项目原型。编程语言爱好者也会发现这本书中的内容，在LLVM的帮助下构建一种新的编程语言也十分有趣



## 作者简介

**Min-Yih "Min" Hsu**是加州大学欧文分校计算机科学博士研究生。他的研究集中在编译器工程、代码优化、高级硬件架构和系统安全。2015年起，他一直是LLVM社区的活跃成员，并贡献了许多补丁。他还致力于通过各种途径倡导LLVM和编译器工程，比如写博客和发表演讲。在业余时间，他喜欢了解各种不同的咖啡豆和煮咖啡的方法。

> 我要感谢所有支持过我的人，特别是家人和导师。还要感谢LLVM社区不论出身的包容和善待每一位成员。
>
> <p align="right"> —Min-Yih Hsu</p>

## 审评者介绍

**Suyog Sarda**是一名专业的软件工程师和开源爱好者，专注于编译器开发和编译器工具，是LLVM开源社区的积极贡献者。他毕业于了印度浦那工程学院，具有计算机技术学士学位。Suyog还参与了ARM和X86架构的代码性能改进，一直是Tizen项目编译团队的一员，对编译器开发的兴趣在于代码优化和向量化。之前，他写过一本关于LLVM的书，名为《LLVM Cookbook》，由Packt出版。除了编译器，Suyog还对Linux内核开发感兴趣。他在迪拜Birla Institute of Technology的2012年IEEE Proceedings of the International Conference on Cloud Computing, Technologies, Applications, and Management上发表了一篇题为《VM pin and Page Coloring Secure Co-resident Virtualization in Multicore Systems》的技术论文。

他在浦那工程学院获得了技术学士学位。到目前为止，他的工作主要与编译器有关，并他对编译器的性能方面特别感兴趣。他曾致力于DSP图像处理语言的研究，使用LLVM的模块化特性可以根据编译器的需求快速实现。然而，LLVM的文档比较分散，他希望这本书可以为LLVM编译器基础架构提供一种综合性的概述。



## 本书相关

* github翻译地址：https://github.com/xiaoweiChen/LLVM-Techniques-Tips-and-Best-Practies
* 译文的LaTeX 环境配置：https://www.cnblogs.com/1625--H/p/11524968.html 

