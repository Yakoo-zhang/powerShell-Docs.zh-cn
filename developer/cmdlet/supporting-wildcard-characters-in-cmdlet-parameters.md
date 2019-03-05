---
title: 中的 Cmdlet 参数支持通配符字符 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcards [PowerShell Programer's Guide]
- parameters [PowerShell Programmer's Guide], wildcards
ms.assetid: 9b26e1e9-9350-4a5a-aad5-ddcece658d93
caps.latest.revision: 12
ms.openlocfilehash: 296490e4692e72f823be0b00aee90dc8c3dc9131
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862513"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="8f215-102">支持在 Cmdlet 参数中使用通配符</span><span class="sxs-lookup"><span data-stu-id="8f215-102">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="8f215-103">通常，您将必须设计用于运行针对一组资源，而不是针对单个资源的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f215-103">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="8f215-104">例如，一个 cmdlet 可能需要在具有相同的名称或扩展的数据存储区中找到的所有文件。</span><span class="sxs-lookup"><span data-stu-id="8f215-104">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="8f215-105">在设计的 cmdlet，将针对资源组的运行时，你必须提供支持的通配符字符。</span><span class="sxs-lookup"><span data-stu-id="8f215-105">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="8f215-106">使用通配符字符有时称为*通配*。</span><span class="sxs-lookup"><span data-stu-id="8f215-106">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="8f215-107">使用通配符的 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f215-107">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="8f215-108">许多 Windows PowerShell cmdlet 的参数值支持通配符字符。</span><span class="sxs-lookup"><span data-stu-id="8f215-108">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="8f215-109">例如，几乎每个 cmdlet，具有`Name`或`Path`参数支持通配符字符为这些参数。</span><span class="sxs-lookup"><span data-stu-id="8f215-109">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="8f215-110">(尽管大多数 cmdlet 都`Path`参数还具有`LiteralPath`不支持通配符字符的参数。)以下命令演示如何使用通配符字符以返回名称中包含 Get 谓词在当前会话中的所有 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f215-110">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 <span data-ttu-id="8f215-111">**PS > get 命令 get-\***</span><span class="sxs-lookup"><span data-stu-id="8f215-111">**PS>get-command get-\***</span></span>

## <a name="supported-wildcard-characters"></a><span data-ttu-id="8f215-112">受支持的通配符字符</span><span class="sxs-lookup"><span data-stu-id="8f215-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="8f215-113">Windows PowerShell 支持下列通配符。</span><span class="sxs-lookup"><span data-stu-id="8f215-113">Windows PowerShell supports the following wildcard characters.</span></span>

|<span data-ttu-id="8f215-114">通配符字符</span><span class="sxs-lookup"><span data-stu-id="8f215-114">Wildcard character</span></span>|<span data-ttu-id="8f215-115">描述</span><span class="sxs-lookup"><span data-stu-id="8f215-115">Description</span></span>|<span data-ttu-id="8f215-116">示例</span><span class="sxs-lookup"><span data-stu-id="8f215-116">Example</span></span>|<span data-ttu-id="8f215-117">匹配</span><span class="sxs-lookup"><span data-stu-id="8f215-117">Matches</span></span>|<span data-ttu-id="8f215-118">不匹配</span><span class="sxs-lookup"><span data-stu-id="8f215-118">Does not match</span></span>|
|------------------------|-----------------|-------------|-------------|--------------------|
|*|<span data-ttu-id="8f215-119">匹配零个或多个字符，从指定位置开始</span><span class="sxs-lookup"><span data-stu-id="8f215-119">Matches zero or more characters, starting at the specified position</span></span>|<span data-ttu-id="8f215-120">a\*</span><span class="sxs-lookup"><span data-stu-id="8f215-120">a\*</span></span>|<span data-ttu-id="8f215-121">A，ag Apple</span><span class="sxs-lookup"><span data-stu-id="8f215-121">A, ag, Apple</span></span>||
|<span data-ttu-id="8f215-122">?</span><span class="sxs-lookup"><span data-stu-id="8f215-122">?</span></span>|<span data-ttu-id="8f215-123">位于指定位置的匹配任何字符</span><span class="sxs-lookup"><span data-stu-id="8f215-123">Matches anycharacter at the specified position</span></span>|<span data-ttu-id="8f215-124">？ n</span><span class="sxs-lookup"><span data-stu-id="8f215-124">?n</span></span>|<span data-ttu-id="8f215-125">中，在</span><span class="sxs-lookup"><span data-stu-id="8f215-125">An, in, on</span></span>|<span data-ttu-id="8f215-126">运行</span><span class="sxs-lookup"><span data-stu-id="8f215-126">ran</span></span>|
|<span data-ttu-id="8f215-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="8f215-127">[ ]</span></span>|<span data-ttu-id="8f215-128">匹配字符的范围</span><span class="sxs-lookup"><span data-stu-id="8f215-128">Matches a range of characters</span></span>|<span data-ttu-id="8f215-129">[a-l]ook</span><span class="sxs-lookup"><span data-stu-id="8f215-129">[a-l]ook</span></span>|<span data-ttu-id="8f215-130">书籍、 cook 外观</span><span class="sxs-lookup"><span data-stu-id="8f215-130">book, cook, look</span></span>|<span data-ttu-id="8f215-131">花费了</span><span class="sxs-lookup"><span data-stu-id="8f215-131">took</span></span>|
|<span data-ttu-id="8f215-132">[ ]</span><span class="sxs-lookup"><span data-stu-id="8f215-132">[ ]</span></span>|<span data-ttu-id="8f215-133">匹配指定的字符</span><span class="sxs-lookup"><span data-stu-id="8f215-133">Matches the specified characters</span></span>|<span data-ttu-id="8f215-134">[bc]ook</span><span class="sxs-lookup"><span data-stu-id="8f215-134">[bc]ook</span></span>|<span data-ttu-id="8f215-135">书籍、 cook</span><span class="sxs-lookup"><span data-stu-id="8f215-135">book, cook</span></span>|<span data-ttu-id="8f215-136">查找</span><span class="sxs-lookup"><span data-stu-id="8f215-136">look</span></span>|

<span data-ttu-id="8f215-137">在设计时支持通配符的 cmdlet，允许的通配符字符的组合。</span><span class="sxs-lookup"><span data-stu-id="8f215-137">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="8f215-138">例如，下面的命令使用`Get-ChildItem`cmdlet 来检索所有.txt 文件，位于 c:\Techdocs 文件夹然后开头的字母"a"到"l。"</span><span class="sxs-lookup"><span data-stu-id="8f215-138">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

<span data-ttu-id="8f215-139">**get-childitem c:\techdocs\\[a-l]\*.txt**</span><span class="sxs-lookup"><span data-stu-id="8f215-139">**get-childitem c:\techdocs\\[a-l]\*.txt**</span></span>

<span data-ttu-id="8f215-140">前一个命令使用范围通配符 **[a-l]** 以指定的文件名称应开始的字符"a"到"l。"</span><span class="sxs-lookup"><span data-stu-id="8f215-140">The previous command uses the range wildcard **[a-l]** to specify that the file name should begin with the characters "a" through "l."</span></span> <span data-ttu-id="8f215-141">该命令将使用 \* 通配符作为.txt 扩展名的文件的名称的第一个字母之间的任何字符的占位符。</span><span class="sxs-lookup"><span data-stu-id="8f215-141">The command then uses the \* wildcard character as a placeholder for any characters between the first letter of the file name and the .txt extension.</span></span>

<span data-ttu-id="8f215-142">下面的示例使用范围通配符模式排除字母"d"，但包含从"a"到"f。"的所有其他字母</span><span class="sxs-lookup"><span data-stu-id="8f215-142">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

<span data-ttu-id="8f215-143">**get-childitem c:\techdocs\\[a-cef]\*.txt**</span><span class="sxs-lookup"><span data-stu-id="8f215-143">**get-childitem c:\techdocs\\[a-cef]\*.txt**</span></span>

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="8f215-144">处理文本字符的通配符模式</span><span class="sxs-lookup"><span data-stu-id="8f215-144">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="8f215-145">如果所指定的通配符模式包含原义字符，使用反撇号字符 （'） 作为转义符。</span><span class="sxs-lookup"><span data-stu-id="8f215-145">If the wildcard pattern you specify contains literal characters, use the backtick character (\`) as an escape character.</span></span> <span data-ttu-id="8f215-146">当以编程方式指定的原义字符时，请使用单个反引号。</span><span class="sxs-lookup"><span data-stu-id="8f215-146">When you specify literal characters programmatically, use a single backtick.</span></span> <span data-ttu-id="8f215-147">当指定文本字符的命令提示符处时，使用两个反撇号。</span><span class="sxs-lookup"><span data-stu-id="8f215-147">When you specify literal characters at the command prompt, use two backticks.</span></span> <span data-ttu-id="8f215-148">例如，以下模式包含必须按字面的两个方括号。</span><span class="sxs-lookup"><span data-stu-id="8f215-148">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="8f215-149">"John Smith \`[\*']"（指定以编程方式）</span><span class="sxs-lookup"><span data-stu-id="8f215-149">"John Smith \`[\*\`]" (specified programmatically)</span></span>

<span data-ttu-id="8f215-150">"John Smith \` \`[\*\`]"（在命令提示符下指定）</span><span class="sxs-lookup"><span data-stu-id="8f215-150">"John Smith \`\`[\*\`\`]"  (specified at the command prompt)</span></span>

<span data-ttu-id="8f215-151">此模式匹配"John Smith [营销]"或"John Smith [开发]"。</span><span class="sxs-lookup"><span data-stu-id="8f215-151">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span>

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="8f215-152">Cmdlet 的输出和通配符</span><span class="sxs-lookup"><span data-stu-id="8f215-152">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="8f215-153">如果 cmdlet 参数支持通配符，cmdlet 操作通常生成数组输出。</span><span class="sxs-lookup"><span data-stu-id="8f215-153">When cmdlet parameters support wildcard characters, a cmdlet operation usually generates an array output.</span></span> <span data-ttu-id="8f215-154">有时，它成为支持输出，因为用户可能会一次使用单个项的数组没有意义。</span><span class="sxs-lookup"><span data-stu-id="8f215-154">Occasionally, it makes no sense to support an array output because the user might use only a single item at a time.</span></span> <span data-ttu-id="8f215-155">例如， `Set-Location` cmdlet 支持输出，因为用户设置的单个位置的数组。</span><span class="sxs-lookup"><span data-stu-id="8f215-155">For example, the `Set-Location` cmdlet does support an array output because the user sets only a single location.</span></span> <span data-ttu-id="8f215-156">在此情况下，该 cmdlet 仍然支持通配符，但它会强制解析为单个位置。</span><span class="sxs-lookup"><span data-stu-id="8f215-156">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f215-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f215-157">See Also</span></span>

[<span data-ttu-id="8f215-158">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f215-158">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="8f215-159">WildcardPattern 类</span><span class="sxs-lookup"><span data-stu-id="8f215-159">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)