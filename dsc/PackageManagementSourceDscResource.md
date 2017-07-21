---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "dsc,powershell,配置,安装程序"
title: "DSC PackageManagementSource 资源"
ms.openlocfilehash: 80d157aff5bf7685a797baaf6a26215f02473096
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="32fcf-103">DSC PackageManagementSource 资源</span><span class="sxs-lookup"><span data-stu-id="32fcf-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="32fcf-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="32fcf-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="32fcf-105">Windows PowerShell Desired State Configuration (DSC) 中的 **PackageManagementSource** 资源提供了一种在目标节点上注册或取消注册程序包管理源的机制。</span><span class="sxs-lookup"><span data-stu-id="32fcf-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="32fcf-106">**以这种方式注册的程序包管理源在系统上下文中注册，可供系统帐户或 DSC 引擎使用。**</span><span class="sxs-lookup"><span data-stu-id="32fcf-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="32fcf-107">此资源需要 http://PowerShellGallery.com 中的 **PackageManagement** 模块。</span><span class="sxs-lookup"><span data-stu-id="32fcf-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

## <a name="syntax"></a><span data-ttu-id="32fcf-108">语法</span><span class="sxs-lookup"><span data-stu-id="32fcf-108">Syntax</span></span>

```
PSModule [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Absent | Present }  ]
    [ InstallationPolicy = [string] ]
    [ ProviderName = [string] ]
    [ SourceUri = [string] ]
    [ SourceCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="32fcf-109">“属性”</span><span class="sxs-lookup"><span data-stu-id="32fcf-109">Properties</span></span>
|  <span data-ttu-id="32fcf-110">属性</span><span class="sxs-lookup"><span data-stu-id="32fcf-110">Property</span></span>  |  <span data-ttu-id="32fcf-111">说明</span><span class="sxs-lookup"><span data-stu-id="32fcf-111">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="32fcf-112">名称</span><span class="sxs-lookup"><span data-stu-id="32fcf-112">Name</span></span>| <span data-ttu-id="32fcf-113">指定要在系统上注册或取消注册的包源名称。</span><span class="sxs-lookup"><span data-stu-id="32fcf-113">Specifies the name of the package source to be registered or unregistered on your system.</span></span>| 
| <span data-ttu-id="32fcf-114">Ensure</span><span class="sxs-lookup"><span data-stu-id="32fcf-114">Ensure</span></span>| <span data-ttu-id="32fcf-115">确定是要注册还是要取消注册包源。</span><span class="sxs-lookup"><span data-stu-id="32fcf-115">Determines whether the package source is to be registered or unregistered.</span></span>| 
| <span data-ttu-id="32fcf-116">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="32fcf-116">InstallationPolicy</span></span>| <span data-ttu-id="32fcf-117">确定是否信任包源。</span><span class="sxs-lookup"><span data-stu-id="32fcf-117">Determines whether you trust the package source.</span></span> <span data-ttu-id="32fcf-118">可取值为“Untrusted”或“Trusted”。</span><span class="sxs-lookup"><span data-stu-id="32fcf-118">One of: "Untrusted", "Trusted".</span></span>| 
| <span data-ttu-id="32fcf-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="32fcf-119">ProviderName</span></span>| <span data-ttu-id="32fcf-120">指定 OneGet 提供程序的名称，借此可以与包源进行互操作。</span><span class="sxs-lookup"><span data-stu-id="32fcf-120">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>| 
| <span data-ttu-id="32fcf-121">SourceUri</span><span class="sxs-lookup"><span data-stu-id="32fcf-121">SourceUri</span></span>| <span data-ttu-id="32fcf-122">指定包源的 URI。</span><span class="sxs-lookup"><span data-stu-id="32fcf-122">Specifies the URI of the package source.</span></span>| 
| <span data-ttu-id="32fcf-123">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="32fcf-123">SourceCredential</span></span>| <span data-ttu-id="32fcf-124">提供远程源上程序包的访问权限。</span><span class="sxs-lookup"><span data-stu-id="32fcf-124">Provides access to the package on a remote source.</span></span>| 

## <a name="example"></a><span data-ttu-id="32fcf-125">示例</span><span class="sxs-lookup"><span data-stu-id="32fcf-125">Example</span></span>

<span data-ttu-id="32fcf-126">此示例使用 **PackageManagementSource** DSC 资源注册 http://nuget.org 包源。</span><span class="sxs-lookup"><span data-stu-id="32fcf-126">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{    
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present" 
        Name        = "MyNuget" 
        ProviderName= "Nuget" 
        SourceUri   = "http://nuget.org/api/v2/"   
        InstallationPolicy ="Trusted" 
    }
}
```
