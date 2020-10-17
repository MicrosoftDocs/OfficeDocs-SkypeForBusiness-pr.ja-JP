---
title: 'Lync Server 2013: サポートされている仮想化テクノロジと既知の制限'
description: 'Lync Server 2013: サポートされている仮想化テクノロジと既知の制限。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544613"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="ce323-103">Lync Server 2013 でサポートされている仮想化テクノロジと既知の制限</span><span class="sxs-lookup"><span data-stu-id="ce323-103">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce323-104">_**トピックの最終更新日:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="ce323-104">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="ce323-105">Lync VDI プラグインは、サポートされている仮想化テクノロジに対して音声およびビデオ通話を許可します。</span><span class="sxs-lookup"><span data-stu-id="ce323-105">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="ce323-106">これにより、microsoft Lync 2010 ホワイトペーパーの「Microsoft Lync Server 2010」に記載されている [クライアント仮想化](https://go.microsoft.com/fwlink/?linkid=330447) の機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="ce323-106">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="ce323-107">標準電話の規制に準拠するには、E911 のサポートも含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce323-107">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="ce323-108">次のセクションでは、Lync VDI プラグインによってサポートされる仮想化テクノロジと既知の機能制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce323-108">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="ce323-109">仮想化テクノロジのサポート</span><span class="sxs-lookup"><span data-stu-id="ce323-109">Support for Virtualization Technologies</span></span>

<span data-ttu-id="ce323-110">Lync VDI プラグインは、個人用仮想デスクトップシナリオでは完全なデスクトップリモート処理をサポートしますが、リモートデスクトップセッションシナリオではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ce323-110">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="ce323-111">これらのシナリオは、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="ce323-111">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="ce323-112">**サポート: カスタマイズされた仮想デスクトップまたは仮想デスクトップインフラストラクチャ (VDI)。**    このシナリオでは、ユーザーごとにカスタマイズ可能な仮想デスクトップにログオンし、セッション間で保持されるファイルをデスクトップに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="ce323-112">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="ce323-113">Microsoft リモートデスクトップサービス、VMware ホライズン表示、および Citrix XenDesktop は、Lync での使用がテストされている実装です。</span><span class="sxs-lookup"><span data-stu-id="ce323-113">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="ce323-114">Microsoft によってテストされたベンダー固有の VDI 環境およびクライアントハードウェアの詳細については、「 [Microsoft Lync 用のインフラストラクチャ認定](https://go.microsoft.com/fwlink/?linkid=313435)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce323-114">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="ce323-115">**サポート対象外: リモートデスクトップセッション。**    このシナリオでは、ユーザーごとに、カスタマイズできない汎用の仮想デスクトップセッションにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ce323-115">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="ce323-116">実装の例には、Microsoft リモートデスクトップセッション (RDSH) と citrix XenApp を Citrix レシーバーと組み合わせたものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce323-116">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="ce323-117">Lync VDI プラグインは、アプリケーションの仮想化などの他の仮想化テクノロジをサポートしていません。これにより、完全なアプリケーションをローカルにインストールすることなく、アプリケーションを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ce323-117">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="ce323-118">実装の例としては、Citrix XenApp と Microsoft Application Virtualization (App-v) があります。</span><span class="sxs-lookup"><span data-stu-id="ce323-118">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="ce323-119">アプリケーションのストリーミング、アプリケーションのリモート処理、および混合仮想化モード (たとえば、完全なデスクトップリモート処理でのアプリケーションのリモート処理) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ce323-119">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="ce323-120">拡張機能を有効にするために、Lync VDI プラグインは、動的仮想チャネル (DVCs) と呼ばれるプラットフォームに依存しない Api を使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ce323-120">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="ce323-121">Lync で明示的にサポートされていないシナリオについては、「VDI ソリューションプロバイダーからのサポートステートメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce323-121">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="ce323-122">既知の機能制限</span><span class="sxs-lookup"><span data-stu-id="ce323-122">Known Feature Limitations</span></span>

<span data-ttu-id="ce323-123">VDI 環境で Lync 2013 を使用する場合の既知の制限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ce323-123">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="ce323-124">通話委任および応答グループエージェント匿名化機能のサポートには制限があります。</span><span class="sxs-lookup"><span data-stu-id="ce323-124">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="ce323-125">以下の機能はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ce323-125">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="ce323-126">統合オーディオ デバイスとビデオ デバイスのチューニング ページ</span><span class="sxs-lookup"><span data-stu-id="ce323-126">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="ce323-127">マルチビュービデオ。</span><span class="sxs-lookup"><span data-stu-id="ce323-127">Multiple-view video.</span></span>
    
      - <span data-ttu-id="ce323-128">会話の録音</span><span class="sxs-lookup"><span data-stu-id="ce323-128">Recording of conversations.</span></span>
    
      - <span data-ttu-id="ce323-129">リモートデスクトップサービス (RDS)。</span><span class="sxs-lookup"><span data-stu-id="ce323-129">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="ce323-130">匿名での会議への参加 (つまり、組織とフェデレーションされない組織によってホストされている Lync 会議への参加)。</span><span class="sxs-lookup"><span data-stu-id="ce323-130">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="ce323-131">Lync VDI プラグインを Lync Phone Edition デバイスと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="ce323-131">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="ce323-132">ネットワーク停止時の通話の継続</span><span class="sxs-lookup"><span data-stu-id="ce323-132">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="ce323-133">カスタマイズされた着信音と音楽の保持機能。</span><span class="sxs-lookup"><span data-stu-id="ce323-133">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="ce323-134">Lync VDI プラグインは、Microsoft 365 または Office 365 環境ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ce323-134">The Lync VDI plug-in is not supported in a Microsoft 365 or Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

