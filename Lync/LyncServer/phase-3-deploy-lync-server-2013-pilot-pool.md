---
title: 'フェーズ 3: Lync Server 2013 パイロットプールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345fe1a110a4521fddde239681891a1491a17cca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="50e45-102">フェーズ 3: Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="50e45-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e45-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="50e45-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="50e45-104">このセクションでは、Lync Server 2013 のパイロットプールを展開するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="50e45-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="50e45-105">Lync Server 2013 を展開するには、トポロジビルダーを使用して、展開するトポロジとコンポーネントを定義し、Lync Server 2013 コンポーネントの展開のために環境を準備して、最初のフロントエンドでトポロジの設計を公開する必要があります。サーバーをインストールし、展開用のコンポーネント用に Lync Server 2013 ソフトウェアをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="50e45-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="50e45-106">完了すると、Lync Server 2013 パイロットプールの展開は既存の Lync Server 2010 プールと共存します。</span><span class="sxs-lookup"><span data-stu-id="50e45-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="50e45-107">このセクション中</span><span class="sxs-lookup"><span data-stu-id="50e45-107">In This Section</span></span>

  - [<span data-ttu-id="50e45-108">Lync Server の Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="50e45-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="50e45-109">既存の展開環境からのトポロジのダウンロード</span><span class="sxs-lookup"><span data-stu-id="50e45-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="50e45-110">Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="50e45-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="50e45-111">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="50e45-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="50e45-112">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="50e45-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="50e45-113">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="50e45-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

