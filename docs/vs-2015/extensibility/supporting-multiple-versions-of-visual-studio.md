---
title: 支持多个版本的 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6a15eb606e2415d3a6cd5cf115580c6a0d71e801
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471916"
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>支持多个版本的 Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[支持多个版本的 Visual Studio](https://docs.microsoft.com/visualstudio/extensibility/supporting-multiple-versions-of-visual-studio)。  
  
术语 *-并行*意味着您可以安装和维护多个版本的同一台计算机上的产品。 对 Vspackage，这意味着用户可以有多个 Visual Studio 版本安装在同一台计算机上。 但是，不能具有你的 Vspackage 加载到单个版本的 Visual Studio 的并行的版本。  
  
 使你的 VSPackage 可以被加载到 Visual Studio 的并行版本之前，请考虑以下方面：  
  
-   您必须确定你想要遵循哪个-同时实施策略。  
  
     有关详细信息，请参阅[之间共享选择和版本控制的 Vspackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md)。  
  
-   您的解决方案和项目文件格式必须符合实施策略。  
  
     有关详细信息，请参阅[升级自定义项目](../misc/upgrading-custom-projects.md)并[注册的文件扩展名的并行部署](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)。  
  
-   您的安装程序必须处理实施策略，以便版本化的组件，以及所有版本之间共享的组件正确安装和注册。  
  
     有关详细信息，请参阅[使用 Windows Installer 安装 Vspackage](../extensibility/internals/installing-vspackages-with-windows-installer.md)以及[组件管理](../extensibility/internals/component-management.md)。  
  
    > [!NOTE]
    >  安装版本的 Visual Studio 还会安装相应版本的[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]。 例如，在同一台计算机上安装 Visual Studio 2010 和 Visual Studio 2012 还会安装版本 4.0 和 4.5 的[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]分别。  
  
## <a name="in-this-section"></a>本节内容  
 [选择共享的 VSPackage 或带有版本的 VSPackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md)  
 介绍如何解决你的 VSPackage 中的并行的问题。  
  
 [注册并行部署的文件扩展名](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)  
 描述你的 VSPackage 如何通过并行方案中注册文件关联。  
  
## <a name="related-sections"></a>相关章节  
 [安装 VSPackage](../misc/installing-vspackages.md)  
 讨论如何生成和安装 VSPackage 以及如何支持同时运行多个版本的 Visual Studio 的用户。
