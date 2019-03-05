---
title: Windows PowerShell 主机快速入门 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a134b81-bd0c-4e1c-a2f0-9acbe852745a
caps.latest.revision: 9
ms.openlocfilehash: 2c6a4bca03ee7f62371cbc296f854464167e5a62
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857393"
---
# <a name="windows-powershell-host-quickstart"></a><span data-ttu-id="207a2-102">Windows PowerShell 主机快速入门</span><span class="sxs-lookup"><span data-stu-id="207a2-102">Windows PowerShell Host Quickstart</span></span>

<span data-ttu-id="207a2-103">若要在应用程序中托管 Windows PowerShell，请使用[System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)类。</span><span class="sxs-lookup"><span data-stu-id="207a2-103">To host Windows PowerShell in your application, you use the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class.</span></span> <span data-ttu-id="207a2-104">此类提供了创建命令的管道，然后在运行空间中执行这些命令的方法。</span><span class="sxs-lookup"><span data-stu-id="207a2-104">This class provides methods that create a pipeline of commands and then execute those commands in a runspace.</span></span> <span data-ttu-id="207a2-105">创建主机应用程序的最简单方法是使用默认的运行空间。</span><span class="sxs-lookup"><span data-stu-id="207a2-105">The simplest way to create a host application is to use the default runspace.</span></span> <span data-ttu-id="207a2-106">默认的运行空间包含的所有核心 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="207a2-106">The default runspace contains all of the core Windows PowerShell commands.</span></span> <span data-ttu-id="207a2-107">如果你希望应用程序来公开 Windows PowerShell 命令的一个子集，则必须创建自定义的运行空间。</span><span class="sxs-lookup"><span data-stu-id="207a2-107">If you want your application to expose only a subset of the Windows PowerShell commands, you must create a custom runspace.</span></span>

## <a name="using-the-default-runspace"></a><span data-ttu-id="207a2-108">使用默认的运行空间</span><span class="sxs-lookup"><span data-stu-id="207a2-108">Using the default runspace</span></span>

<span data-ttu-id="207a2-109">若要开始，我们将使用默认的运行空间，并使用的方法[System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)类将命令、 参数、 语句和脚本添加到管道。</span><span class="sxs-lookup"><span data-stu-id="207a2-109">To start, we'll use the default runspace, and use the methods of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands, parameters, statements, and scripts to a pipeline.</span></span>

### <a name="addcommand"></a><span data-ttu-id="207a2-110">AddCommand</span><span class="sxs-lookup"><span data-stu-id="207a2-110">AddCommand</span></span>

