---
title: 调试 HTML 和 CSS 示例代码 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 51893967-98c8-4141-ba40-03646f221760
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7f5ec540fe2454c0e5b31c93002c099f7a54388a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697762"
---
# <a name="debug-html-and-css-sample-code"></a>调试 HTML 和 CSS 示例代码

本主题中的代码是示例文件[快速入门： 调试 HTML 和 CSS](../debugger/quickstart-debug-html-and-css.md)。 此版本的代码中修复了快速入门中有意出现的错误。

## <a name="sample-code"></a>代码示例
快速入门中的 \<body> 标记中使用了以下 HTML 代码。

```html
<div id="flipTemplate" data-win-control="WinJS.Binding.Template"
         style="display:none">
    <div class="fixedItem" >
        <img src="#" data-win-bind="src: flipImg" />
    </div>
</div>
<div id="fView" data-win-control="WinJS.UI.FlipView" data-win-options="{
    itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">
</div>
```

以下 CSS 显示了在 default.css 中增加的代码。

```css
#fView {
    background-color:#0094ff;
    height: 500px;
    margin: 25px;
}
```

以下代码示例展示了 default.js 中的完整 JavaScript 代码。 对此代码的 WinJS 命名空间的引用位于模板的 default.html 文件中。

```javascript
(function () {
    "use strict";

    var app = WinJS.Application;
    var activation = Windows.ApplicationModel.Activation;

    var myData = [];
    for (var x = 0; x < 3; x++) {
        myData[x] = { flipImg: "/images/logo.png" }
    };

    var pages = new WinJS.Binding.List(myData, { proxy: true });

    app.onactivated = function (args) {
        if (args.detail.kind === activation.ActivationKind.launch) {
            if (args.detail.previousExecutionState !==
            activation.ApplicationExecutionState.terminated) {
                // TODO: . . .
            } else {
                // TODO: . . .
            }
            args.setPromise(WinJS.UI.processAll());

            updateImages();
        }
    };

    function updateImages() {

        pages.setAt(0, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });
        pages.setAt(1, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg" });
        pages.setAt(2, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg" });
    };

    app.oncheckpoint = function (args) {
    };

    app.start();

    var publicMembers = {
        items: pages
    };

    WinJS.Namespace.define("Data", publicMembers);

})();
```

## <a name="see-also"></a>请参阅
- [快速入门：调试 HTML 和 CSS](../debugger/quickstart-debug-html-and-css.md)
