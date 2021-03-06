---
title: 调试F#|Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11a310884f9f63264157c96bafc15e8161c0239d
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57323836"
---
# <a name="debugging-f"></a>调试 F\#
调试 F# 与调试任何托管语言类似，但有以下几种例外情况：

-   “自动”窗口不显示 F# 变量。

-   F# 不支持“编辑并继续”。 可以在调试会话期间编辑 F# 代码，但应避免这样做。 因为在调试会话期间无法应用代码更改，所以在调试期间编辑 F# 代码将导致源代码和正在调试的代码出现不匹配。

-   调试器无法识别 F# 表达式。 若要在 F# 调试期间在调试器窗口或对话框中输入表达式，必须将该表达式转换为 C# 语法。 在将 F# 表达式转换为 C# 时，请务必记住 C# 使用 == 作为比较运算符中的等号，而 F# 使用单个 =。

## <a name="see-also"></a>请参阅
- [调试托管代码](../debugger/debugging-managed-code.md)
