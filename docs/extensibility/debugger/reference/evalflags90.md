---
title: EVALFLAGS90 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 73673d0b0ca7ccb640a3fab2043bc35b26657a9b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720297"
---
# <a name="evalflags90"></a>EVALFLAGS90
枚举的有效值的控制表达式求值的标志。 此枚举扩展[EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)枚举。

## <a name="syntax"></a>语法

```cpp
enum enum_EVALFLAGS90
{
    // VS 8.0 values
    EVAL90_RETURNVALUE                 = 0x0002,
    EVAL90_NOSIDEEFFECTS               = 0x0004,
    EVAL90_ALLOWBPS                    = 0x0008,
    EVAL90_ALLOWERRORREPORT            = 0x0010,
    EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,
    EVAL90_NOFUNCEVAL                  = 0x0080,
    EVAL90_NOEVENTS                    = 0x1000,
    EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,
    EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,

    // Values added in VS 9.0
    EVAL90_FORCE_EVALUATION_NOW        = 0x8000
};
typedef DWORD EVALFLAGS90;
```

```csharp
public enum enum_EVALFLAGS90
{
    // VS 8.0 values
    EVAL90_RETURNVALUE                 = 0x0002,
    EVAL90_NOSIDEEFFECTS               = 0x0004,
    EVAL90_ALLOWBPS                    = 0x0008,
    EVAL90_ALLOWERRORREPORT            = 0x0010,
    EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,
    EVAL90_NOFUNCEVAL                  = 0x0080,
    EVAL90_NOEVENTS                    = 0x1000,
    EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,
    EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,

    // Values added in VS 9.0
    EVAL90_FORCE_EVALUATION_NOW        = 0x8000
};
```

#### <a name="parameters"></a>参数
EVAL90_RETURNVALUE 指定的计算返回值，如果有的话。

EVAL90_NOSIDEEFFECTS 指定不允许副作用。

EVAL90_ALLOWBPS 指定在断点停止。

EVAL90_ALLOWERRORREPORT 指定报告到主机，以允许该错误。 主要用于在 Internet Explorer 中的脚本中的表达式计算。

EVAL90_FUNCTION_AS_ADDRESS 强制函数计算结果为地址，而不是调用该函数。

评估 EVAL90_NOFUNCEVAL 阻止函数。 例如，考虑`int`令牌在表达式中`myExpression(int) + 10`。 为地址，但不能作为一个值，此函数可以正确评估。

EVAL90_NOEVENTS 标志以指示会话调试管理器 (SDM) 或 IDE 未发送的表达式计算期间发生的事件。

EVAL90_DESIGN_TIME_EXPR_EVAL 使设计时表达式计算。

EVAL90_ALLOW_IMPLICIT_VARS 允许隐式变量创建。

EVAL90_FORCE_EVALUATION_NOW 强制立即进行计算。 当请求，如用户请求提供服务时，这很有用。

## <a name="requirements"></a>要求
标头：Msdbg90.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
