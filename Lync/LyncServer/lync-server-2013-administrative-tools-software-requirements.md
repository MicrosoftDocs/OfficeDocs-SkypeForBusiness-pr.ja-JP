---
title: 'Lync Server 2013: 管理ツールのソフトウェア要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d1532acc21bc788adc8e52bfd1d562509e105ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="82913-102">Lync Server 2013 の管理ツールソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="82913-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82913-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="82913-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="82913-104">このトピックでは、オペレーティングシステムの要件に加えて、Lync Server 2013 の管理ツールをインストールして使用するために必要なソフトウェアについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82913-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="82913-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="82913-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="82913-106">Lync Server 2013 では、64ビット版の Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="82913-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="82913-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="82913-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="82913-108">Microsoft Lync Server 2013 のコンポーネントを実行するには、Windows PowerShell 3.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="82913-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="82913-109">詳細については、「 [Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82913-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="82913-110">Windows Installer Version 4.5</span><span class="sxs-lookup"><span data-stu-id="82913-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="82913-111">Lync Server 2013 は、Windows インストーラーテクノロジを使用して、さまざまなサーバーの役割をインストール、アンインストール、および保守します。</span><span class="sxs-lookup"><span data-stu-id="82913-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="82913-112">Windows Installer Version 4.5 は、Windows Server オペレーティング システムの再頒布可能なコンポーネントとして入手可能です。</span><span class="sxs-lookup"><span data-stu-id="82913-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="82913-113">Windows インストーラー4.5 は、Windows Server 2012 R2、Windows Server 2012、および Windows Server 2008 R2 と共に出荷されます。これは、Lync 2013 Server を実行しているコンピューターに対してユーティリティをダウンロードする必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82913-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="82913-114">(Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 を実行しているコンピューターにのみインストールできます。)</span><span class="sxs-lookup"><span data-stu-id="82913-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="82913-115">ただし、管理者ワークステーションに Lync Server 管理シェルまたは Lync Server トポロジビルダーをインストールする場合は、Windows インストーラー4.5 をダウンロードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="82913-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="82913-116">このユーティリティには、windows 7 および windows 2008 R2 が付属していますが、Windows オペレーティングシステムの以前のバージョンには同梱されていません。</span><span class="sxs-lookup"><span data-stu-id="82913-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="82913-117">Windows インストーラー4.5 は、「Microsoft ダウンロードセンター」からダウンロード<https://go.microsoft.com/fwlink/p/?linkid=197395>できます。</span><span class="sxs-lookup"><span data-stu-id="82913-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="82913-118">Microsoft Silverlight 5 ブラウザープラグイン</span><span class="sxs-lookup"><span data-stu-id="82913-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="82913-119">Lync Server 2013 コントロールパネルは web ベースのツールであり、Microsoft Silverlight 5 ブラウザープラグインの最新バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82913-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="82913-120">Lync Server 2013 コントロールパネルを起動したときに、このソフトウェアがインストールされていない場合、または以前のバージョンがインストールされている場合は、Lync Server 2013 コントロールパネルで必要なバージョンをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="82913-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82913-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="82913-121">See Also</span></span>


[<span data-ttu-id="82913-122">Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート</span><span class="sxs-lookup"><span data-stu-id="82913-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="82913-123">Lync Server 2013 の管理ツールのインフラストラクチャ要件</span><span class="sxs-lookup"><span data-stu-id="82913-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="82913-124">Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="82913-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

