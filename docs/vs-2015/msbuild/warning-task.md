---
title: Warning 任务 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Warning
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Warning task [MSBuild]
- MSBuild, Warning task
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 010ab0d98fa384a7b3a5d18e54a8409d5aa165b2
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "54771915"
---
# <a name="warning-task"></a>Warning 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
基于评估的条件语句，在生成期间记录警告。  
  
## <a name="parameters"></a>参数  
 下表描述了 `Warning` 任务的参数。  
  
|参数|说明​​|  
|---------------|-----------------|  
|`Code`|可选 `String` 参数。<br /><br /> 与警告相关联的警告代码。|  
|`File`|可选 `String` 参数。<br /><br /> 指定相关文件（如果有）。 如果未提供任何文件，则使用包含 Warning 任务的文件。|  
|`HelpKeyword`|可选 `String` 参数。<br /><br /> 与警告关联的 Help 关键字。|  
|`Text`|可选 `String` 参数。<br /><br /> 如果 `Condition` 参数计算结果为 `true`，则为 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 记录的警告文本。|  
  
## <a name="remarks"></a>备注  
 `Warning` 任务使 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 项目可以在继续下一个生成步骤之前，先检查必需的配置或属性是否存在。  
  
 当 `Warning` 任务的 `Condition` 参数的计算结果为 `true` 时，将记录 `Text` 参数的值，并继续执行生成操作。 如果 `Condition` 参数不存在，则记录警告文本。 有关日志记录的详细信息，请参阅[获取生成日志](../msbuild/obtaining-build-logs-with-msbuild.md)。  
  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>示例  
 以下代码示例检查在命令行上设置的属性。 如果未设置任何属性，则项目将引发警告事件，并记录 `Warning` 任务的 `Text` 参数的值。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Warning  
            Text=" The 0 property was not set on the command line."  
            Condition="'$(0)' == ''" />  
        <Warning  
            Text=" The FREEBUILD property was not set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [获取生成日志](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [项目文件架构参考](../msbuild/msbuild-project-file-schema-reference.md)
