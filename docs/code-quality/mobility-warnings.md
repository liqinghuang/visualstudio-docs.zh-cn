---
title: 移动性警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.MobilityRules
helpviewer_keywords:
- managed code analysis warnings, mobility warnings
- mobility warnings
- warnings, mobility
ms.assetid: 9808054c-593b-4fc3-92cc-1fc45f41569c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 170caf52999fb687c040c2e9212d1a1ed2e154a0
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55908409"
---
# <a name="mobility-warnings"></a>移动性警告
移动性警告支持高效使用电源。

## <a name="in-this-section"></a>本节内容

|规则|描述|
|----------|-----------------|
|[CA1600:不要使用 idle 进程优先级](../code-quality/ca1600-do-not-use-idle-process-priority.md)|不要将进程优先级设置为 Idle。 具有 System.Diagnostics.ProcessPriorityClass.Idle 优先级的进程将在 CPU 本应处于空闲状态时占用它，从而阻止进入待机状态。|
|[CA1601:不要使用阻止电源状态更改的计时器](../code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes.md)|频率较高的定期活动会使 CPU 处于繁忙状态，并且会干扰具有节能功能（关闭显示器和硬盘）的空闲计时器。|