<span data-ttu-id="207a2-111">您使用[System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)方法[System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)类将命令添加到管道。</span><span class="sxs-lookup"><span data-stu-id="207a2-111">You use the [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands to the pipeline.</span></span> <span data-ttu-id="207a2-112">例如，假设你想要获取在计算机上运行的进程列表。</span><span class="sxs-lookup"><span data-stu-id="207a2-112">For example, suppose you want to get the list of running processes on the machine.</span></span> <span data-ttu-id="207a2-113">若要运行此命令的方法是按如下所示。</span><span class="sxs-lookup"><span data-stu-id="207a2-113">The way to run this command is as follows.</span></span>

1. <span data-ttu-id="207a2-114">创建[System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)对象。</span><span class="sxs-lookup"><span data-stu-id="207a2-114">Create a [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="207a2-115">添加你想要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="207a2-115">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="207a2-116">调用命令。</span><span class="sxs-lookup"><span data-stu-id="207a2-116">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="207a2-117">如果您调用[System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)方法多次在调用之前[System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)方法、 的结果第一个命令将被输送到第二个，依次类推。</span><span class="sxs-lookup"><span data-stu-id="207a2-117">If you call the [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="207a2-118">如果您不想要通过管道传递到命令前一命令的结果，则将其添加通过调用[System.Management.Automation.Powershell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)相反。</span><span class="sxs-lookup"><span data-stu-id="207a2-118">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="207a2-119">AddParameter</span><span class="sxs-lookup"><span data-stu-id="207a2-119">AddParameter</span></span>

<span data-ttu-id="207a2-120">前面的示例执行不带任何参数的单个命令。</span><span class="sxs-lookup"><span data-stu-id="207a2-120">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="207a2-121">通过使用添加到命令参数[System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)方法，如以下代码获取一系列的所有进程名为`PowerShell`上运行计算机。</span><span class="sxs-lookup"><span data-stu-id="207a2-121">You can add parameters to the command by using the [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="207a2-122">可以添加其他参数，通过调用[System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)重复。</span><span class="sxs-lookup"><span data-stu-id="207a2-122">You can add additional parameters by calling [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

<span data-ttu-id="207a2-123">此外可以通过调用添加参数名称和值的字典[System.Management.Automation.PowerShell.AddParameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="207a2-123">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.PowerShell.AddParameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="207a2-124">AddStatement</span><span class="sxs-lookup"><span data-stu-id="207a2-124">AddStatement</span></span>

<span data-ttu-id="207a2-125">可以通过使用批处理来模拟[System.Management.Automation.PowerShell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)方法，该管道的以下代码获取具有名称运行进程的列表的末尾添加一个附加的语句方法`PowerShell`，然后获取正在运行服务的列表。</span><span class="sxs-lookup"><span data-stu-id="207a2-125">You can simulate batching by using the [System.Management.Automation.PowerShell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="207a2-126">AddScript</span><span class="sxs-lookup"><span data-stu-id="207a2-126">AddScript</span></span>

<span data-ttu-id="207a2-127">可以通过调用运行现有脚本[System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)方法。</span><span class="sxs-lookup"><span data-stu-id="207a2-127">You can run an existing script by calling the [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="207a2-128">下面的示例将脚本添加到管道，并运行它。</span><span class="sxs-lookup"><span data-stu-id="207a2-128">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="207a2-129">此示例假定已存在名为的脚本`MyScript.ps1`中名为的文件夹`D:\PSScripts`。</span><span class="sxs-lookup"><span data-stu-id="207a2-129">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="207a2-130">此外，还有新版[System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)方法采用布尔参数名为`useLocalScope`。</span><span class="sxs-lookup"><span data-stu-id="207a2-130">There is also a version of the [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="207a2-131">如果此参数设置为`true`，然后在本地作用域中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="207a2-131">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="207a2-132">下面的代码将在本地作用域中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="207a2-132">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a><span data-ttu-id="207a2-133">创建自定义的运行空间</span><span class="sxs-lookup"><span data-stu-id="207a2-133">Creating a custom runspace</span></span>

<span data-ttu-id="207a2-134">尽管上述示例中使用默认的运行空间加载所有核心 Windows PowerShell 命令，可以创建加载指定的一个子集的所有命令的自定义运行空间。</span><span class="sxs-lookup"><span data-stu-id="207a2-134">While the default runspace used in the previous examples loads all of the core Windows PowerShell commands, you can create a custom runspace that loads only a specified subset of all commands.</span></span> <span data-ttu-id="207a2-135">你可能想要这样做可以提高性能 （正在加载更多的命令是性能下降），或限制用户能够执行的操作。</span><span class="sxs-lookup"><span data-stu-id="207a2-135">You might want to do this to improve performance (loading a larger number of commands is a performance hit), or to restrict the capability of the user to perform operations.</span></span> <span data-ttu-id="207a2-136">公开只有有限的数量的命令的运行空间称为受限运行空间。</span><span class="sxs-lookup"><span data-stu-id="207a2-136">A runspace that exposes only a limited number of commands is called a constrained runspace.</span></span> <span data-ttu-id="207a2-137">若要创建受限运行空间，请使用[System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace)并[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)类。</span><span class="sxs-lookup"><span data-stu-id="207a2-137">To create a constrained runspace, you use the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) and [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) classes.</span></span>

### <a name="creating-an-initialsessionstate-object"></a><span data-ttu-id="207a2-138">创建 InitialSessionState 对象</span><span class="sxs-lookup"><span data-stu-id="207a2-138">Creating an InitialSessionState object</span></span>

<span data-ttu-id="207a2-139">若要创建自定义的运行空间，必须首先创建[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象。</span><span class="sxs-lookup"><span data-stu-id="207a2-139">To create a custom runspace, you must first create an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span> <span data-ttu-id="207a2-140">在以下示例中，我们将使用[System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory)若要创建默认值后，创建 ruspace [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象。</span><span class="sxs-lookup"><span data-stu-id="207a2-140">In the following example, we use the [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) to create a ruspace after creating a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a><span data-ttu-id="207a2-141">限制运行空间</span><span class="sxs-lookup"><span data-stu-id="207a2-141">Constraining the runspace</span></span>

<span data-ttu-id="207a2-142">在上述示例中，我们创建了默认值[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)加载所有内置的核心 Windows PowerShell 的对象。</span><span class="sxs-lookup"><span data-stu-id="207a2-142">In the previous example, we created a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object that loads all of the built-in core Windows PowerShell.</span></span> <span data-ttu-id="207a2-143">我们可能也称为[System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2)方法来创建一个 InitialSessionState 对象，将加载只有 Mirosoft.PowerShell.Core 中的命令管理单元。</span><span class="sxs-lookup"><span data-stu-id="207a2-143">We could also have called the [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) method to create an InitialSessionState object that would load only the commands in the Mirosoft.PowerShell.Core snapin.</span></span> <span data-ttu-id="207a2-144">若要创建更多受限运行空间，必须创建一个空[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象通过调用[System.Management.Automation.Runspaces.InitialSessionState.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create)方法，然后将命令添加到 InitialSessionState。</span><span class="sxs-lookup"><span data-stu-id="207a2-144">To create a more constrained runspace, you must create an empty [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object by calling the [System.Management.Automation.Runspaces.InitialSessionState.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add commands to the InitialSessionState.</span></span>

<span data-ttu-id="207a2-145">使用加载指定的命令的运行空间提供了显著改进了的性能。</span><span class="sxs-lookup"><span data-stu-id="207a2-145">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

<span data-ttu-id="207a2-146">使用的方法[System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry)类来定义初始会话状态的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="207a2-146">You use the methods of the [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span> <span data-ttu-id="207a2-147">下面的示例将创建空的初始会话状态，然后定义并添加`Get-Command`和`Import-Module`初始会话状态的命令。</span><span class="sxs-lookup"><span data-stu-id="207a2-147">The following example creates an empty initial session state, then defines and adds the `Get-Command` and `Import-Module` commands to the initial session state.</span></span> <span data-ttu-id="207a2-148">然后，我们创建初始会话状态，受约束的运行空间，并在该运行空间中执行命令。</span><span class="sxs-lookup"><span data-stu-id="207a2-148">We then create a runspace constrained by that initial session state, and execute the commands in that runspace.</span></span>

<span data-ttu-id="207a2-149">创建初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="207a2-149">Create the initial session state.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

<span data-ttu-id="207a2-150">定义并将命令添加到初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="207a2-150">Define and add commands to the initial session state.</span></span>

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

<span data-ttu-id="207a2-151">创建并打开运行空间。</span><span class="sxs-lookup"><span data-stu-id="207a2-151">Create and open the runspace.</span></span>

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

<span data-ttu-id="207a2-152">执行命令并显示结果。</span><span class="sxs-lookup"><span data-stu-id="207a2-152">Execute a command and show the result.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

<span data-ttu-id="207a2-153">当运行时，此代码的输出将如下所示。</span><span class="sxs-lookup"><span data-stu-id="207a2-153">When run, the output of this code will look as follows.</span></span>

```powershell
Get-Command
Import-Module
```