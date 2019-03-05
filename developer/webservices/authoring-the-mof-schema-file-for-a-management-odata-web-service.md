---
title: 创作管理 OData web 服务的 MOF 架构文件 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65fbac8b-07d0-4513-bc8d-79f1f389be0f
caps.latest.revision: 5
ms.openlocfilehash: 7aadee07b38d2e9d87c5f0c548d13a5cdad1939f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854713"
---
# <a name="authoring-the-mof-schema-file-for-a-management-odata-web-service"></a><span data-ttu-id="4d534-102">创作管理 OData Web 服务的 MOF 架构文件</span><span class="sxs-lookup"><span data-stu-id="4d534-102">Authoring the MOF schema file for a Management OData web service</span></span>

<span data-ttu-id="4d534-103">定义管理 OData web 服务公开通过创建使用公共资源架构的 MOF 文件的资源。</span><span class="sxs-lookup"><span data-stu-id="4d534-103">You define the resources that your Management OData web service exposes by creating a MOF file that used the public resource schema.</span></span> <span data-ttu-id="4d534-104">每个资源被定义为在文件中，类和属性定义为类成员。</span><span class="sxs-lookup"><span data-stu-id="4d534-104">Each resource is defined as a class in the file, and properties are defined as class members.</span></span> <span data-ttu-id="4d534-105">有关 MOF 文件中使用的架构的详细信息，请参阅[公共资源架构](./public-resource-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="4d534-105">For more information about the schema used in the MOF file, see [Public Resource Schema](./public-resource-schema.md).</span></span>

## <a name="example-mof-file"></a><span data-ttu-id="4d534-106">示例 MOF 文件</span><span class="sxs-lookup"><span data-stu-id="4d534-106">Example MOF file</span></span>

<span data-ttu-id="4d534-107">以下文件定义服务和进程资源。</span><span class="sxs-lookup"><span data-stu-id="4d534-107">The following file defines Service and Process resources.</span></span> <span data-ttu-id="4d534-108">每种资源对应于一个可以由一组 Windows PowerShell cmdlet 管理的对象。</span><span class="sxs-lookup"><span data-stu-id="4d534-108">Each of these resources corresponds to an object that can be managed by a set of Windows PowerShell cmdlet.</span></span> <span data-ttu-id="4d534-109">属性对应于使用这些 cmdlet 的参数。</span><span class="sxs-lookup"><span data-stu-id="4d534-109">The properties correspond to parameters used by those cmdlets.</span></span>

<span data-ttu-id="4d534-110">每两个资源都包含复杂类型的属性。</span><span class="sxs-lookup"><span data-stu-id="4d534-110">Each of the two resources contains properties that are of complex type.</span></span> <span data-ttu-id="4d534-111">复杂类型定义为类的已修改与`ComplexType`限定符。</span><span class="sxs-lookup"><span data-stu-id="4d534-111">The complex types are defined as classes modified with the `ComplexType` qualifier.</span></span>

```csharp

class PswsTest_Service
{
    [Key]      String  ServiceName;
    [Required] String  DisplayName;
    [Required] String  MachineName;
    [Required] String  ServiceType;
    [Required, EmbeddedInstance("PswsTest_DependentService")] String ServicesDependentOn [];
    [Required] Boolean CanPauseAndContinue;
    [Required] Boolean CanShutdown;
    [Required] Boolean CanStop;
    [Required, Etag] String Status;
};

class PswsTest_Process
{
    [Key] SInt32 Id;
    [Required] SInt32 BasePriority;
    [Required, EmbeddedInstance("PowerShell_PSCredential")] String Credential;
    [Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
    [Required] SInt32 HandleCount;
    [Required] String MachineName;
    [Required] SInt32 MainWindowHandle;
    [Required] String MainWindowTitle;
    [Required] SInt32 NonpagedSystemMemorySize;
    [Required] SInt64 NonpagedSystemMemorySize64;
    [Required] SInt32 PagedMemorySize;
    [Required] SInt64 PagedMemorySize64;
    [Required] SInt32 PagedSystemMemorySize;
    [Required] SInt64 PagedSystemMemorySize64;
    [Required] SInt32 PeakPagedMemorySize;
    [Required] SInt64 PeakPagedMemorySize64;
    [Required] SInt32 PeakWorkingSet;
    [Required] SInt64 PeakWorkingSet64;
    [Required] SInt32 PeakVirtualMemorySize;
    [Required] SInt64 PeakVirtualMemorySize64;
    [Required] SInt32 PrivateMemorySize;
    [Required] SInt64 PrivateMemorySize64;
    [Required] String ProcessName;
    [Required] Boolean Responding;
    [Required] SInt32 SessionId;
    [Required, EmbeddedInstance("PswsTest_ProcessStartInfo")] String StartInfo;
    [Required] SInt32 VirtualMemorySize;
    [Required] SInt64 VirtualMemorySize64;
    [Required] Boolean EnableRaisingEvents;
    [Required] SInt32 WorkingSet;
    [Required] SInt64 WorkingSet64;
};

[ComplexType]
class PswsTest_DependentService
{
    String  ServiceName;
};

[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};

[ComplexType]
class PswsTest_ProcessStartInfo
{
    String Verb;
    String Arguments;
    Boolean CreateNoWindow;
    Boolean RedirectStandardInput;
    Boolean RedirectStandardOutput ;
    Boolean RedirectStandardError;
    [EmbeddedInstance("PswsTest_Encoding")] String StandardErrorEncoding;
    [EmbeddedInstance("PswsTest_Encoding")] String StandardOutputEncoding;
    Boolean UseShellExecute;
    String UserName ;
    [EmbeddedInstance("PswsTest_SecureString")] String Password;
    String Domain;
    Boolean LoadUserProfile;
    String FileName;
    String WorkingDirectory ;
    Boolean ErrorDialog ;
    SInt32 ErrorDialogParentHandle;
    String WindowStyle;
};

[ComplexType]
class PswsTest_FileVersionInfo
{
    String Comments;
    String CompanyName;
    SInt32 FileBuildPart;
    String FileDescription;
    sInt32 FileMajorPart;
    SInt32 FileMinorPart;
    String FileName;
    SInt32 FilePrivatePart;
    String FileVersion;
    String InternalName;
    Boolean IsDebug;
    Boolean IsPatched;
    Boolean IsPrivateBuild;
    Boolean IsPreRelease;
    Boolean IsSpecialBuild;
    String Language;
    String LegalCopyright;
    String LegalTrademarks;
    String OriginalFilename;
    String PrivateBuild;
    SInt32 ProductBuildPart;
    SInt32 ProductMajorPart;
    SInt32 ProductMinorPart;
    String ProductName;
    SInt32 ProductPrivatePart;
    String ProductVersion;
    String SpecialBuild;
};

[ComplexType]
class PswsTest_Encoding
{
    String BodyName;
    String EncodingName;
    String HeaderName;
    String WebName;
    SInt32 WindowsCodePage;
    Boolean IsBrowserDisplay;
    Boolean IsBrowserSave;
    Boolean IsMailNewsDisplay;
    Boolean IsMailNewsSave;
    Boolean IsSingleByte;
    [EmbeddedInstance("PswsTest_EncoderFallback")] String EncoderFallback;
    [EmbeddedInstance("PswsTest_DecoderFallback")] String DecoderFallback;
    Boolean IsReadOnly;
    SInt32 CodePage;
};

[ComplexType]
class PswsTest_EncoderFallback
{
    SInt32 MaxCharCount;
};

[ComplexType]
class PswsTest_DecoderFallback
{
    SInt32 MaxCharCount;
};

[ComplexType]
class PswsTest_SecureString
{
    SInt32 Length;
};

[ComplexType]
class PswsTest_ProcessThread
{
    SInt32 BasePriority;
    SInt32 CurrentPriority;
    SInt32 Id;
    SInt32 IdealProcessor;
    String PriorityLevel;
    SInt32 StartAddress;
    String ThreadState;
    String WaitReason;
    SInt32 ProcessorAffinity;
};

[ComplexType]
class PswsTest_Stream
{
    Boolean CanRead;
    Boolean CanSeek;
    Boolean CanTimeout;
    Boolean CanWrite;
    SInt64 Length;
    SInt64 Position;
    SInt32 ReadTimeout;
    SInt32 WriteTimeout;
};

```

## <a name="see-also"></a><span data-ttu-id="4d534-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d534-112">See Also</span></span>

[<span data-ttu-id="4d534-113">创建管理 OData Web 服务</span><span class="sxs-lookup"><span data-stu-id="4d534-113">Creating a Management OData Web Service</span></span>](./creating-a-management-odata-web-service.md)

[<span data-ttu-id="4d534-114">公共资源架构</span><span class="sxs-lookup"><span data-stu-id="4d534-114">Public Resource Schema</span></span>](./public-resource-schema.md)