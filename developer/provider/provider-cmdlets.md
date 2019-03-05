---
title: 提供程序 cmdlet |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2465420-0970-4408-9ee5-260cf444cb67
caps.latest.revision: 8
ms.openlocfilehash: e6a0711cff6a550100f584fb64ae7f59f71a3cfb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854763"
---
# <a name="provider-cmdlets"></a><span data-ttu-id="88edd-102">提供程序 cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-102">Provider cmdlets</span></span>

<span data-ttu-id="88edd-103">用户可以运行以管理数据存储区的 cmdlet 称为提供程序 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-103">The cmdlets that the user can run to manage a data store are referred to as provider cmdlets.</span></span> <span data-ttu-id="88edd-104">若要支持这些 cmdlet，需要覆盖某些由基本提供程序类和接口定义的方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-104">To support these cmdlets, you need to overwrite some of the methods defined by the base provider classes and interfaces.</span></span>

## <a name="provider-cmdlets"></a><span data-ttu-id="88edd-105">提供程序 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-105">Provider Cmdlets</span></span>

<span data-ttu-id="88edd-106">下面是可以由用户运行的提供程序 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88edd-106">Here are the provider cmdlets that can be run by the user:</span></span>

### <a name="psdrive-cmdlets"></a><span data-ttu-id="88edd-107">PSDrive cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-107">PSDrive cmdlets</span></span>

- <span data-ttu-id="88edd-108">`Get-PSDrive`：此 cmdlet 将返回当前会话中的 Windows PowerShell 驱动器。</span><span class="sxs-lookup"><span data-stu-id="88edd-108">`Get-PSDrive`: This cmdlet returns the Windows PowerShell drives in the current session.</span></span> <span data-ttu-id="88edd-109">不需要覆盖任何方法，以支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-109">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="88edd-110">`New-PSDrive`：此 cmdlet 允许用户创建 Windows PowerShell 驱动器来访问数据存储区。</span><span class="sxs-lookup"><span data-stu-id="88edd-110">`New-PSDrive`: This cmdlet allows the user to create Windows PowerShell drives to access the data store.</span></span> <span data-ttu-id="88edd-111">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Drivecmdletprovider.Newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)和[System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-111">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-112">`Remove-PSDrive`：此 cmdlet 允许用户访问数据存储区的 Windows PowerShell 驱动器中删除。</span><span class="sxs-lookup"><span data-stu-id="88edd-112">`Remove-PSDrive`: This cmdlet allows the user to remove Windows PowerShell drives that access the data store.</span></span> <span data-ttu-id="88edd-113">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-113">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span>

### <a name="item-cmdlets"></a><span data-ttu-id="88edd-114">Item cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-114">Item cmdlets</span></span>

