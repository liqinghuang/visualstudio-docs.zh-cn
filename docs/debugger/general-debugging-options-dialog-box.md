---
title: “常规”&gt;“调试”&gt;“选项”对话框 | Microsoft Docs
ms.date: 11/09/2018
ms.topic: reference
f1_keywords:
- vs.debug.options.General
- VS.ToolsOptionsPages.Debugger.General
- VS.ToolsOptionsPages.Debugger.ENC
- vs.debug.options.ENC
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Options dialog box, debugging
ms.assetid: b33aee0b-43c3-4c26-8ed4-bc673f491503
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e97f2f844c53a6bf26fecc4559b65ae69970c6b
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526533"
---
# <a name="general-debugging-options"></a>常规调试选项

若要设置 Visual Studio 调试器选项，选择“工具” > “选项”，在“调试”中选中或取消选中“常规”选项旁边的选择框。 可以通过“工具”  >  “导入和导出设置” > “重置所有设置”恢复所有默认设置。 若要重置设置的子集，在做出要测试的更改之前，使用“导入和导出设置向导”保存设置，然后在以后导入保存的设置。

可以设置以下“常规”选项：

**删除所有断点之前询问**： 需要在完成前的进行确认**删除所有断点**命令。

**一个进程中断时则中断所有进程**： 同时中断调试器附加到，发生都中断时中断所有进程。

**当异常跨越 AppDomain 或托管/本机边界时中断**： 在托管或混合模式调试中，公共语言运行时可以捕获跨越应用程序域边界或托管/本机边界的异常时以下条件成立：

1. 当本机代码使用 COM 互操作调用托管代码且托管代码引发异常。 请参阅 [COM 互操作介绍](/dotnet/articles/visual-basic/programming-guide/com-interop/introduction-to-com-interop)。

2. 应用程序域 1 中运行的托管代码调用应用程序域 2 中的托管代码，且应用程序域 2 中的代码引发异常。 请参阅[应用程序域编程](/dotnet/articles/framework/app-domains/index)。

3. 代码通过使用反射调用一个函数时且该函数引发异常。 请参阅[反射](/dotnet/framework/reflection-and-codedom/reflection)。

在 2 和 3 的情况下，异常有时由 `mscorlib` 中的托管代码而非由公共语言运行时捕获。 此选项不影响在 `mscorlib` 捕获到异常时中断。

**启用地址级调试**： 启用高级功能在地址级上进行调试 (**反汇编**窗口中，**注册**窗口中和地址断点)。

- **如果源不可用时显示反汇编**： 将自动显示**反汇编**窗口时调试的代码的源是为其不可用。

**启用断点筛选器**： 使您能够在断点上设置筛选器，以便他们将影响特定的进程、 线程或计算机。

**使用新的异常帮助器**： 使替换异常助手异常帮助器。 （异常帮助器开始支持在 Visual Studio 2017）

> [!NOTE]
> 对于托管代码，此选项以前称为“启用异常助手”。

**启用仅我的代码**： 调试器显示和指导，用户代码 （"我的代码"） 转换忽略系统代码和其他经过优化或没有调试符号的代码。

- **启动 （仅限托管） 上没有用户代码则发出警告**： 启动调试时启用仅我的代码，此选项会警告你如果没有用户代码 （"我的代码"）。

**启用.NET Framework 源代码单步执行**： 允许调试器单步执行.NET Framework 源代码。 启用此选项会自动禁用“仅我的代码”。 .NET Framework 符号将下载到缓存位置。 使用“选项”对话框>“调试类别”>“符号”页面可更改缓存位置。

**逐过程执行属性和运算符 （仅限托管）**： 使调试器无法单步执行属性和托管代码中的运算符。

**启用属性求值和其他隐式函数调用**： 打开自动求值的属性和隐式函数调用在变量窗口中，**快速监视**对话框。

