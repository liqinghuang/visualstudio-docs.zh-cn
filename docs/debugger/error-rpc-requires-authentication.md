---
title: 错误： RPC 要求身份验证 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0bf72110e82fc3cd920f571a5630faafbf2aa5ec
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696527"
---
# <a name="error-rpc-requires-authentication"></a>错误：RPC 要求身份验证
Visual Studio 调试器无法连接到远程计算机。 本地计算机上启用了阻止远程调试的 RPC 策略。

### <a name="to-correct-this-error"></a>更正此错误

1.  运行`\` *windir*`\system32\regedt32.exe`

2.  找到并删除`HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`。

3.  重新启动计算机以使注册表更改生效。

4.  如果问题仍然存在，请联系您的域管理员**计算机配置 > 管理模板 > 系统 > 远程过程调用 > 的未经身份验证的 RPC 客户端限制**组策略设置。