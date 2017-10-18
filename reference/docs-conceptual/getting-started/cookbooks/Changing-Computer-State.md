---
ms.date: 2017-06-05
keywords: powershell,cmdlet
title: "更改计算机状态"
ms.assetid: 8093268b-27f8-4a49-8871-142c5cc33f01
ms.openlocfilehash: 636690c72b16bf19826b0a7e54ce00114ce30fb6
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2017
---
# <a name="changing-computer-state"></a><span data-ttu-id="f4bd9-103">更改计算机状态</span><span class="sxs-lookup"><span data-stu-id="f4bd9-103">Changing Computer State</span></span>
<span data-ttu-id="f4bd9-104">若要在 Windows PowerShell 中重置计算机，请使用标准命令行工具或 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-104">To reset a computer in Windows PowerShell, use either a standard command-line tool or a WMI class.</span></span> <span data-ttu-id="f4bd9-105">尽管你使用 Windows PowerShell 仅仅是为了运行该工具，但了解如何在 Windows PowerShell 中更改计算机的电源状态将阐明有关在 Windows PowerShell 中使用外部工具的一些重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-105">Although you are using Windows PowerShell only to run the tool, learning how to change a computer's power state in Windows PowerShell illustrates some of the important details about working with external tools in Windows PowerShell.</span></span>

### <a name="locking-a-computer"></a><span data-ttu-id="f4bd9-106">锁定计算机</span><span class="sxs-lookup"><span data-stu-id="f4bd9-106">Locking a Computer</span></span>
<span data-ttu-id="f4bd9-107">使用标准可用工具直接锁定计算机的唯一方法是调用 **user32.dll** 中的 **LockWorkstation()** 函数：</span><span class="sxs-lookup"><span data-stu-id="f4bd9-107">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll**:</span></span>

```
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="f4bd9-108">此命令将立即锁定工作站。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-108">This command immediately locks the workstation.</span></span> <span data-ttu-id="f4bd9-109">它使用 *rundll32.exe*，后者运行 Windows DLL（并保存其库以便重复使用）以运行 user32.dll（Windows 管理函数的库）。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-109">It uses *rundll32.exe*, which runs Windows DLLs (and saves their libraries for repeated use) to run user32.dll, a library of Windows management functions.</span></span>

<span data-ttu-id="f4bd9-110">如果在启用了“快速用户切换”时锁定工作站（例如在 Windows XP 中），则计算机将显示用户登录屏幕，而不会启动当前用户的屏幕保护程序。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-110">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="f4bd9-111">若要关闭终端服务器上的特定会话，请使用 **tsshutdn.exe** 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-111">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

### <a name="logging-off-the-current-session"></a><span data-ttu-id="f4bd9-112">注销当前会话</span><span class="sxs-lookup"><span data-stu-id="f4bd9-112">Logging Off the Current Session</span></span>
<span data-ttu-id="f4bd9-113">可以使用多种不同的方法来注销本地系统上的会话。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-113">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="f4bd9-114">最简单的方法是使用远程桌面/终端服务命令行工具 **logoff.exe**（若要了解有关详细信息，请在 Windows PowerShell 提示符处键入 **logoff /?**）。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-114">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the Windows PowerShell prompt, type **logoff /?**).</span></span> <span data-ttu-id="f4bd9-115">若要注销当前活动会话，请键入 **logoff** 而不带参数。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-115">To log off the current active session, type **logoff** with no arguments.</span></span>

<span data-ttu-id="f4bd9-116">你还可以使用具 **shutdown.exe** 工具及其 logoff 选项：</span><span class="sxs-lookup"><span data-stu-id="f4bd9-116">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```
shutdown.exe -l
```

<span data-ttu-id="f4bd9-117">第三个选项是使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-117">A third option is to use WMI.</span></span> <span data-ttu-id="f4bd9-118">Win32_OperatingSystem 类具有 Win32Shutdown 方法。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-118">The Win32_OperatingSystem class has a Win32Shutdown method.</span></span> <span data-ttu-id="f4bd9-119">调用具有 0 标志的方法将启动注销：</span><span class="sxs-lookup"><span data-stu-id="f4bd9-119">Invoking the method with the 0 flag initiates logoff:</span></span>

```
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(0)
```

<span data-ttu-id="f4bd9-120">若要了解有关详细信息和 Win32Shutdown 方法的其他功能，请参阅 MSDN 中的“Win32_OperatingSystem 类的 Win32Shutdown 方法”。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-120">For more information, and to find other features of the Win32Shutdown method, see "Win32Shutdown Method of the Win32_OperatingSystem Class" in MSDN.</span></span>

### <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="f4bd9-121">关闭或重启计算机</span><span class="sxs-lookup"><span data-stu-id="f4bd9-121">Shutting Down or Restarting a Computer</span></span>
<span data-ttu-id="f4bd9-122">关闭和重启计算机通常是相同类型的任务。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-122">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="f4bd9-123">关闭计算机的工具通常也可以重启计算机，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-123">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="f4bd9-124">从 Windows PowerShell 重启计算机有两个直接的选项。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-124">There are two straightforward options for restarting a computer from Windows PowerShell.</span></span> <span data-ttu-id="f4bd9-125">使用 Tsshutdn.exe 或 Shutdown.exe 及其相应参数。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-125">Use either Tsshutdn.exe or Shutdown.exe with appropriate arguments.</span></span> <span data-ttu-id="f4bd9-126">你可以从 **tsshutdn.exe /?**</span><span class="sxs-lookup"><span data-stu-id="f4bd9-126">You can get detailed usage information from **tsshutdn.exe /?**</span></span> <span data-ttu-id="f4bd9-127">或 **shutdown.exe /?** 获取详细的使用情况信息。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-127">or **shutdown.exe /?**.</span></span>

<span data-ttu-id="f4bd9-128">也可以通过使用 **Win32_OperatingSystem** 直接从 Windows PowerShell 执行关闭或重启操作。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-128">You can also perform shutdown and restart operations by using **Win32_OperatingSystem** directly from Windows PowerShell as well.</span></span>

<span data-ttu-id="f4bd9-129">若要关闭计算机，请使用具有 **1** 标志的 Win32Shutdown 方法。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-129">To shut down the computer, use the Win32Shutdown method with the **1** flag.</span></span>

```
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(1)
```

<span data-ttu-id="f4bd9-130">若要重启计算机，请使用具有 **2** 标志的 Win32Shutdown 方法。</span><span class="sxs-lookup"><span data-stu-id="f4bd9-130">To restart the operating system, use the Win32Shutdown method with the **2** flag.</span></span>

```
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(2)
```
