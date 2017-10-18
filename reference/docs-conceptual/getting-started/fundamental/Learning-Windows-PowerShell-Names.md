---
ms.date: 2017-06-05
keywords: powershell,cmdlet
title: "学习 Windows PowerShell 名称"
ms.assetid: b4d0fd22-8298-4ee6-82ae-9b6f2907c986
ms.openlocfilehash: 28c821c4a617b6ac775dbdda8ade3d15c3f218c3
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2017
---
# <a name="learning-windows-powershell-names"></a><span data-ttu-id="43a01-103">学习 Windows PowerShell 名称</span><span class="sxs-lookup"><span data-stu-id="43a01-103">Learning Windows PowerShell Names</span></span>
<span data-ttu-id="43a01-104">学习命令和命令参数的名称是使用大多数命令行接口时重要的时间投入。</span><span class="sxs-lookup"><span data-stu-id="43a01-104">Learning names of commands and command parameters is a significant time investment with most command-line interfaces.</span></span> <span data-ttu-id="43a01-105">问题是模式非常少，因此学习的唯一方法是通过记住需要定期使用的每个命令和每个参数。</span><span class="sxs-lookup"><span data-stu-id="43a01-105">The issue is that there are very few patterns, so the only way to learn is by memorizing each command and each parameter that you need to use on a regular basis.</span></span>

<span data-ttu-id="43a01-106">当使用新命令或参数时，你通常不能使用已知名称；你需要查找和学习新的名称。</span><span class="sxs-lookup"><span data-stu-id="43a01-106">When you work with a new command or parameter, you cannot generally use what you already know; you have to find and learn a new name.</span></span> <span data-ttu-id="43a01-107">如果你看看接口是如何从一小组工具通过递增添加发展为功能，那就很容易明白为什么结构是非标准的。</span><span class="sxs-lookup"><span data-stu-id="43a01-107">If you look at how interfaces grow from a small set of tools with incremental additions to functionality, it is easy to see why the structure is nonstandard.</span></span> <span data-ttu-id="43a01-108">特别是命令名称，由于每个命令都是独立的工具，所以听起来可能很有逻辑，但还有更好的方法来处理命令名称。</span><span class="sxs-lookup"><span data-stu-id="43a01-108">With command names in particular, this may sound logical since each command is a separate tool, but there is a better way to handle command names.</span></span>

<span data-ttu-id="43a01-109">大多数命令用于管理操作系统或应用程序中的元素，如服务或进程。</span><span class="sxs-lookup"><span data-stu-id="43a01-109">Most commands are built to manage elements of the operating system or applications, such as services or processes.</span></span> <span data-ttu-id="43a01-110">命令具有众多名称，这些名称可能或可能不会纳入一个系列。</span><span class="sxs-lookup"><span data-stu-id="43a01-110">The commands have a variety of names that may or may not fit into a family.</span></span> <span data-ttu-id="43a01-111">例如，在 Windows 系统中，你可以使用 **net start** 和 **net stop** 命令来启动和停止服务。</span><span class="sxs-lookup"><span data-stu-id="43a01-111">For example, on Windows systems, you can use the **net start** and **net stop** commands to start and stop a service.</span></span> <span data-ttu-id="43a01-112">还有另一种对 Windows 更通用的服务控制工具，该工具具有完全不同的名称，即 **sc**，但该名称未纳入 **net** 服务命令的命名模式。</span><span class="sxs-lookup"><span data-stu-id="43a01-112">There is another more generalized service control tool for Windows that has a completely different name, **sc**, that does not fit into the naming pattern for the **net** service commands.</span></span> <span data-ttu-id="43a01-113">对于流程管理，Windows 使用 **tasklist** 命令列出进程，使用 **taskkill** 命令终止进程。</span><span class="sxs-lookup"><span data-stu-id="43a01-113">For process management, Windows has the **tasklist** command to list processes and the **taskkill** command to kill processes.</span></span>

