---
title: 调试实时 ASP.NET Azure 虚拟机和 Azure 虚拟机规模集
description: 了解如何设置吸附点和查看快照调试程序的快照。
ms.custom: ''
ms.date: 02/06/2019
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: poppastring
ms.author: madownie
manager: andster
monikerRange: '>= vs-2019'
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 608745fc2c96836163e1406abda6869d52b1da1b
ms.sourcegitcommit: 62149c96de0811415e99bb1e0194e76c320e1a1e
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "57007263"
---
# <a name="debug-live-aspnet-apps-on-azure-virtual-machines-and-azure-virtual-machine-scale-sets-using-the-snapshot-debugger"></a>调试 Azure 虚拟机上的实时 ASP.NET 应用和 Azure 虚拟机规模集使用快照调试程序

Snapshot Debugger 会在你感兴趣的代码执行时为生产中的应用拍摄快照。 若要指示该调试器拍摄快照，可以在代码中设置快照点和记录点。 通过该调试器，可精确查看出错的内容，而不会影响生产应用程序的流量。 Snapshot Debugger 有助于大幅减少解决生产环境中出现的问题所需的时间。

快照点和记录点类似于断点，但与断点不同的是，快照点不会在命中时停止应用程序。 通常，在快照点捕获快照需要 10-20 毫秒。

在本教程中，你将：

> [!div class="checklist"]
> * 启动快照调试器
> * 设置快照点，以及查看快照
> * 设置记录点

## <a name="prerequisites"></a>系统必备

