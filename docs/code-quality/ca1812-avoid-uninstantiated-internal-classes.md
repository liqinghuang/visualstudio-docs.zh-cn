---
title: CA1812:避免未实例化的内部类
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 08d8b907e4a211b0735f07377c21dec1c0a982c9
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55950742"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812:避免未实例化的内部类

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因

程序集级别类型的实例不是由程序集中的代码创建的。

## <a name="rule-description"></a>规则说明

此规则会尝试查找对该类型的构造函数之一的调用，并报告冲突，如果不找到任何调用。

该规则不检查以下类型：

- 值类型

- 抽象类型

- 枚举

- 委托

- 编译器发出的数组类型

- 类型无法实例化和用于定义`static`(`Shared`在 Visual Basic 中) 只方法。

如果将应用<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName>对所分析的程序集，此规则不会标记为任何构造函数上发生`internal`因为无法确定是否一个字段正由另一个`friend`程序集。

即使您不能解决此限制在 Visual Studio 代码分析中，外部的独立 FxCop 会发生内部构造函数上每个`friend`程序集是在分析中存在。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请删除类型或添加使用它的代码。 如果类型仅包含静态方法，请将以下项之一添加到要阻止编译器发出的默认公共实例构造函数的类型：

- 私有构造函数的类型的目标.NET Framework 1.0 和 1.1 版。

- `static` (`Shared`在 Visual Basic 中) 修饰符类型面向[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

它可以安全地禁止显示此规则的警告。 我们建议您取消显示在以下情况下的此警告：

- 如通过反射后期绑定方法创建的类<xref:System.Activator.CreateInstance%2A?displayProperty=fullName>。

- 类是由运行时或 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 自动创建的。 例如，用于实现 <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> 或 <xref:System.Web.IHttpHandler?displayProperty=fullName> 的类。

- 类是作为具有一个新约束的泛型类型参数传递。 例如，下面的示例将引发此规则。

    ```csharp
    internal class MyClass
    {
        public DoSomething()
        {
        }
    }
    public class MyGeneric<T> where T : new()
    {
        public T Create()
        {
            return new T();
        }
    }
    // [...]
    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

  在这些情况下，我们建议您取消显示此警告。

## <a name="related-rules"></a>相关的规则

[CA1811:避免使用未调用的私有代码](../code-quality/ca1811-avoid-uncalled-private-code.md)

[CA1801:检查未使用的参数](../code-quality/ca1801-review-unused-parameters.md)

[CA1804:删除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)