<span data-ttu-id="43a01-114">采用参数的命令的参数规范不规则。</span><span class="sxs-lookup"><span data-stu-id="43a01-114">Commands that take parameters have irregular parameter specifications.</span></span> <span data-ttu-id="43a01-115">不能使用 **net start** 命令来启动远程计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="43a01-115">You cannot use the **net start** command to start a service on a remote computer.</span></span> <span data-ttu-id="43a01-116">**sc** 命令将在远程计算机上启动服务，但若要指定远程计算机，必须在其名称前使用双反斜杠作为前缀。</span><span class="sxs-lookup"><span data-stu-id="43a01-116">The **sc** command will start a service on a remote computer, but to specify the remote computer, you must prefix its name with a double backslash.</span></span> <span data-ttu-id="43a01-117">例如，若要在名为 DC01 的远程计算机上启动后台处理程序服务，应键入 **sc \\DC01 start spooler\\**。</span><span class="sxs-lookup"><span data-stu-id="43a01-117">For example, to start the spooler service on a remote computer named DC01, you would type **sc \\\\DC01 start spooler**.</span></span> <span data-ttu-id="43a01-118">若要列出在 DC01 上运行的任务，需要使用 **/S**（代指“系统”）参数并提供没有反斜杠的名称 DC01，如：**tasklist /S DC01**。</span><span class="sxs-lookup"><span data-stu-id="43a01-118">To list tasks running on DC01, you need to use the **/S** (for "system") parameter and supply the name DC01 without backslashes, like this: **tasklist /S DC01**.</span></span>

<span data-ttu-id="43a01-119">尽管服务和进程之间具有重要的技术区别，但它们都是计算机上的可管理元素的示例，具有定义完善的生命周期。</span><span class="sxs-lookup"><span data-stu-id="43a01-119">Although there are important technical distinctions between a service and a process, they are both examples of manageable elements on a computer that have a well-defined life cycle.</span></span> <span data-ttu-id="43a01-120">你可能想要启动或停止服务或进程，或获取所有当前正在运行的服务或进程的列表。</span><span class="sxs-lookup"><span data-stu-id="43a01-120">You may want to start or stop a service or process, or get a list of all currently running services or processes.</span></span> <span data-ttu-id="43a01-121">换而言之，尽管服务和过程是不同的事物，我们对服务或进程执行的操作通常从概念上讲是相同的。</span><span class="sxs-lookup"><span data-stu-id="43a01-121">In other words, although a service and a process are different things, the actions we perform on a service or a process are often conceptually the same.</span></span> <span data-ttu-id="43a01-122">此外，通过指定参数自定义操作所做的选择从概念上讲也是相似的。</span><span class="sxs-lookup"><span data-stu-id="43a01-122">Furthermore, choices we may make to customize an action by specifying parameters may be conceptually similar as well.</span></span>

<span data-ttu-id="43a01-123">Windows PowerShell 利用这些相似之处减少了解和使用 cmdlet 时需要知道的不同名称的数量。</span><span class="sxs-lookup"><span data-stu-id="43a01-123">Windows PowerShell exploits these similarities to reduce the number of distinct names you need to know to understand and use cmdlets.</span></span>

### <a name="cmdlets-use-verb-noun-names-to-reduce-command-memorization"></a><span data-ttu-id="43a01-124">Cmdlet 使用谓词-名词的名称来减少命令记忆</span><span class="sxs-lookup"><span data-stu-id="43a01-124">Cmdlets Use Verb-Noun Names to Reduce Command Memorization</span></span>
<span data-ttu-id="43a01-125">Windows PowerShell 使用“谓词-名词”命名系统，其中每个 cmdlet 名称由标准谓词、连字符、特定名词组成。</span><span class="sxs-lookup"><span data-stu-id="43a01-125">Windows PowerShell uses a "verb-noun" naming system, where each cmdlet name consists of a standard verb hyphenated with a specific noun.</span></span> <span data-ttu-id="43a01-126">Windows PowerShell 谓词并不始终是英文谓词，但在 Windows PowerShell 中表达特定的操作。</span><span class="sxs-lookup"><span data-stu-id="43a01-126">Windows PowerShell verbs are not always English verbs, but they express specific actions in Windows PowerShell.</span></span> <span data-ttu-id="43a01-127">名词非常类似于任何语言中的名词，它们描述在系统管理中十分重要的特定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="43a01-127">Nouns are very much like nouns in any language, they describe specific types of objects that are important in system administration.</span></span> <span data-ttu-id="43a01-128">通过查看一些谓词和名词的示例，可以很容易地演示这些包含两个部分的名称如何减少学习的负担。</span><span class="sxs-lookup"><span data-stu-id="43a01-128">It is easy to demonstrate how these two-part names reduce learning effort by looking at a few examples of verbs and nouns.</span></span>

