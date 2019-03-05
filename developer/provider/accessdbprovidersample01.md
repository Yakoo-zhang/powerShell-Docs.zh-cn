---
title: AccessDBProviderSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 853b7e5d-76c1-490e-8269-0ef31ba2ff13
caps.latest.revision: 10
ms.openlocfilehash: dc1ae92af8a57d6197b595db8e098256ac444b78
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854153"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="63757-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="63757-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="63757-103">此示例演示如何声明直接派生的提供程序类[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)类。</span><span class="sxs-lookup"><span data-stu-id="63757-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="63757-104">仅出于完整性考虑而在此处包含此项。</span><span class="sxs-lookup"><span data-stu-id="63757-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="63757-105">说明</span><span class="sxs-lookup"><span data-stu-id="63757-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63757-106">提供程序类将很可能从以下类之一派生，并可能实现其他提供程序接口：</span><span class="sxs-lookup"><span data-stu-id="63757-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="63757-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)类。</span><span class="sxs-lookup"><span data-stu-id="63757-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="63757-108">请参阅[AccessDBProviderSample03](./accessdbprovidersample03.md)。</span><span class="sxs-lookup"><span data-stu-id="63757-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="63757-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)类。</span><span class="sxs-lookup"><span data-stu-id="63757-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="63757-110">请参阅[AccessDBProviderSample04](./accessdbprovidersample04.md)。</span><span class="sxs-lookup"><span data-stu-id="63757-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="63757-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类。</span><span class="sxs-lookup"><span data-stu-id="63757-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="63757-112">请参阅[AccessDBProviderSample05](./accessdbprovidersample05.md)。</span><span class="sxs-lookup"><span data-stu-id="63757-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="63757-113">有关选择哪个提供程序类派生自基于提供程序功能，请参阅详细信息[设计你 Windows PowerShell 提供程序](./provider-types.md)。</span><span class="sxs-lookup"><span data-stu-id="63757-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="63757-114">此示例将演示如下：</span><span class="sxs-lookup"><span data-stu-id="63757-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="63757-115">声明`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="63757-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="63757-116">定义提供程序类直接派生自[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)类。</span><span class="sxs-lookup"><span data-stu-id="63757-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="63757-117">示例</span><span class="sxs-lookup"><span data-stu-id="63757-117">Example</span></span>

<span data-ttu-id="63757-118">此示例演示如何定义提供程序类以及如何声明`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="63757-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  /// <summary>
  /// This sample shows how to declare a provider class and how to
  /// declare the CmdletProvider attribute.
  /// </summary>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : CmdletProvider
  {
    // Add provider logic here.
  }
}
```

## <a name="see-also"></a><span data-ttu-id="63757-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63757-119">See Also</span></span>

[<span data-ttu-id="63757-120">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="63757-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="63757-121">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="63757-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="63757-122">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="63757-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="63757-123">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="63757-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)