---
title: 关闭 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b9b8848399ea88b5f4ce7ebf30f970e2091e6406
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "54784594"
---
# <a name="shutdown"></a>关闭
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

“关闭”选项会等待任何当前分析的进程结束或分离，然后关闭探查器和分析数据文件。 “关闭”选项必须是分析运行的最后一个命令。  
  
 如果没有指定超时参数，则“关闭”选项将无限期等待。 如果指定了超时参数，则此选项将在指定的秒数后返回，而不会关闭探查器或数据文件。  
  
 “关闭”选项必须是命令行中指定的唯一选项。  
  
## <a name="syntax"></a>语法  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>参数  
 `Timeout`  
 -   （可选）如果指定，则此选项将在指定的秒数后返回，而不会关闭探查器或分析数据文件。  
  
## <a name="see-also"></a>请参阅  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [分析独立应用程序](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [分析 ASP.NET Web 应用程序](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [分析服务](../profiling/command-line-profiling-of-services.md)