- <span data-ttu-id="88edd-115">`Clear-Item`：此 cmdlet 允许用户在数据存储区中删除项的值。</span><span class="sxs-lookup"><span data-stu-id="88edd-115">`Clear-Item`: This cmdlet allows the user to remove the value of an item in the data store.</span></span> <span data-ttu-id="88edd-116">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Itemcmdletprovider.Clearitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)和[System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-116">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-117">`Copy-Item`：此 cmdlet 允许用户将项从一个位置复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="88edd-117">`Copy-Item`: This cmdlet allows the user to copy an item from one location to another.</span></span> <span data-ttu-id="88edd-118">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Containercmdletprovider.Copyitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)和[System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-118">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Containercmdletprovider.Copyitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) and [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-119">`Get-Item`：此 cmdlet 允许用户从数据存储中检索数据。</span><span class="sxs-lookup"><span data-stu-id="88edd-119">`Get-Item`: This cmdlet allows the user to retrieve data from the data store.</span></span> <span data-ttu-id="88edd-120">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Itemcmdletprovider.Getitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)和[System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-120">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-121">`Get-ChildItem`：此 cmdlet 允许用户检索父项的子项。</span><span class="sxs-lookup"><span data-stu-id="88edd-121">`Get-ChildItem`: This cmdlet allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="88edd-122">若要支持此 cmdlet，覆盖以下方法：</span><span class="sxs-lookup"><span data-stu-id="88edd-122">To support this cmdlet, overwrite the following methods:</span></span>

  - [<span data-ttu-id="88edd-123">System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*</span><span class="sxs-lookup"><span data-stu-id="88edd-123">System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [<span data-ttu-id="88edd-124">System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*</span><span class="sxs-lookup"><span data-stu-id="88edd-124">System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [<span data-ttu-id="88edd-125">System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*</span><span class="sxs-lookup"><span data-stu-id="88edd-125">System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [<span data-ttu-id="88edd-126">System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*</span><span class="sxs-lookup"><span data-stu-id="88edd-126">System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- <span data-ttu-id="88edd-127">`Invoke-Item`：此 cmdlet 允许用户执行指定的项的默认操作。</span><span class="sxs-lookup"><span data-stu-id="88edd-127">`Invoke-Item`: This cmdlet allows the user to perform the default action specified by the item.</span></span> <span data-ttu-id="88edd-128">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)和[System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-128">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) and [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) methods.</span></span>

- <span data-ttu-id="88edd-129">`Move-Item`：此 cmdlet 允许用户将项从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="88edd-129">`Move-Item`: This cmdlet allows the user to move an item from one location to another location.</span></span> <span data-ttu-id="88edd-130">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)和[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)的方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-130">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) and [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s methods.</span></span>

- <span data-ttu-id="88edd-131">`New-ItemProperty`：此 cmdlet 允许用户在数据存储区中创建新项。</span><span class="sxs-lookup"><span data-stu-id="88edd-131">`New-ItemProperty`: This cmdlet allows the user to create a new item in the data store.</span></span>

- <span data-ttu-id="88edd-132">`Remove-Item`：此 cmdlet 允许用户从数据存储区中删除项目。</span><span class="sxs-lookup"><span data-stu-id="88edd-132">`Remove-Item`: This cmdlet allows the user to remove items from the data store.</span></span> <span data-ttu-id="88edd-133">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Containercmdletprovider.Removeitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)和[System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-133">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) and [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-134">`Rename-Item`：此 cmdlet 允许用户重命名数据存储中的项目。</span><span class="sxs-lookup"><span data-stu-id="88edd-134">`Rename-Item`: This cmdlet allows the user to rename items in the data store.</span></span> <span data-ttu-id="88edd-135">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Containercmdletprovider.Renameitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)和[System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-135">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) and [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-136">`Set-Item`：此 cmdlet 允许用户更新的数据存储区中的项的值。</span><span class="sxs-lookup"><span data-stu-id="88edd-136">`Set-Item`: This cmdlet allows the user to update the values of items in the data store.</span></span> <span data-ttu-id="88edd-137">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Itemcmdletprovider.Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)和[System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-137">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) methods.</span></span>

### <a name="item-content-cmdlets"></a><span data-ttu-id="88edd-138">项内容 cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-138">Item content cmdlets</span></span>

- <span data-ttu-id="88edd-139">`Add-Content`：此 cmdlet 允许用户将内容添加到项目。</span><span class="sxs-lookup"><span data-stu-id="88edd-139">`Add-Content`: This cmdlet allows the user to add content to an item.</span></span>

- <span data-ttu-id="88edd-140">`Clear-Content`：此 cmdlet 允许用户从注册表项删除内容，而不删除该项。</span><span class="sxs-lookup"><span data-stu-id="88edd-140">`Clear-Content`: This cmdlet allows the user to delete content from an item without deleting the item.</span></span> <span data-ttu-id="88edd-141">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)和[System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-141">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) and [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-142">`Get-Content`：此 cmdlet 允许用户检索其内容的项。</span><span class="sxs-lookup"><span data-stu-id="88edd-142">`Get-Content`: This cmdlet allows the user to retrieve the content of an item.</span></span> <span data-ttu-id="88edd-143">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)和[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-143">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) and [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) methods.</span></span> <span data-ttu-id="88edd-144">[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)方法将返回[System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)定义接口用于读取内容的方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-144">The [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method returns an [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) interface that defines the methods used to read the content.</span></span>

- <span data-ttu-id="88edd-145">`Set-Content`：此 cmdlet 允许用户更新项的内容。</span><span class="sxs-lookup"><span data-stu-id="88edd-145">`Set-Content`: This cmdlet allows the user to update the content of an item.</span></span> <span data-ttu-id="88edd-146">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)和[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-146">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) and [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) methods.</span></span> <span data-ttu-id="88edd-147">[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)方法将返回[System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)定义接口用于写入内容的方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-147">The [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) method returns an [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) interface that defines the methods used to write the content.</span></span>

### <a name="item-property-cmdlets"></a><span data-ttu-id="88edd-148">Item 属性 cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-148">Item property cmdlets</span></span>

- <span data-ttu-id="88edd-149">`Clear-ItemProperty`：此 cmdlet 允许用户删除属性的值。</span><span class="sxs-lookup"><span data-stu-id="88edd-149">`Clear-ItemProperty`: This cmdlet allows the user to delete the value of a property.</span></span> <span data-ttu-id="88edd-150">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)和[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-150">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) and [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-151">`Copy-ItemProperty`：此 cmdlet 允许用户将属性和其值从一个位置复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="88edd-151">`Copy-ItemProperty`: This cmdlet allows the user to copy a property and its value from one location to another.</span></span> <span data-ttu-id="88edd-152">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty)和[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-152">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-153">`Get-ItemProperty`：此 cmdlet 检索项的属性。</span><span class="sxs-lookup"><span data-stu-id="88edd-153">`Get-ItemProperty`: This cmdlet retrieves the properties of an item.</span></span> <span data-ttu-id="88edd-154">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)和[System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-154">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) and [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-155">`Move-ItemProperty`：此 cmdlet 允许用户将属性和其值从一个位置移到另一个。</span><span class="sxs-lookup"><span data-stu-id="88edd-155">`Move-ItemProperty`: This cmdlet allows the user to move a property and its value from one location to another.</span></span> <span data-ttu-id="88edd-156">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty)和[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-156">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-157">`New-ItemProperty`：此 cmdlet 允许用户创建新的属性并将其值设置。</span><span class="sxs-lookup"><span data-stu-id="88edd-157">`New-ItemProperty`: This cmdlet allows the user to create a new property and set its value.</span></span> <span data-ttu-id="88edd-158">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty)和[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-158">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-159">`Remove-ItemProperty`：此 cmdlet 允许用户删除一个属性及其值。</span><span class="sxs-lookup"><span data-stu-id="88edd-159">`Remove-ItemProperty`: This cmdlet allows the user to delete a property and its value.</span></span> <span data-ttu-id="88edd-160">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)和[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-160">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-161">`Rename-ItemProperty`：此 cmdlet 允许用户更改的属性名称。</span><span class="sxs-lookup"><span data-stu-id="88edd-161">`Rename-ItemProperty`: This cmdlet allows the user to change the name of a property.</span></span> <span data-ttu-id="88edd-162">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)和[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-162">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="88edd-163">`Set-ItemProperty`：此 cmdlet 允许用户更新项的属性。</span><span class="sxs-lookup"><span data-stu-id="88edd-163">`Set-ItemProperty`: This cmdlet allows the user to update the properties of an item.</span></span> <span data-ttu-id="88edd-164">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)和[System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-164">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) and [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) methods.</span></span>

### <a name="location-cmdlets"></a><span data-ttu-id="88edd-165">位置 cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-165">Location cmdlets</span></span>

- <span data-ttu-id="88edd-166">`Get-Location`：检索有关当前工作位置的信息。</span><span class="sxs-lookup"><span data-stu-id="88edd-166">`Get-Location`: Retrieves information about the current working location.</span></span> <span data-ttu-id="88edd-167">不需要覆盖任何方法，以支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-167">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="88edd-168">`Pop-Location`：此 cmdlet 将当前位置更改到最近推入堆栈的位置。</span><span class="sxs-lookup"><span data-stu-id="88edd-168">`Pop-Location`: This cmdlet changes the current location to the location most recently pushed onto the stack.</span></span> <span data-ttu-id="88edd-169">不需要覆盖任何方法，以支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-169">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="88edd-170">`Push-Location`：此 cmdlet 将当前位置添加到的位置 （"堆栈"） 的列表顶部。</span><span class="sxs-lookup"><span data-stu-id="88edd-170">`Push-Location`: This cmdlet adds the current location to the top of a list of locations (a "stack").</span></span> <span data-ttu-id="88edd-171">不需要覆盖任何方法，以支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-171">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="88edd-172">`Set-Location`：此 cmdlet 将当前的工作位置设置为指定的位置。</span><span class="sxs-lookup"><span data-stu-id="88edd-172">`Set-Location`: This cmdlet sets the current working location to a specified location.</span></span> <span data-ttu-id="88edd-173">不需要覆盖任何方法，以支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-173">You do not need to overwrite any methods to support this cmdlet.</span></span>

### <a name="path-cmdlets"></a><span data-ttu-id="88edd-174">路径 cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-174">Path cmdlets</span></span>

- <span data-ttu-id="88edd-175">`Join-Path`：此 cmdlet 允许用户以合并一个父级和子级路径片段来创建提供程序内部的路径。</span><span class="sxs-lookup"><span data-stu-id="88edd-175">`Join-Path`: This cmdlet allows the user to combine a parent and child path segment to create a provider-internal path.</span></span> <span data-ttu-id="88edd-176">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-176">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method.</span></span>

- <span data-ttu-id="88edd-177">`Convert-Path`：此 cmdlet 将路径从 Windows PowerShell 路径转换为 Windows PowerShell 提供程序路径。</span><span class="sxs-lookup"><span data-stu-id="88edd-177">`Convert-Path`: This cmdlet converts a path from a Windows PowerShell path to a Windows PowerShell provider path.</span></span>

- <span data-ttu-id="88edd-178">`Split-Path`：返回指定的路径部分。</span><span class="sxs-lookup"><span data-stu-id="88edd-178">`Split-Path`: Returns the specified part of a path.</span></span>

- <span data-ttu-id="88edd-179">`Resolve-Path`：解析路径中的通配符并显示路径内容。</span><span class="sxs-lookup"><span data-stu-id="88edd-179">`Resolve-Path`: Resolves the wildcard characters in a path, and displays the path contents.</span></span>

- <span data-ttu-id="88edd-180">`Test-Path`：此 cmdlet 确定路径的所有元素是否都存在。</span><span class="sxs-lookup"><span data-stu-id="88edd-180">`Test-Path`: This cmdlet determines whether all elements of a path exist.</span></span> <span data-ttu-id="88edd-181">若要支持此 cmdlet，覆盖[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)和[System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-181">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) and [System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) methods.</span></span>

### <a name="psprovider-cmdlets"></a><span data-ttu-id="88edd-182">PSProvider cmdlet</span><span class="sxs-lookup"><span data-stu-id="88edd-182">PSProvider cmdlets</span></span>

- <span data-ttu-id="88edd-183">`Get-PSProvider`：此 cmdlet 将返回有关在会话中可用的提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="88edd-183">`Get-PSProvider`: This cmdlet returns information about the providers available in the session.</span></span> <span data-ttu-id="88edd-184">不需要覆盖任何方法，以支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88edd-184">You do not need to overwrite any methods to support this cmdlet.</span></span>