- **对变量窗口中的对象调用字符串转换函数 (C#仅限和 JavaScript)**： 计算变量窗口中的对象时，执行隐式字符串转换调用。 结果显示为字符串而不是类型名称。 仅在 C# 代码中进行调试时适用。 此设置可能由 DebuggerDisplay 特性重写 (请参阅[使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md))。

**启用源服务器支持**： 告知 Visual Studio 调试器从实现 SrcSrv 源服务器获取源代码文件 (`srcsrv.dll`) 协议。 Team Foundation Server 和 Windows 的调试工具是实现协议的两个源服务器。 有关 SrcSrv 设置的详细信息，请参阅[SrcSrv](/windows-hardware/drivers/debugger/srcsrv)文档。 此外，请参阅[指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)。

> [!IMPORTANT]
> 由于读取 .pdb 文件可在文件中执行任意代码，因此请确保你信任该服务器。

- **源服务器诊断消息打印到输出窗口**： 此设置启用源服务器支持后，会打开诊断显示。

- **允许源服务器中的部分信任程序集 （仅限托管）**： 启用源服务器支持后，此设置将重写不检索的部分信任程序集的源的默认行为。

- **始终运行不受信任的源服务器命令并且不再提示**： 启用源服务器支持后，此设置将重写提示运行不受信任的命令时的默认行为。

**启用源链接支持**： 告知 Visual Studio 调试器，若要下载的源文件 *.pdb*文件包含源链接信息。 有关源链接的详细信息，请参阅[源链接规范](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/source_link.md)。

> [!IMPORTANT]
>  由于源链接将使用 http 或 https 下载文件，因此请确保你信任该 .pdb 文件。

- **故障回复到 Git 凭据管理器身份验证的所有源链接请求**： 时源链接支持已启用，并且源链接请求失败身份验证，Visual Studio，然后调用 Git 凭据管理器。

**突出显示整个行的断点和当前语句 （c + +）**： 时调试器突出显示断点或当前语句，它会突出显示整个行。

**要求源文件与完全匹配的原始版本**： 指示调试器验证源文件与用于生成正在调试的可执行文件的源代码的版本相匹配。 若版本不匹配，系统会提示你查找匹配的源。 如果未找到匹配源，则在调试过程中不会显示源代码。

**将所有输出窗口文本重都定向到即时窗口**： 发送的所有调试器消息将通常显示在**输出**到窗口**即时**窗口相反。

**变量窗口中显示对象的原始结构**： 关闭所有对象结构视图自定义项。 有关视图自定义的详细信息，请参阅[创建 .managed 对象的自定义视图](../debugger/create-custom-views-of-dot-managed-objects.md)。

**在模块加载 （仅限托管） 取消 JIT 优化**： 时加载的模块并编译 JIT 后附加调试器时禁用托管代码的 JIT 优化。 禁用优化可能更易于调试某些问题，尽管这会降低性能。 如果正在使用“仅我的代码”，则取消 JIT 优化会导致非用户代码显示为用户代码（“我的代码”）。 有关详细信息，请参阅[JIT 优化和调试](../debugger/jit-optimization-and-debugging.md)。

**启用 JavaScript 调试 （Chrome、 Edge 和 IE） 的 asp.net**： 启用脚本调试程序对 ASP.NET 应用程序。 第一次在 Chrome 中使用时，可能需要登录到浏览器来启用已安装的 Chrome 扩展。 禁用此选项可还原为旧行为。

**适用于 UWP JavaScript 应用 （实验性） 启用 Edge 开发人员工具**： 启用适用于 UWP JavaScript 应用在 Edge 中开发人员工具。

**启用旧版 Chrome JavaScript 调试器 asp.net**： 启用旧版 Chrome JavaScript 脚本调试器对 ASP.NET 应用程序。 第一次在 Chrome 中使用时，可能需要登录到浏览器来启用已安装的 Chrome 扩展。

**使用启动 Chrome JavaScript 调试时以管理员身份运行 Visual Studio 的实验性方法**： 告知 Visual Studio 尝试在 JavaScript 调试期间启动 Chrome 的新方法。

**加载 dll 导出 （仅限本机）**： 加载 dll 导出表。 处理 Windows 消息、Windows 过程 (WindowProc)、COM 对象、封送或不具有其符号的任何 DLL 时，DLL 导出表中的符号信息将很有用。 读取 DLL 导出信息会占用一些系统开销。 因此，默认情况下此功能被禁用。

若要查看 DLL 导出表中的可用符号，请使用 `dumpbin /exports`。 符号可用于任何 32 位系统 DLL。 从 `dumpbin /exports` 输出中，可以查看到精确的函数名，包括非字母数字字符。 这对于在函数上设置断点很有用。 DLL 导出表中的函数名在调试器的其他位置似乎被截断了。 调用将按调用顺序列出，当前函数（嵌套最深的函数）位于顶端。 有关详细信息，请参阅 [dumpbin /exports](/cpp/build/reference/dash-exports)。

**显示并行堆栈关系图自下而上**： 控制在其中堆栈中的显示的方向**并行堆栈**窗口。

**如果写入的数据未更改值，则忽略 GPU 内存访问异常**： 将忽略的数据未更改调试期间检测到的争用条件。 有关详细信息，请参阅[调试 GPU 代码](../debugger/debugging-gpu-code.md)。

**使用托管兼容模式**： 替换默认调试引擎以实现这些方案为旧版本：

- 使用 C#、Visual Basic 或 F# 以外的 .NET Framework 语言，该语言提供自己的表达式计算器（包括 C + + CLI）。

- 想要在混合模式调试过程中为 C++ 项目启用“编辑并继续”。

> [!NOTE]
> 选择托管兼容模式会禁用仅在默认调试引擎中实现某些功能。 在 Visual Studio 2012 中取代旧调试引擎。

**使用旧C#和 VB 表达式计算器**： 调试器将使用 Visual Studio 2013C#或 Visual Basic 表达式计算器而不是基于 Visual Studio 2015 Roslyn 的表达式计算器。

**使用自定义调试器可视化工具可能不安全进程 （仅限托管） 时，则发出警告**: Visual Studio 会警告你，在使用正在调试的进程中运行代码的自定义调试器可视化工具，因为它可能在运行时不安全代码。

**启用 Windows 调试堆分配器 （仅限本机）**： 启用 windows 调试堆以改进堆诊断。 启用此选项会影响调试性能。

**启用 XAML 的 UI 调试工具**： 在开始调试时，将显示实时可视化树和实时属性资源管理器窗口 (**F5**) 支持的项目类型。 有关详细信息，请参阅[调试时检查 XAML 属性](../debugger/inspect-xaml-properties-while-debugging.md)。

- **预览实时可视化树中的所选的元素**： 选择其上下文的 XAML 元素也会选中**实时可视化树**窗口。

- **在应用程序中显示运行时工具**： 显示了**实时可视化树**在正在调试的 XAML 应用程序的主窗口工具栏中的命令。 Visual Studio 2015 Update 2 中引入了此选项。

- **启用 XAML 编辑并继续**： 允许您使用编辑并继续使用 XAML 代码的功能。

**调试时启用诊断工具**:**诊断工具**进行调试时显示窗口。

**调试时显示运行时间 PerfTip**： 在调试时，代码窗口会显示给定的方法调用的已用时间。

**启用编辑并继续**： 调试时启用编辑并继续功能。

- **启用本机编辑并继续**： 你可以使用编辑并继续调试本机 c + + 代码时的功能。 有关详细信息，请参阅[编辑并继续 (Visual C++)](../debugger/edit-and-continue-visual-cpp.md)。

- **将更改应用在继续 （仅限本机）**: Visual Studio 会自动编译并应用从中断状态继续该过程时所做的任何未完成的代码更改。 可选择使用“调试”菜单下的“应用代码更改”项来应用更改（如果尚未选择）。

- **就陈旧的代码 （仅限本机），则发出警告**： 收到关于陈旧代码警告。

**显示运行到单击按钮在编辑器中进行调试时**： 选中此选项后，[运行时单击](debugger-feature-tour.md#run-to-a-point-in-your-code-quickly-using-the-mouse)调试时，将会显示按钮。

**调试停止时自动关闭控制台**： 告知 Visual Studio 调试会话结束时关闭控制台。

## <a name="options-available-in-older-versions-of-visual-studio"></a>较旧版本的 Visual Studio 中的可用选项

如果你使用 Visual Studio 的较旧版本，可能会出现一些其他选项。

**启用异常助手**： 对于托管代码中，会启用异常助手。 从 Visual Studio 2017 中，异常帮助器替换为异常助手。

**展开调用堆栈上未经处理的异常**： 将导致**调用堆栈**窗口调用堆栈回滚到点之前发生了未经处理的异常。

**启动时 （仅限本机） 的无符号则发出警告**： 当调试调试程序没有对应符号信息为其的程序时显示一个警告对话框。

**如果在启动禁用脚本调试，则发出警告**： 禁用了脚本调试启动调试器时显示一个警告对话框。

**使用本机兼容模式**： 选中此选项后，调试器使用 Visual Studio 2010 本机调试器而不是新的本机调试器。

- 如果正在调试 .NET C++ 代码，请使用此选项，因为新的调试引擎不支持计算 .NET C++ 表达式。 但是，启用本机兼容模式会禁用依赖于当前调试器实现来操作的许多功能。 例如，旧引擎缺少许多用于内置类型（如 Visual Studio 2015 项目中的 `std::string`）的可视化工具。   为获得最佳调试体验，在这些应用场景中请使用 Visual Studio 2013 项目。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中进行调试](../debugger/index.md)
- [调试器功能简介](../debugger/debugger-feature-tour.md)