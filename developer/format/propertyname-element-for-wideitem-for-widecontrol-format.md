---
title: PropertyName 元素 WideControl （格式） 的 WideItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860953"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="71864-102">PropertyName Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="71864-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="71864-103">指定其值宽视图中显示的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="71864-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="71864-104">元素 （格式） ViewDefinitions 元素 （格式） 视图元素 （格式） WideControl 元素 （格式） WideEntries 元素 （格式） WideEntry 元素 （格式） WideItem 元素 （格式） 属性名称的配置元素 WideItem （格式）</span><span class="sxs-lookup"><span data-stu-id="71864-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="71864-105">语法</span><span class="sxs-lookup"><span data-stu-id="71864-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="71864-106">属性和元素</span><span class="sxs-lookup"><span data-stu-id="71864-106">Attributes and Elements</span></span>

<span data-ttu-id="71864-107">以下各节描述的特性、 子元素和父元素的`PropertyName`元素。</span><span class="sxs-lookup"><span data-stu-id="71864-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="71864-108">特性</span><span class="sxs-lookup"><span data-stu-id="71864-108">Attributes</span></span>

<span data-ttu-id="71864-109">无。</span><span class="sxs-lookup"><span data-stu-id="71864-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="71864-110">子元素</span><span class="sxs-lookup"><span data-stu-id="71864-110">Child Elements</span></span>

<span data-ttu-id="71864-111">无。</span><span class="sxs-lookup"><span data-stu-id="71864-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="71864-112">父元素</span><span class="sxs-lookup"><span data-stu-id="71864-112">Parent Elements</span></span>

|<span data-ttu-id="71864-113">元素</span><span class="sxs-lookup"><span data-stu-id="71864-113">Element</span></span>|<span data-ttu-id="71864-114">描述</span><span class="sxs-lookup"><span data-stu-id="71864-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="71864-115">WideItem 元素 （格式）</span><span class="sxs-lookup"><span data-stu-id="71864-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="71864-116">定义属性或其值宽视图中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="71864-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="71864-117">文本值</span><span class="sxs-lookup"><span data-stu-id="71864-117">Text Value</span></span>

<span data-ttu-id="71864-118">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="71864-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="71864-119">备注</span><span class="sxs-lookup"><span data-stu-id="71864-119">Remarks</span></span>

<span data-ttu-id="71864-120">有关较宽的视图的组件的详细信息，请参阅[创建较宽的视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="71864-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="71864-121">示例</span><span class="sxs-lookup"><span data-stu-id="71864-121">Example</span></span>

<span data-ttu-id="71864-122">此示例显示了显示的 ProcessName 属性的值较宽的视图[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)对象。</span><span class="sxs-lookup"><span data-stu-id="71864-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="71864-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71864-123">See Also</span></span>

[<span data-ttu-id="71864-124">WideItem 元素 （格式）</span><span class="sxs-lookup"><span data-stu-id="71864-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="71864-125">创建较宽的视图</span><span class="sxs-lookup"><span data-stu-id="71864-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="71864-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="71864-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)