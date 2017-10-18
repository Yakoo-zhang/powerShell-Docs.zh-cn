---
ms.date: 2017-06-05
keywords: powershell,cmdlet
title: "Windows PowerShell 基础知识"
ms.assetid: 6b3cbbc8-060c-4877-b00b-7300dbbe4e28
ms.openlocfilehash: 7b5cdfce876aa7d5559fe772379829011b275a02
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2017
---
# <a name="windows-powershell-basics"></a><span data-ttu-id="48fcf-103">Windows PowerShell 基础知识</span><span class="sxs-lookup"><span data-stu-id="48fcf-103">Windows PowerShell Basics</span></span>
<span data-ttu-id="48fcf-104">图形用户界面采用大多数计算机用户熟悉的一些基本概念。</span><span class="sxs-lookup"><span data-stu-id="48fcf-104">Graphical user interfaces use some basic concepts that are well known to most computer users.</span></span> <span data-ttu-id="48fcf-105">用户凭借对这些界面的熟悉度来完成任务。</span><span class="sxs-lookup"><span data-stu-id="48fcf-105">Users rely on the familiarity of those interfaces to accomplish tasks.</span></span> <span data-ttu-id="48fcf-106">操作系统为用户提供可浏览项的图形表现形式，通常含有访问特定功能的下拉菜单以及访问特定于上下文的功能的上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="48fcf-106">Operating systems present users with a graphical representation of items that can be browsed, usually with drop-down menus for accessing specific functionality and context menus for accessing context-specific functionality.</span></span>

<span data-ttu-id="48fcf-107">命令行接口 (CLI)（如 Windows PowerShell）则必须使用不同的方法来公开信息，因为它没有菜单或图形系统来帮助用户。</span><span class="sxs-lookup"><span data-stu-id="48fcf-107">A command-line interface (CLI), such as Windows PowerShell, must use a different approach to expose information, because it does not have menus or graphical systems to help the user.</span></span> <span data-ttu-id="48fcf-108">你需要知道命令的名称才能使用命令。</span><span class="sxs-lookup"><span data-stu-id="48fcf-108">You need to know command names before you can use them.</span></span> <span data-ttu-id="48fcf-109">尽管你可以键入与 GUI 环境中功能等效的复杂命令，但你必须要熟悉常用命令和命令参数。</span><span class="sxs-lookup"><span data-stu-id="48fcf-109">Although you can type complex commands that are equivalent to the features in a GUI environment, you must become familiar with commonly-used commands and command parameters.</span></span>

<span data-ttu-id="48fcf-110">大多数 CLI 不具有可以帮助用户了解界面的参数。</span><span class="sxs-lookup"><span data-stu-id="48fcf-110">Most CLIs do not have patterns that can help the user to learn the interface.</span></span> <span data-ttu-id="48fcf-111">因为 CLI 是第一个操作系统外壳程序，因此许多命令名称和参数名称都是任意选择的。</span><span class="sxs-lookup"><span data-stu-id="48fcf-111">Because CLIs were the first operating system shells, many command names and parameter names were selected arbitrarily.</span></span> <span data-ttu-id="48fcf-112">通常选择简要的命令名称而不是清楚的名称。</span><span class="sxs-lookup"><span data-stu-id="48fcf-112">Terse command names were generally chosen over clear ones.</span></span> <span data-ttu-id="48fcf-113">尽管帮助系统和命令设计标准都集成到大多数 CLI 中，但它们通常设计为与最早的命令相兼容，因此命令集仍受数十年前所做决定的影响。</span><span class="sxs-lookup"><span data-stu-id="48fcf-113">Although help systems and command design standards are integrated into most CLIs, they have been generally designed for compatibility with the earliest commands, so the command set is still shaped by decisions made decades ago.</span></span>

<span data-ttu-id="48fcf-114">Windows PowerShell 旨在充分利用用户对 CLI 一直以来所了解的知识。</span><span class="sxs-lookup"><span data-stu-id="48fcf-114">Windows PowerShell was designed to take advantage of a user's historic knowledge of CLIs.</span></span> <span data-ttu-id="48fcf-115">在本节中，我们将谈论可用于快速了解 Windows PowerShell 的基本工具和概念。</span><span class="sxs-lookup"><span data-stu-id="48fcf-115">In this chapter, we will talk about some basic tools and concepts that you can use to learn Windows PowerShell quickly.</span></span> <span data-ttu-id="48fcf-116">其中包括：</span><span class="sxs-lookup"><span data-stu-id="48fcf-116">They include:</span></span>

- <span data-ttu-id="48fcf-117">使用 Get-Command</span><span class="sxs-lookup"><span data-stu-id="48fcf-117">Using Get-Command</span></span>

- <span data-ttu-id="48fcf-118">使用 Cmd.exe 和 UNIX 命令</span><span class="sxs-lookup"><span data-stu-id="48fcf-118">Using Cmd.exe and UNIX commands</span></span>

- <span data-ttu-id="48fcf-119">使用外部命令</span><span class="sxs-lookup"><span data-stu-id="48fcf-119">Using External Commands</span></span>

- <span data-ttu-id="48fcf-120">使用 Tab-Completion</span><span class="sxs-lookup"><span data-stu-id="48fcf-120">Using Tab-Completion</span></span>

- <span data-ttu-id="48fcf-121">使用 Get-Help</span><span class="sxs-lookup"><span data-stu-id="48fcf-121">Using Get-Help</span></span>
