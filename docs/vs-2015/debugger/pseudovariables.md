---
title: 伪变量 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Watch window, pseudovariables
- debugging [Visual Studio], pseudovariables
- pseudovariables
ms.assetid: fae84f68-2138-4144-9bd4-c9e271b6182a
caps.latest.revision: 40
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 79d2f47acfbd5a4b6adf6d5f679fb3b514679dab
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789494"
---
# <a name="pseudovariables"></a>伪变量
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

伪变量是使用变量窗口中显示某些信息的术语或**快速监视**对话框。 你可以像输入普通变量那样输入伪变量。 但伪变量不是变量，它不与程序中的变量名相对应。  
  
## <a name="example"></a>示例  
 假设你在编写本机代码应用程序，并且希望看到此应用程序中分配的句柄数。 在中**Watch**窗口中，您可以输入以下伪变量在**名称**列，然后按返回以对其进行评估：  
  
```  
$handles  
```  
  
 在本机代码中，可使用的伪变量如下表所示：  
  
|伪变量|函数|  
|--------------------|--------------|  
|`$err`|显示函数 SetLastError 设置的上一个错误值。 显示的值代表将由 GetLastError 函数返回的值。<br /><br /> 使用 `$err,hr` 查看此值的已解码形式。 例如，如果上一个错误是 3，则 `$err,hr` 将显示 `ERROR_PATH_NOT_FOUND : The system cannot find the path specified.`|  
|`$handles`|显示应用程序中分配的句柄数。|  
|`$vframe`|显示当前堆栈帧的地址。|  
|`$tid`|显示当前线程的线程 ID。|  
|`$env`|在字符串查看器中显示环境块。|  
|`$cmdline`|显示已启动程序的命令行字符串。|  
|`$pid`|显示进程 ID。|  
|`$` *寄存器名*<br /><br /> 或<br /><br /> `@` *寄存器名*|显示寄存器的内容*寄存器名*。<br /><br /> 通常，只需输入寄存器名便可以显示寄存器的内容。 仅在寄存器名重载变量名时才需要使用此语法。 如果寄存器名与当前范围内的某个变量名同名，则调试器将该名称解释为变量名。 即，当`$`*寄存器名*或`@`*寄存器名*派上用场。|  
|`$clk`|以时钟形式显示时间。|  
|`$user`|显示一个结构，在该结构中含有应用程序运行于的帐户的帐户信息。 出于安全原因，将不显示密码信息。|  
|`$exceptionstack`|显示当前 Windows 运行时异常的堆栈跟踪。 `$ exceptionstack` 仅在 Windows 8.1 或更高版本上运行的应用商店应用中可用。 C++ 异常和 SHE 异常不支持 `$ exceptionstack`|  
|`$ReturnValue`|显示 .NET Framework 方法的返回值。 请参阅[检查方法调用的返回值](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f)|  
  
 在 C# 和 Visual Basic 中，可使用的伪变量如下表所示：  
  
|伪变量|函数|  
|--------------------|--------------|  
|`$exception`|显示有关上一个异常的信息。 如果没有发生异常，则计算 `$exception` 将显示错误消息。<br /><br /> Visual C# 中，禁用异常助手，`$exception`自动添加到**局部变量**窗口时则会发生异常。|  
|`$user`|显示一个结构，在该结构中含有应用程序运行于的帐户的帐户信息。 出于安全原因，将不显示密码信息。|  
  
 在 Visual Basic 中，可使用的伪变量如下表所示：  
  
|伪变量|函数|  
|--------------------|--------------|  
|`$delete` 或 `$$delete`|删除已在中创建的隐式变量**即时**窗口。 语法是`$delete,`*变量*或`$delete,`*变量*`.`|  
|`$objectids` 或 `$listobjectids`|将所有活动对象 ID 显示为指定的表达式的子级。 语法是`$objectid,`*表达式*或`$listobjectids,`*表达式*`.`|  
|`$` *N* `#`|显示对象 ID 等于对象*N*。|  
|`$dynamic`|显示这两个特殊**动态视图**实现的对象的节点`IDynamicMetaObjectProvider`。 接口。 语法是`$dynamic,`*对象*。 此功能仅应用于使用 .NET Framework 版本 4 的代码。 请参阅[动态视图](http://msdn.microsoft.com/library/4c851b17-2c12-46a0-9828-eb6ea6f5c563)。|  
  
## <a name="see-also"></a>请参阅  
 [监视窗口和快速监视 Windows](../debugger/watch-and-quickwatch-windows.md)   
 [变量的 Windows](http://msdn.microsoft.com/library/ce0a67f6-2502-4b7a-ba45-cc32f8aeba3e)





