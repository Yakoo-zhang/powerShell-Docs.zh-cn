---
title: 如何重写输入处理方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1ad921-5816-4937-acf1-ed4760fae740
caps.latest.revision: 8
ms.openlocfilehash: eff40a01b60985788ae0e21156fec7ec4e27fcf1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855913"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="3ed2f-102">如何替代输入处理方法</span><span class="sxs-lookup"><span data-stu-id="3ed2f-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="3ed2f-103">这些示例演示如何覆盖的输入处理某个 cmdlet 中的方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="3ed2f-104">这些方法用于执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3ed2f-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="3ed2f-105">[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)方法用于执行一次性启动操作有效的 cmdlet 处理的所有对象。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-105">The [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="3ed2f-106">Windows PowerShell 运行时一次调用此方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="3ed2f-107">[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法用于处理传递给 cmdlet 的对象。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-107">The [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="3ed2f-108">对于每个对象传递给 cmdlet，Windows PowerShell 运行时调用此方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="3ed2f-109">[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)方法用于执行一次性 post 处理操作。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-109">The [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="3ed2f-110">Windows PowerShell 运行时一次调用此方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="3ed2f-111">若要重写 BeginProcessing 方法</span><span class="sxs-lookup"><span data-stu-id="3ed2f-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="3ed2f-112">声明的是受保护的重写[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-112">Declare a protected override of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="3ed2f-113">下面的类将输出的示例消息。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-113">The following class prints a sample message.</span></span> <span data-ttu-id="3ed2f-114">若要使用此类，动词和名词的 Cmdlet 属性中更改、 更改以反映新谓词和名词，类的名称，然后将所需的功能添加到的重写[System.Management.Automation.Cmdlet.Beginprocessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="3ed2f-115">若要重写 ProcessRecord 方法</span><span class="sxs-lookup"><span data-stu-id="3ed2f-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="3ed2f-116">声明的是受保护的重写[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-116">Declare a protected override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="3ed2f-117">下面的类将输出的示例消息。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-117">The following class prints a sample message.</span></span> <span data-ttu-id="3ed2f-118">若要使用此类，动词和名词的 Cmdlet 属性中更改、 更改以反映新谓词和名词，类的名称，然后将所需的功能添加到的重写[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="3ed2f-119">若要重写 EndProcessing 方法</span><span class="sxs-lookup"><span data-stu-id="3ed2f-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="3ed2f-120">声明的是受保护的重写[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-120">Declare a protected override of the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="3ed2f-121">下面的类将输出一个示例。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-121">The following class prints a sample.</span></span> <span data-ttu-id="3ed2f-122">若要使用此类，动词和名词的 Cmdlet 属性中更改、 更改以反映新谓词和名词，类的名称，然后将所需的功能添加到的重写[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)方法。</span><span class="sxs-lookup"><span data-stu-id="3ed2f-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a><span data-ttu-id="3ed2f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ed2f-123">See Also</span></span>

[<span data-ttu-id="3ed2f-124">System.Management.Automation.Cmdlet.Beginprocessing\*</span><span class="sxs-lookup"><span data-stu-id="3ed2f-124">System.Management.Automation.Cmdlet.Beginprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="3ed2f-125">System.Management.Automation.Cmdlet.Endprocessing\*</span><span class="sxs-lookup"><span data-stu-id="3ed2f-125">System.Management.Automation.Cmdlet.Endprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="3ed2f-126">System.Management.Automation.Cmdlet.Processrecord\*</span><span class="sxs-lookup"><span data-stu-id="3ed2f-126">System.Management.Automation.Cmdlet.Processrecord\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="3ed2f-127">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3ed2f-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)