---
title: 教程：Visual Basic 入门
description: 了解如何在 Visual Studio 中逐步创建 Visual Basic 控制台应用。
ms.custom: seodec18, get-started
ms.date: 08/10/2018
ms.technology: vs-ide-general
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: a190a17147530fe42cd6bb9e95b313527eb16b0d
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840409"
---
# <a name="tutorial-get-started-with-visual-basic-in-visual-studio"></a>教程：Visual Studio 中的 Visual Basic 入门

在本 Visual Basic (VB) 教程中，你将使用 Visual Studio 创建和运行几个不同的控制台应用，并在执行这些操作时了解 [Visual Studio 集成开发环境 (IDE)](visual-studio-ide.md) 的部分功能。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)页免费安装。

## <a name="create-a-project"></a>创建项目

首先，创建一个 Visual Basic 应用程序项目。 项目类型随附了所需的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

3. 在“新建项目”对话框左侧的窗格中，展开“Visual Basic”，然后选择“.NET Core”。 在中间窗格中，选择“控制台应用(.NET Core)”。 随后将文件命名为 HelloWorld。

   ![Visual Studio IDE 中“新建项目”对话框中的控制台应用 (.NET Core) 项目模板](media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

### <a name="add-a-workload-optional"></a>添加工作负载（可选）

如果未显示“控制台应用(.NET Core)”项目模板，可通过添加“.NET Core 跨平台开发”工作负载获取它。 可通过以下两种方式添加此工作负载，具体取决于计算机上安装的 Visual Studio 2017 更新。

#### <a name="option-1-use-the-new-project-dialog-box"></a>选项 1：使用“新建项目”对话框

1. 单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。

   ![单击“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](../media/vs-open-visual-studio-installer-generic.png)

1. Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

   ![Visual Studio 安装程序中的 .NET Core 跨平台开发工作负荷](../media/tutorial-aspnet-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>选项 2：使用“工具”菜单栏

1. 取消“新建项目”对话框，再依次选择顶部菜单栏中的“工具” > “获取工具和功能”。

1. Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

## <a name="create-a-what-is-your-name-application"></a>创建一个“What Is Your Name”应用程序

创建一个应用，它会提示你输入名字，然后将名字随日期和时间一起显示。 操作方法如下：

1. 打开 WhatIsYourName 项目（如果尚未打开）。

1. 立即在 `Sub Main(args As String())` 行后的左括号和 `End Sub` 行之间，输入以下 Visual Basic 代码：

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    此代码替换现有的 <xref:System.Console.WriteLine%2A>、<xref:System.Console.Write%2A> 和 <xref:System.Console.ReadKey%2A> 语句。

   ![显示“What Is Your Name”代码的代码窗口](media/vb-codewindow-what-name.png)

1. 控制台窗口打开时，输入名字。 控制台窗口应如以下屏幕快照所示：

   ![显示“What Is Your Name”、时间和日期以及“按任意键继续”消息的控制台窗口](media/vb-console-what-name.png)

1. 按任意键关闭控制台窗口。

## <a name="create-a-calculate-this-application"></a>创建“Calculate This”应用程序

1. 打开 Visual Studio 2017，然后在顶部菜单栏中，选择“文件” > “新建” > “项目”。

1. 在“新建项目”对话框左侧的窗格中，展开“Visual Basic”，然后选择“.NET Core”。 在中间窗格中，选择“控制台应用(.NET Core)”。 然后将文件命名为 CalculateThis。

1. 在 `Module Program` 行和 `End Module` 行之间输入以下代码：

   ```vb
   Public num1 As Integer
   Public num2 As Integer
   Public answer As Integer
   Sub Main()
       Console.WriteLine("Type a number and press Enter")
       num1 = Console.ReadLine()
       Console.WriteLine("Type another number to add to it and press Enter")
       num2 = Console.ReadLine()
       answer = num1 + num2
       Console.WriteLine("The answer is " & answer)
       Console.ReadLine()
   End Sub
   ```

   代码窗口应如以下屏幕截图所示：

   ![显示“Calculate This”代码的代码窗口](media/vb-codewindow-calculate-this.png)

1. 单击“CalculateThis”运行程序。 控制台窗口应如以下屏幕快照所示：

    ![显示“CaluculateThis”应用的控制台窗口，其中包括要执行的操作的相应提示。](media/vb-console-calculate-this.png)

## <a name="quick-answers-faq"></a>快速解答常见问题

下面是一个快速 FAQ，突出介绍了一些关键概念。

### <a name="what-is-visual-basic"></a>什么是 Visual Basic？

Visual Basic 是一种易于学习的类型安全编程语言。 它派生自 BASIC，BASIC 的意指“初学者通用符号指令代码”。

### <a name="what-is-visual-studio"></a>什么是 Visual Studio？

Visual Studio 是适用于开发人员的生产力工具集成开发套件。 可将其视为可用于创建程序和应用程序的程序。

### <a name="what-is-a-console-app"></a>什么是控制台应用？

控制台应用获取输入，在命令行窗口（也称为 控制台）中显示输出。

### <a name="what-is-net-core"></a>.NET Core 是什么？

.NET Core 是 .NET Framework 的进一步演化。 .NET Framework 允许跨编程语言共享代码，而 .NET Core 增加了跨平台共享代码的功能。 此外，它还为开放源。 （.NET Framework 和 .NET Core 都包含预生成功能的库以及公共语言运行时 (CLR)，公共语言运行时充当用于运行代码的虚拟机。）

## <a name="next-steps"></a>后续步骤

恭喜你完成本教程！ 若要更深入地了解，请参阅以下教程。

> [!div class="nextstepaction"]
> [在 Visual Studio 中使用 Visual Basic 和 .NET Core SDK 生成库](/dotnet/core/tutorials/vb-library-with-visual-studio)

## <a name="see-also"></a>请参阅

* [Visual Basic 语言演练](/dotnet/visual-basic/walkthroughs)
* [Visual Basic 语言参考](/dotnet/visual-basic/language-reference/index)
* [Visual Basic 代码文件的 IntelliSense](../../ide/visual-basic-specific-intellisense.md)
