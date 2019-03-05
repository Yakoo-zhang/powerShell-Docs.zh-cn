---
title: 如何将输入的类型添加到 Cmdlet 帮助主题 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860803"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="b4610-102">如何向 Cmdlet 帮助主题添加输入类型</span><span class="sxs-lookup"><span data-stu-id="b4610-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="b4610-103">本部分介绍如何将输入部分添加到 Windows PowerShell® cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b4610-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="b4610-104">输入部分列出了该 cmdlet 接受作为输入通过管道，通过值或属性名称的对象的.NET 类。</span><span class="sxs-lookup"><span data-stu-id="b4610-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="b4610-105">可以将它们添加到输入部分的类的数目没有限制。</span><span class="sxs-lookup"><span data-stu-id="b4610-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="b4610-106">输入的类型括在\<命令： inputTypes > 节点，而且中所包含的每个类\<命令： inputType > 元素。</span><span class="sxs-lookup"><span data-stu-id="b4610-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="b4610-107">架构包含两个\<maml:description > 中每个元素\<命令： inputType > 元素。</span><span class="sxs-lookup"><span data-stu-id="b4610-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="b4610-108">但是， `Get-Help` cmdlet 将显示的内容\<命令： inputType > /\<maml:description >) 元素。</span><span class="sxs-lookup"><span data-stu-id="b4610-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="b4610-109">从 Windows PowerShell 3.0 开始`Get-Help`cmdlet 将显示的内容\<: uri > 元素。</span><span class="sxs-lookup"><span data-stu-id="b4610-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="b4610-110">此元素允许你将用户定向到主题，介绍.NET 类。</span><span class="sxs-lookup"><span data-stu-id="b4610-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="b4610-111">下面的 XML 演示\<maml:inputTypes > 节点。</span><span class="sxs-lookup"><span data-stu-id="b4610-111">The following XML shows the \<maml:inputTypes> node.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

<span data-ttu-id="b4610-112">下面的 XML 演示使用的示例\<maml:inputTypes > 节点来记录输入的类型。</span><span class="sxs-lookup"><span data-stu-id="b4610-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```