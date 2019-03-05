---
title: TableHeaders 元素 （格式） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856873"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="ada87-102">TableHeaders Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ada87-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="ada87-103">定义表的列的标头。</span><span class="sxs-lookup"><span data-stu-id="ada87-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="ada87-104">TableControl （格式） 的 ViewDefinitions 元素 （格式） 视图元素 （格式） TableControl 元素 （格式） TableHeaders 元素</span><span class="sxs-lookup"><span data-stu-id="ada87-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ada87-105">语法</span><span class="sxs-lookup"><span data-stu-id="ada87-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ada87-106">属性和元素</span><span class="sxs-lookup"><span data-stu-id="ada87-106">Attributes and Elements</span></span>

<span data-ttu-id="ada87-107">以下各节描述的特性、 子元素和父元素的`TableHeaders`元素。</span><span class="sxs-lookup"><span data-stu-id="ada87-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="ada87-108">必须是要显示的对象的每个属性的子元素。</span><span class="sxs-lookup"><span data-stu-id="ada87-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="ada87-109">列标头信息显示在指定的子元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="ada87-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="ada87-110">特性</span><span class="sxs-lookup"><span data-stu-id="ada87-110">Attributes</span></span>

<span data-ttu-id="ada87-111">无。</span><span class="sxs-lookup"><span data-stu-id="ada87-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ada87-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ada87-112">Child Elements</span></span>

|<span data-ttu-id="ada87-113">元素</span><span class="sxs-lookup"><span data-stu-id="ada87-113">Element</span></span>|<span data-ttu-id="ada87-114">描述</span><span class="sxs-lookup"><span data-stu-id="ada87-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ada87-115">TableColumnHeader 元素 （格式）</span><span class="sxs-lookup"><span data-stu-id="ada87-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="ada87-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="ada87-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ada87-117">定义标签、 宽度和表视图的列的数据的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="ada87-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ada87-118">父元素</span><span class="sxs-lookup"><span data-stu-id="ada87-118">Parent Elements</span></span>

|<span data-ttu-id="ada87-119">元素</span><span class="sxs-lookup"><span data-stu-id="ada87-119">Element</span></span>|<span data-ttu-id="ada87-120">描述</span><span class="sxs-lookup"><span data-stu-id="ada87-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ada87-121">TableControl 元素 （格式）</span><span class="sxs-lookup"><span data-stu-id="ada87-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="ada87-122">定义一个视图，以表格式。</span><span class="sxs-lookup"><span data-stu-id="ada87-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ada87-123">备注</span><span class="sxs-lookup"><span data-stu-id="ada87-123">Remarks</span></span>

<span data-ttu-id="ada87-124">表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="ada87-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ada87-125">示例</span><span class="sxs-lookup"><span data-stu-id="ada87-125">Example</span></span>

<span data-ttu-id="ada87-126">此示例显示了`TableHeaders`元素，用于定义两个列标题。</span><span class="sxs-lookup"><span data-stu-id="ada87-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="ada87-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ada87-127">See Also</span></span>

[<span data-ttu-id="ada87-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="ada87-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ada87-129">TableColumnHeader 元素 （格式）</span><span class="sxs-lookup"><span data-stu-id="ada87-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="ada87-130">TableControl 元素 （格式）</span><span class="sxs-lookup"><span data-stu-id="ada87-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="ada87-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ada87-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)