---
title: Visual Studio 调试器词汇表 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- glossary [Debugging SDK]
- debugging [Debugging SDK], glossary
ms.assetid: 4a2cfaab-1fbd-4a23-bd00-9ac4cc50d7fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8bca908957a98dfa9fa12b0e420a727a2798b4fc
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686842"
---
# <a name="visual-studio-debugger-glossary"></a>Visual Studio 调试器词汇表
以下是中使用的术语[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]调试 SDK。

## <a name="terms"></a>术语
 绑定的断点在代码中设置断点的抽象。 没有绑定的断点和代码流中的断点指令之间的一对一关系。 卸载代码时，绑定的断点可能会取消绑定。

 因果关系提供跨多个物理线程、 进程和计算机，跟踪逻辑的执行线程，并在该线程的生存期内重新构造在任意给定时间该逻辑线程的调用堆栈的功能。

 代码上下文提供已知的调试引擎的代码中的位置的抽象。 为大多数运行时体系结构，代码上下文是在程序的指令流中的地址。 对于非传统的语言，其中代码可能不由表示的说明，可以通过其他方式来表示代码上下文。

 代码路径表示在其中执行分支或函数调用的代码中执行的点。 堆栈跟踪是实质上是一系列函数调用的代码路径。

 调试引擎 (DE) 允许调试运行时体系结构的一个组件。 调试引擎与解释程序或操作系统一起工作，并提供调试服务，例如执行控制、 断点、 和表达式计算。

 文档上下文提供抽象的调试引擎已知的源代码文件文档中的位置。 对于大多数语言文档上下文是源文件中的位置。 对于非传统的语言，为其源文件可能不是文本，可以通过某些其他方法表示文档上下文。 另请参阅*文档位置*。

 文档位置提供已知的 IDE 的源文件中的位置的抽象。 对于大多数语言文档位置是一个源文件中的位置。 对于非传统的语言，可以以其他方式表示的文档位置。 另请参阅*文档上下文*。

 错误断点的抽象描述中挂起断点的错误。 错误断点可能描述挂起断点，挂起断点或会阻止挂起断点绑定到代码位置的其他信息与关联的表达式的位置中的错误。

 评估上下文提供的编程上下文的表达式计算的抽象。 通常情况下，评估上下文是一个范围。 当执行表达式上下文中的计算表达式，表达式上下文提供符合其创建连接点的作用域规则。 例如，在堆栈帧中创建的表达式上下文将评估本地变量、 方法参数、 类成员 （如果适用） 和全局变量提供的上下文。

 截获异常的调试引擎截获异常，即使没有异常处理机制是在当前堆栈帧中的位置。

 JustMyCode 的调试仅属于用户的代码并忽略所有中间代码，如系统代码的概念，即使该系统代码提供了源代码。

 挂起的断点提供断点之前、 期间和之后的代码的抽象是加载和一种方式，为虚拟化的断点。 挂起断点的一个：

- 包含将断点绑定到一个或多个程序中的代码所需的所有信息。

- 可能会将绑定到一个或多个程序的多个代码位置。

- 永远不会将自身绑定到代码。

  每个时间代码加载，在程序中的所有挂起断点则检查以确定是否它们可以将绑定。 挂起断点称为包含此属性与绑定的所有绑定的断点。

  处理物理的 Win32 进程。 一个进程可以包含多个程序。 另请参阅*程序*。

  编程特定的运行时体系结构内运行的单个命名空间。 另请参阅*进程*。

  会话调试管理器 (SDM) 管理任意数量的调试任意数量的任意数量的计算机上的多个进程中的程序的调试引擎。 在基本级别，SDM 是多路复用器的调试引擎。 此外，SDM 提供了对 IDE 的调试会话的统一的视图。

  堆栈帧表示特定级别的嵌套的函数调用和计算的特定帧的状态。

  线程在至少一个程序中运行的基于堆栈的指令执行的通用的概念。

  警告断点的抽象描述中挂起断点的警告。 警告断点介绍为何挂起断点有尚未绑定到代码位置的原因。 这可能是加载的代码具有未尚未挂起断点所描述的位置或某些其他原因。

## <a name="see-also"></a>请参阅
- [Visual Studio 调试器可扩展性](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)