---
title: IDebugFunctionObject2::CreateObject |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugFunctionObject2::CreateObject
- CreateObject
ms.assetid: 148de615-941e-4b64-ab11-75b692aae465
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7004e57aaf659b90b5323105c6d2c2b80baa4d0f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723118"
---
# <a name="idebugfunctionobject2createobject"></a>IDebugFunctionObject2::CreateObject
创建使用给定评估标志设置和超时值的构造函数的对象。

## <a name="syntax"></a>语法

```cpp
HRESULT CreateObject (
   IDebugFunctionObject* pConstructor,
   DWORD                 dwArgs,
   IDebugObject*         pArgs[],
   DWORD                 dwEvalFlags,
   DWORD                 dwTimeout,
   IDebugObject**        ppObject
);
```

```csharp
int CreateObject (
   IDebugFunctionObject pConstructor,
   uint                 dwArgs,
   IDebugObject[]       pArgs,
   uint                 dwEvalFlags,
   uint                 dwTimeout,
   out IDebugObject**   ppObject
);
```

#### <a name="parameters"></a>参数
 `pConstructor`

 [in][IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)对象，表示要创建的对象的构造函数。

 `dwArgs`

 [in]中的参数数量`pArg`数组。 表示传递给构造函数的参数数目。

 `pArgs`

 [in]一个数组[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示的参数的对象传递给构造函数。

 `dwEvalFlags`

 [in]中的标志的组合[EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)指定计算的执行方式的枚举。

 `dwTimeout`

 [in]最大时间 （毫秒），此方法返回前等待。 使用**无限**无限期等待。

 `ppObject`

 [out]返回**IDebugObject**表示新创建的对象。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 调用此方法以创建一个对象，表示一个类或其他复杂类型，它需要是一个参数的构造函数的实例。

## <a name="see-also"></a>请参阅
- [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)