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
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="6f416-102">Lync Server 2013 の管理ツールのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="6f416-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f416-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6f416-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6f416-104">このトピックでは、オペレーティングシステムの要件に加えて、Lync Server 2013 管理ツールをインストールして使用するために必要なソフトウェアについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f416-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="6f416-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6f416-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="6f416-106">Lync Server 2013 では、64ビット版の Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f416-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="6f416-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="6f416-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="6f416-108">Microsoft Lync Server 2013 のコンポーネントを実行するには、Windows PowerShell 3.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f416-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6f416-109">詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f416-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="6f416-110">Windows インストーラーバージョン4.5</span><span class="sxs-lookup"><span data-stu-id="6f416-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="6f416-111">Lync Server 2013 は、Windows インストーラーテクノロジを使用して、さまざまなサーバーの役割をインストール、アンインストール、維持します。</span><span class="sxs-lookup"><span data-stu-id="6f416-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="6f416-112">Windows インストーラーバージョン4.5 は、Windows Server オペレーティングシステムの再頒布可能コンポーネントとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="6f416-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="6f416-113">Windows Installer 4.5 は windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 と共に出荷されているため、Lync Server 2013 を実行しているコンピューターでは、このユーティリティをダウンロードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f416-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="6f416-114">(Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 を実行しているコンピューターにのみインストールできます)。</span><span class="sxs-lookup"><span data-stu-id="6f416-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="6f416-115">ただし、Lync Server 管理シェルまたは Lync Server Topology Builder を管理者のワークステーションにインストールする場合は、Windows インストーラー4.5 のダウンロードが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6f416-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="6f416-116">このユーティリティには windows 7 と Windows 2008 R2 が付属していますが、以前のバージョンの Windows オペレーティングシステムには付属していません。</span><span class="sxs-lookup"><span data-stu-id="6f416-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="6f416-117">Windows インストーラー4.5 は、Microsoft ダウンロードセンターからダウンロードでき<http://go.microsoft.com/fwlink/p/?linkid=197395>ます。</span><span class="sxs-lookup"><span data-stu-id="6f416-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="6f416-118">Microsoft Silverlight 5 browser プラグイン</span><span class="sxs-lookup"><span data-stu-id="6f416-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="6f416-119">Lync Server 2013 コントロールパネルは web ベースのツールであり、Microsoft Silverlight 5 browser プラグインの最新バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f416-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="6f416-120">Lync Server 2013 コントロールパネルを起動したときに、このソフトウェアがインストールされていない場合、または以前のバージョンがインストールされている場合は、Lync Server 2013 コントロールパネルで、必要なバージョンをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6f416-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f416-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f416-121">See Also</span></span>


[<span data-ttu-id="6f416-122">Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート</span><span class="sxs-lookup"><span data-stu-id="6f416-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="6f416-123">Lync Server 2013 での管理ツールインフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="6f416-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="6f416-124">Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6f416-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

