---
title: 目录状态代码枚举器 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6a23bef10dda57d761ce7f07c3b87808b021830c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51766665"
---
# <a name="directory-status-code-enumerator"></a>目录状态代码枚举器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`SccDirStatus`枚举数包含命名的常量值用于指定源代码管理系统中的目录的状态。 此枚举由[SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)。 这是在源控件插件 API 版本 1.2 中引入的。  
  
## <a name="syntax"></a>语法  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>成员  
 SCC_DIRSTATUS_INVALID  
 无法获取状态;不依赖于它。  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 目录不是源代码管理下。  
  
 SCC_DIRSTATUS_CONTROLLED  
 目录位于源控件下。  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 对此目录相对应的项目为空。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)

