---
title: ATTACH_REASON |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 08a7a39ba7035e4f5b53a105b2b90d99e958a3a1
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51775493"
---
# <a name="attachreason"></a>ATTACH_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定调试引擎 (DE) 的原因，若要将附加到程序节点。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>成员  
 ATTACH_REASON_AUTO  
 将附加，因为进程当前处于调试模式。  
  
 ATTACH_REASON_LAUNCH  
 将附加，因为启动进程。  
  
 ATTACH_REASON_USER  
 由于用户请求而将附加。  
  
## <a name="remarks"></a>备注  
 这些值用作参数[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)并[附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)