<span data-ttu-id="43a01-129">名词所受限制更少，但它们应始终描述命令作用的对象。</span><span class="sxs-lookup"><span data-stu-id="43a01-129">Nouns are less restricted, but they should always describe what a command acts upon.</span></span> <span data-ttu-id="43a01-130">Windows PowerShell 很多命令，例如 **Get-Process**、**Stop-Process**、**Get-Service** 和 **Stop-Service**。</span><span class="sxs-lookup"><span data-stu-id="43a01-130">Windows PowerShell has commands such as **Get-Process**, **Stop-Process**, **Get-Service**, and **Stop-Service**.</span></span>

<span data-ttu-id="43a01-131">在两个名词和两个谓词的情况下，一致性并未简化太多学习。</span><span class="sxs-lookup"><span data-stu-id="43a01-131">In the case of two nouns and two verbs, consistency does not simplify learning that much.</span></span> <span data-ttu-id="43a01-132">但是，如果你查看 10 个谓词和 10 个名词的标准集，那么你仅需了解 20 个词，但这些词可用于组成 100 个不同的命令名。</span><span class="sxs-lookup"><span data-stu-id="43a01-132">However, if you look at a standard set of 10 verbs and 10 nouns, you then have only 20 words to understand, but those words can be used to form 100 distinct command names.</span></span>

<span data-ttu-id="43a01-133">通常情况下，你通过阅读命令的名称就可以识别命令，对新的命令该使用什么名称通常是显而易见的。</span><span class="sxs-lookup"><span data-stu-id="43a01-133">Frequently, you can recognize what a command does by reading its name, and it is usually apparent what name should be used for a new command.</span></span> <span data-ttu-id="43a01-134">例如，计算机关机命令可能是 **Stop-Computer**。</span><span class="sxs-lookup"><span data-stu-id="43a01-134">For example, a computer shutdown command might be **Stop-Computer**.</span></span> <span data-ttu-id="43a01-135">列出网络上的所有计算机的命令可能是 **Get-Computer**。</span><span class="sxs-lookup"><span data-stu-id="43a01-135">A command that lists all computers on a network might be **Get-Computer**.</span></span> <span data-ttu-id="43a01-136">获取系统日期的命令是 **Get-Date**。</span><span class="sxs-lookup"><span data-stu-id="43a01-136">The command that gets the system date is **Get-Date**.</span></span>

<span data-ttu-id="43a01-137">你可以使用 **Get-Command** 的 **-Verb** 参数列出包含特定谓词的所有命令（我们将在下一节中详细介绍 **Get-Command**）。</span><span class="sxs-lookup"><span data-stu-id="43a01-137">You can list all commands that include a particular verb with the **-Verb** parameter for **Get-Command** (We will discuss **Get-Command** in detail in the next section).</span></span> <span data-ttu-id="43a01-138">例如，若要查看使用谓词 **Get** 的所有 cmdlet，键入：</span><span class="sxs-lookup"><span data-stu-id="43a01-138">For example, to see all cmdlets that use the verb **Get**, type:</span></span>

```
PS> Get-Command -Verb Get
CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Get-Acl                         Get-Acl [[-Path] <String[]>]...
Cmdlet          Get-Alias                       Get-Alias [[-Name] <String[]...
Cmdlet          Get-AuthenticodeSignature       Get-AuthenticodeSignature [-...
Cmdlet          Get-ChildItem                   Get-ChildItem [[-Path] <Stri...
...
```

<span data-ttu-id="43a01-139">**-Noun** 参数更有用，因为它可让你查看将对同一类型的对象产生影响的命令系列。</span><span class="sxs-lookup"><span data-stu-id="43a01-139">The **-Noun** parameter is even more useful because it allows you to see a family of commands that affect the same type of object.</span></span> <span data-ttu-id="43a01-140">例如，如果你想要查看哪些命令可用于管理服务，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="43a01-140">For example, if you want to see which commands are available for managing services, type following command:</span></span>

