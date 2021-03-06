---
title: “选项”对话框、项目和解决方案、生成和运行 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0aa325aa016b95a0dac0047f4b6fe9ae67f52ecc
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54800857"
---
# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>选项对话框，项目和解决方案，生成和运行
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
在此对话框中，可以指定可同时生成的 Visual C++ 或 Visual C# 项目的最大数量、某些默认生成行为及一些生成日志设置。 若要打开“选项”对话框中，依次选择菜单栏上的“工具”、“选项”。 若要访问此组选项，请展开“项目和解决方案”，然后选择“生成并运行”。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **最大并行项目生成数**  
 指定可以同时生成的 Visual C++ 和 Visual C# 项目的最大数量。 若要优化生成过程，最大并行项目生成数自动设置为你的计算机的 CPU 数量。 最大数量为 32。  
  
 **在运行时仅生成启动项目和依赖项**  
 如果在选择 F5 键时选中了此复选框，则将仅生成启动项目及其依赖项；依次选择菜单栏上的“调试”、“启动”；或者依次选择菜单栏上的“生成”、“生成”。 如果在选择 F5 键时清楚了此复选框，则将生成所有项目、依赖项和解决方案文件；依次选择菜单栏上的“调试”、“启动”；或者依次选择菜单栏上的“生成”、“生成”。 默认情况下清除此选项。  
  
 **运行期间，当项目过期时**  
 > [!NOTE]
>  此列表仅适用于 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 项目。  
  
 默认情况下，如果在选择 F5 键或在菜单栏上依次选择“调试”、“启动”时，项目配置已过期，则将显示一条消息。 你可以指定是否仍要生成项目以及是否显示消息。 此选项用于指定是否将显示消息以及不显示消息时的生成行为。  
  
 **始终生成**  
 未出现此消息框，并且尽管有过期配置，仍生成项目。 于在消息中选择“不再显示此对话框”框，然后选择“是”按钮时，设置此选项。  
  
 **从不生成**  
 未出现此消息框，且未生成项目。 于在消息中选择“不再显示此对话框”框，然后选择“否”按钮时，设置此选项。  
  
 **提示生成**  
 每当项目配置过期时显示此消息框。  
  
 **运行期间，当出现生成或部署错误时**  
 如果从“生成”菜单启动生成时出现生成错误，则将显示一条消息。 您可以指定是否要继续通过启动该应用程序和该消息将显示每次生成错误发生。 此选项用于指定是否将显示消息以及不显示消息时的行为。  
  
> [!NOTE]
>  此选项仅适用于 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 项目。  
  
 **提示启动**  
 在每次出现生成错误时显示一个消息框。  
  
 **不启动**  
 未出现此消息框，且未启动应用程序。 于在消息框中选择“不再显示此对话框”复选框，然后选择“否”按钮时，设置此选项。  
  
 **启动早期版本**  
 未出现此消息框，且未启动应用程序的新生成版本。 于在消息框中选择“不再显示此对话框”复选框，然后选择“是”按钮时，设置此选项。  
  
 **对于新解决方案，使用当前选定的项目作为启动项目**  
 如果选中该复选框，则新解决方案将当前选择的项目用作启动项目。  
  
 **MSBuild 项目生成输出详细信息**  
 确定出现在生成的“输出”窗口中的信息数。  
  
 **MSBuild 项目生成日志文件详细信息**  
 > [!NOTE]
>  此选项仅适用于 Visual C++ 项目。  
  
 确定写入到生成日志文件中的信息数，该文件位于 \\...\\ProjectName\Debug\\ProjectName.log。  
  
## <a name="see-also"></a>请参阅  
 [编译和生成](../../ide/compiling-and-building-in-visual-studio.md)
