---
title: IDebugObject::GetValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetValue
helpviewer_keywords:
- IDebugObject::GetValue method
ms.assetid: eec6051e-8ecb-49fa-bdd4-dd786f211692
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8d8b55fed250b94fc02c9810eca17ec0934bf81e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690729"
---
# <a name="idebugobjectgetvalue"></a>IDebugObject::GetValue
获取对象的值作为一系列连续的字节数。

## <a name="syntax"></a>语法

```cpp
HRESULT GetValue( 
   BYTE* pValue,
   UINT  nSize
);
```

```csharp
int GetValue(
   ref byte[] pValue,
   uint nSize
);
```

#### <a name="parameters"></a>参数
 `pValue`

 [in、 out]使用一系列连续的字节数表示的对象的值填充数组。

 `nSize`

 [in]要提取的字节数目上限。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 获取可以通过调用提取的值字节总数[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)方法。

## <a name="see-also"></a>请参阅
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)