```
PS> Get-Command -Noun Service
CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Get-Service                     Get-Service [[-Name] <String...
Cmdlet          New-Service                     New-Service [-Name] <String>...
Cmdlet          Restart-Service                 Restart-Service [-Name] <Str...
Cmdlet          Resume-Service                  Resume-Service [-Name] <Stri...
Cmdlet          Set-Service                     Set-Service [-Name] <String>...
Cmdlet          Start-Service                   Start-Service [-Name] <Strin...
Cmdlet          Stop-Service                    Stop-Service [-Name] <String...
Cmdlet          Suspend-Service                 Suspend-Service [-Name] <Str... 
...
```

<span data-ttu-id="43a01-141">命令不一定是 cmdlet，只是因为命令具有谓词-名词的命名结构。</span><span class="sxs-lookup"><span data-stu-id="43a01-141">A command is not necessarily a cmdlet, just because it has a verb-noun naming scheme.</span></span> <span data-ttu-id="43a01-142">并非 cmdlet 但具有谓词-名词名称的本地 Windows PowerShell 命令的一个例子为，用于清除控制台窗口的命令：Clear-Host。</span><span class="sxs-lookup"><span data-stu-id="43a01-142">One example of a native Windows PowerShell command that is not a cmdlet but has a verb-noun name, is the command for clearing a console window, Clear-Host.</span></span> <span data-ttu-id="43a01-143">Clear-Host 命令实际上是内部函数，如果你对其运行 Get-Command 便可知道：</span><span class="sxs-lookup"><span data-stu-id="43a01-143">The Clear-Host command is actually an internal function, as you can see if you run Get-Command against it:</span></span>

```
PS> Get-Command -Name Clear-Host

CommandType     Name                            Definition
-----------     ----                            ----------
Function        Clear-Host                      $spaceType = [System.Managem...
```

### <a name="cmdlets-use-standard-parameters"></a><span data-ttu-id="43a01-144">Cmdlet 使用标准参数</span><span class="sxs-lookup"><span data-stu-id="43a01-144">Cmdlets Use Standard Parameters</span></span>
<span data-ttu-id="43a01-145">如前文所述，在传统命令行接口中使用的命令通常没有一致的参数名称。</span><span class="sxs-lookup"><span data-stu-id="43a01-145">As noted earlier, commands used in traditional command-line interfaces do not generally have consistent parameter names.</span></span> <span data-ttu-id="43a01-146">有时参数根本没有名称。</span><span class="sxs-lookup"><span data-stu-id="43a01-146">Sometimes parameters do not have names at all.</span></span> <span data-ttu-id="43a01-147">若有名称，通常是可以快速输入但对新用户来说不能轻松理解的单个字符或缩写词。</span><span class="sxs-lookup"><span data-stu-id="43a01-147">When they do, they are often single-character or abbreviated words that can be typed rapidly but are not easily understood by new users.</span></span>

<span data-ttu-id="43a01-148">不同于大多数其他传统的命令行接口，Windows PowerShell 直接处理参数，并使用参数的这种直接访问权限以及开发人员指南标准化参数名称。</span><span class="sxs-lookup"><span data-stu-id="43a01-148">Unlike most other traditional command-line interfaces, Windows PowerShell processes parameters directly, and it uses this direct access to the parameters along with developer guidance to standardize parameter names.</span></span> <span data-ttu-id="43a01-149">尽管这样并不保证每个 cmdlet 将始终符合标准，但还是备受鼓舞。</span><span class="sxs-lookup"><span data-stu-id="43a01-149">Although this does not guarantee that every cmdlet will always conform to the standards, it does encourage it.</span></span>

> [!NOTE]
> <span data-ttu-id="43a01-150">使用时，参数名始终具有一个预置的“-”，以允许 Windows PowerShell 清楚地将它们标识为参数。</span><span class="sxs-lookup"><span data-stu-id="43a01-150">Parameter names always have a '-' prepended to them when you use them, to allow Windows PowerShell to clearly identify them as parameters.</span></span> <span data-ttu-id="43a01-151">在 **Get-Command -Name Clear-Host** 示例中，参数的名称为 **Name**，但输入时为 -**Name**。</span><span class="sxs-lookup"><span data-stu-id="43a01-151">In the **Get-Command -Name Clear-Host** example, the parameter's name is **Name**, but it is entered as -**Name**.</span></span>