* Azure 虚拟机 (VM) 和 Azure 虚拟机规模集 (VMSS) 的快照调试程序是仅适用于 Visual Studio 2019 Enterprise 预览版或更高版本与**Azure 开发工作负荷**。 (下**各个组件**选项卡上，您发现下**调试和测试** > **快照调试程序**。)

    如果尚未安装，安装[Visual Studio 2019 Enterprise 预览版](https://visualstudio.microsoft.com/vs/preview/)。

* 快照集合是适用于以下的 Azure VM/VMSS web 应用：
  * 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
  * 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>打开你的项目并启动快照调试器

1. 打开你想要快照调试的项目。

    > [!IMPORTANT]
    > 您需要打开到快照调试*相同版本的源代码*，它发布到 Azure VM/VMSS 服务。

1. 附加 Snapshot Debugger。 可以使用多种不同的方法之一：

    * 选择**调试 > 附加 Snapshot Debugger...**.选择你的 web 应用部署到 Azure VM/VMSS 和 Azure 存储帐户，然后依次**附加**。

      ![启动快照调试程序从调试菜单](../debugger/media/snapshot-debug-menu-attach.png)

    * 右键单击项目，然后选择**发布**，然后在发布页上，单击**附加 Snapshot Debugger**。 选择你的 web 应用部署到 Azure VM/VMSS 和 Azure 存储帐户，然后依次**附加**。
    ![启动快照调试程序与发布页](../debugger/media/snapshot-publish-attach.png)

    * 在调试目标下拉列表菜单中选择**快照调试器**、 命中**F5** ，然后如果需要选择你的 web 应用部署到 Azure VM/VMSS 和 Azure 存储帐户，然后依次**附加**。
    ![启动快照调试程序与 F5 下拉列表菜单](../debugger/media/snapshot-F5-dropdown-attach.png)

    * 使用云资源管理器 (**视图 > 云资源管理器**)，右键单击你的 web 应用部署到 Azure VM/VMSS 和选择 Azure 存储帐户，然后单击**附加 Snapshot Debugger**。

      ![启动快照调试程序与云资源管理器](../debugger/media/snapshot-launch.png)

    > [!IMPORTANT]
    > 选择第一次**附加 Snapshot Debugger** vm，会自动重新启动 IIS。
    > 选择第一次**附加 Snapshot Debugger**在 vmss，需要手动升级每个 VMSS 实例。

    元数据**模块**最初不会激活，导航到 web 应用和**开始收集**按钮将激活。 Visual Studio 现在处于快照调试模式下。

    > [!NOTE]
    > Application Insights 站点扩展还支持快照调试。 如果你遇到的"站点扩展已过期"错误消息，请参阅[故障排除提示和已知的问题的快照调试](../debugger/debug-live-azure-apps-troubleshooting.md)升级的详细信息。
    > VMSS 的用户时需要在其 VMSS 实例手动升级后首次连接 Snapshot Debugger。

   ![快照调试模式](../debugger/media/snapshot-message.png)

   **模块**窗口中显示时的所有模块已都加载的 Azure VM/VMSS (选择**调试 > Windows > 模块**要打开此窗口)。

   ![检查模块窗口](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>设置快照点

1. 在代码编辑器中，单击你感兴趣的代码行旁边的左滚动条槽以设置快照点。 请确保它是你已知将执行的代码。

   ![设置快照点](../debugger/media/snapshot-set-snappoint.png)

1. 单击“开始收集”以打开快照点。

   ![开启快照点](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > 查看快照时，不能执行步骤，但可以在代码中放置多个快照点以在不同代码行处跟进执行。 如果代码中有多个快照点，快照调试器可以确保对应的快照来自相同的最终用户会话。 即使有多个用户点击应用，快照调试器仍会执行此操作。

## <a name="take-a-snapshot"></a>获取快照

启用快照点后，它将在快照点所在的代码行执行时捕获快照。 此执行可能由服务器上的实际请求引起。 若要强制命中快照点，请转到网站的浏览器视图，并执行命中快照点所需的任何操作。

## <a name="inspect-snapshot-data"></a>检查快照数据

1. 命中快照点时，快照将出现在诊断工具窗口。 若要打开此窗口，请依次选择“调试”>“窗口”>“显示诊断工具”。

   ![打开快照点](../debugger/media/snapshot-diagsession-window.png)

1. 双击快照点，以在代码编辑器中打开快照。

   ![检查快照数据](../debugger/media/snapshot-inspect-data.png)

   在此视图中，可通过将鼠标悬停在变量上来查看数据提示；使用“局部变量”、“监视”和“调用堆栈”窗口；以及计算表达式。

    网站本身仍然是实时的，最终用户不会受到影响。 默认情况下，每个快照点只捕获一个快照：快照点在捕获快照后即关闭。 如果要在此快照点再捕获一个快照，可以通过单击“更新集合”来重新打开快照点。

还可以向应用添加更多快照点，并使用“更新集合”按钮将其启动。

**需要帮助？** 请参阅[疑难解答和已知的问题](../debugger/debug-live-azure-apps-troubleshooting.md)并[快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)页。

## <a name="set-a-conditional-snappoint"></a>设置条件性快照点

如果难以在应用中重新创建某一特定状态，请考虑使用条件性快照点是否会有所帮助。 条件性快照点可帮助避免在应用进入所需状态前获取快照，例如，变量具有你想要检查的特定值的情况。 可以使用表达式、筛选器或命中次数设置表达式。

#### <a name="to-create-a-conditional-snappoint"></a>若要创建条件的吸附点

1. 右键单击吸附点图标 （空心球），然后选择**设置**。

   ![选择“设置”](../debugger/media/snapshot-snappoint-settings.png)

1. 在吸附点设置窗口中，键入一个表达式。

   ![键入一个表达式](../debugger/media/snapshot-snappoint-conditions.png)

   在上图中，仅拍摄快照的吸附点时`visitor.FirstName == "Dan"`。

## <a name="set-a-logpoint"></a>设置记录点

除了在命中吸附点时，拍摄快照，还可以配置吸附点将消息记录 （即，创建记录点）。 您可以设置个记录点，而无需重新部署您的应用程序。 记录点几乎执行，并会导致没有影响或负面影响到你正在运行的应用程序。

#### <a name="to-create-a-logpoint"></a>若要创建的记录点

1. 右键单击吸附点图标 （蓝色六边形），然后选择**设置**。

1. 在吸附点设置窗口中，选择**操作**。

    ![创建记录点](../debugger/media/snapshot-logpoint.png)

1. 在中**消息**字段中，可以输入想要记录新的日志消息。 您也可以通过将它们放在大括号内将日志消息中计算变量。

    如果愿意**将发送到输出窗口**，当命中记录点，请在诊断工具窗口中将显示该消息。

    ![Diagsession 窗口中的记录点数据](../debugger/media/snapshot-logpoint-output.png)

    如果愿意**发送到应用程序日志**，当命中记录点，请任意位置，您可以看到消息从出现的消息`System.Diagnostics.Trace`(或`ILogger`.NET Core 中)，如[App Insights](/azure/application-insights/app-insights-asp-net-trace-logs)。

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何为 Azure 虚拟机和 Azure 虚拟机规模集使用快照调试程序。 您可能想要阅读有关此功能的更多详细信息。

> [!div class="nextstepaction"]
> [快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)