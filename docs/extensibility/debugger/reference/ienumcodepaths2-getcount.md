---
title: IEnumCodePaths2::GetCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCodePaths2::GetCount
helpviewer_keywords:
- IEnumCodePaths2::GetCount
ms.assetid: 988c5092-fcc5-43a1-a94c-c261edd56ebf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9059a080d9d128517f636b00a7a8b285c5be1dc9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688493"
---
# <a name="ienumcodepaths2getcount"></a>IEnumCodePaths2::GetCount
枚举中返回元素的数。

## <a name="syntax"></a>语法

```cpp
HRESULT GetCount(
   ULONG* pcelt
);
```

```csharp
int GetCount(
   out uint pcelt
);
```

#### <a name="parameters"></a>参数
 `pcelt`

 [out]枚举中返回元素的数。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法不是惯用的 COM 枚举接口，只有指定的一部分`Next`， `Clone`， `Skip`，和`Reset`方法需要实现。

## <a name="see-also"></a>请参阅
- [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)