<span data-ttu-id="43a01-152">以下是标准参数名称和用法的一些一般特征。</span><span class="sxs-lookup"><span data-stu-id="43a01-152">Here are some of the general characteristics of the standard parameter names and usages.</span></span>

#### <a name="the-help-parameter-"></a><span data-ttu-id="43a01-153">帮助参数 (?)</span><span class="sxs-lookup"><span data-stu-id="43a01-153">The Help Parameter (?)</span></span>
<span data-ttu-id="43a01-154">指定 **-?** 时</span><span class="sxs-lookup"><span data-stu-id="43a01-154">When you specify the **-?**</span></span> <span data-ttu-id="43a01-155">参数到任何 cmdlet，将不会执行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="43a01-155">parameter to any cmdlet, the cmdlet is not executed.</span></span> <span data-ttu-id="43a01-156">相反，Windows PowerShell 将显示有关 cmdlet 的帮助。</span><span class="sxs-lookup"><span data-stu-id="43a01-156">Instead, Windows PowerShell displays help for the cmdlet.</span></span>

#### <a name="common-parameters"></a><span data-ttu-id="43a01-157">通用参数</span><span class="sxs-lookup"><span data-stu-id="43a01-157">Common Parameters</span></span>
<span data-ttu-id="43a01-158">Windows PowerShell 具有一些名为“通用参数”的参数。</span><span class="sxs-lookup"><span data-stu-id="43a01-158">Windows PowerShell has several parameters known as *common parameters*.</span></span> <span data-ttu-id="43a01-159">因为这些参数由 Windows PowerShell 引擎控制，每当 cmdlet 实现这些参数时，它们的行为方式将始终相同。</span><span class="sxs-lookup"><span data-stu-id="43a01-159">Because these parameters are controlled by the Windows PowerShell engine, whenever they are implemented by a cmdlet, they will always behave the same way.</span></span> <span data-ttu-id="43a01-160">通用参数有 **WhatIf**、**Confirm**、**Verbose**、**Debug**、**Warn**、**ErrorAction**、**ErrorVariable**、**OutVariable** 和 **OutBuffer**</span><span class="sxs-lookup"><span data-stu-id="43a01-160">The common parameters are **WhatIf**, **Confirm**, **Verbose**, **Debug**, **Warn**, **ErrorAction**, **ErrorVariable**, **OutVariable**, and **OutBuffer**.</span></span>

#### <a name="suggested-parameters"></a><span data-ttu-id="43a01-161">建议参数</span><span class="sxs-lookup"><span data-stu-id="43a01-161">Suggested Parameters</span></span>
<span data-ttu-id="43a01-162">对于类似的参数，Windows PowerShell 核心 cmdlet 使用标准名称。</span><span class="sxs-lookup"><span data-stu-id="43a01-162">The Windows PowerShell core cmdlets use standard names for similar parameters.</span></span> <span data-ttu-id="43a01-163">尽管不强制使用参数名称，但是具有明确的用法指南支持标准化。</span><span class="sxs-lookup"><span data-stu-id="43a01-163">Although the use of parameter names is not enforced, there is explicit guidance for usage to encourage standardization.</span></span>

<span data-ttu-id="43a01-164">例如，本指南建议使用例如 **ComputerName** 等名称命名指示计算机的参数，而不使用 Server、Host、System、Node 或其他常见的备选单词。</span><span class="sxs-lookup"><span data-stu-id="43a01-164">For example, the guidance recommends naming a parameter that refers to a computer by name as **ComputerName**, rather than Server, Host, System, Node, or other common alternative words.</span></span> <span data-ttu-id="43a01-165">重要的建议参数名称有 **Force**、**Exclude**、**Include**、**PassThru**、**Path** 和 **CaseSensitive**。</span><span class="sxs-lookup"><span data-stu-id="43a01-165">Among the important suggested parameter names are **Force**, **Exclude**, **Include**, **PassThru**, **Path**, and **CaseSensitive**.</span></span>
