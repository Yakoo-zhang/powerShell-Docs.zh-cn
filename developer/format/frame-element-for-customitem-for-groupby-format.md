---
title: 元素对 CustomItem 的帧的 GroupBy （格式） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854843"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="9b203-102">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9b203-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="9b203-103">定义如何显示数据，如向左或向右移位数据。</span><span class="sxs-lookup"><span data-stu-id="9b203-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="9b203-104">定义如何显示一组新对象时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9b203-105">GroupBy （格式） 的 GroupBy （格式） CustomEntry 元素 CustomControl CustomEntries 元素的视图 （格式） CustomControl 元素的配置元素 （格式） ViewDefinitions 元素 （格式） 视图元素 （格式） GroupBy 元素CustomControl CustomEntry CustomItem 为 GroupBy （格式） 的 GroupBy （格式） 框架元素的 GroupBy （格式） CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b203-106">语法</span><span class="sxs-lookup"><span data-stu-id="9b203-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b203-107">属性和元素</span><span class="sxs-lookup"><span data-stu-id="9b203-107">Attributes and Elements</span></span>

<span data-ttu-id="9b203-108">以下各节描述了特性、 子元素和父元素的`Frame`元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b203-109">特性</span><span class="sxs-lookup"><span data-stu-id="9b203-109">Attributes</span></span>

<span data-ttu-id="9b203-110">无。</span><span class="sxs-lookup"><span data-stu-id="9b203-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b203-111">子元素</span><span class="sxs-lookup"><span data-stu-id="9b203-111">Child Elements</span></span>

|<span data-ttu-id="9b203-112">元素</span><span class="sxs-lookup"><span data-stu-id="9b203-112">Element</span></span>|<span data-ttu-id="9b203-113">描述</span><span class="sxs-lookup"><span data-stu-id="9b203-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="9b203-114">所需的元素</span><span class="sxs-lookup"><span data-stu-id="9b203-114">Required Element</span></span>|
|[<span data-ttu-id="9b203-115">GroupBy （格式） 的帧的 FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="9b203-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9b203-117">指定向左移动数据的第一行的字符数。</span><span class="sxs-lookup"><span data-stu-id="9b203-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="9b203-118">GroupBy （格式） 的帧的 FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="9b203-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-119">Optional element.</span></span><br /><br /> <span data-ttu-id="9b203-120">指定向右移动数据的第一行的字符数。</span><span class="sxs-lookup"><span data-stu-id="9b203-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="9b203-121">GroupBy （格式） 的帧的 LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="9b203-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-122">Optional element.</span></span><br /><br /> <span data-ttu-id="9b203-123">指定左边距远离数据向右移的字符数。</span><span class="sxs-lookup"><span data-stu-id="9b203-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="9b203-124">[GroupBy （格式） 的帧的 RightIndent 元素](./rightindent-element-for-frame-for-groupby-format.md)RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="9b203-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-125">Optional element.</span></span><br /><br /> <span data-ttu-id="9b203-126">指定数据向右移离开右边距的字符数。</span><span class="sxs-lookup"><span data-stu-id="9b203-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9b203-127">父元素</span><span class="sxs-lookup"><span data-stu-id="9b203-127">Parent Elements</span></span>

|<span data-ttu-id="9b203-128">元素</span><span class="sxs-lookup"><span data-stu-id="9b203-128">Element</span></span>|<span data-ttu-id="9b203-129">描述</span><span class="sxs-lookup"><span data-stu-id="9b203-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b203-130">GroupBy （格式） 的 CustomEntry CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="9b203-131">定义由控件显示的数据和显示方式。</span><span class="sxs-lookup"><span data-stu-id="9b203-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b203-132">备注</span><span class="sxs-lookup"><span data-stu-id="9b203-132">Remarks</span></span>

<span data-ttu-id="9b203-133">不能指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)并[FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md)中相同的元素`Frame`元素。</span><span class="sxs-lookup"><span data-stu-id="9b203-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b203-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b203-134">See Also</span></span>

[<span data-ttu-id="9b203-135">GroupBy （格式） 的帧的 FirstLineHanging 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="9b203-136">GroupBy （格式） 的帧的 FirstLineIndent 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="9b203-137">GroupBy （格式） 的帧的 LeftIndent 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="9b203-138">GroupBy （格式） 的帧的 RightIndent 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="9b203-139">GroupBy （格式） 的 CustomEntry CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="9b203-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="9b203-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9b203-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)