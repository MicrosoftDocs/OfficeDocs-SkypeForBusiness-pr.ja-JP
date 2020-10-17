---
title: パイロット プールとレガシ プールの共存の確認
description: パイロットプールとレガシプールの共存を確認します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b910939b59fdaed6df32ae504eb2719435a0161e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555553"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="25acd-103">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="25acd-103">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25acd-104">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="25acd-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="25acd-105">パイロット プールを展開した後、プール情報を表示するための管理ツールを使用して、2 つのプールの共存を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25acd-105">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="25acd-106">Lync Server 2013 プールおよび従来のプールの場合は、Lync Server 2013 コントロールパネルおよびトポロジビルダーのツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25acd-106">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="25acd-107">Lync Server 2013 サービスが開始されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="25acd-107">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="25acd-108">Lync Server 2013 フロントエンドサーバーから、[管理ツール] [サービス] アプレットに移動し \\ ます。</span><span class="sxs-lookup"><span data-stu-id="25acd-108">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="25acd-109">次のサービスがフロントエンド サーバーで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25acd-109">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="25acd-110">**Lync Server 2013 サービス**</span><span class="sxs-lookup"><span data-stu-id="25acd-110">**Lync Server 2013 services**</span></span>

<span data-ttu-id="25acd-111">![開始された Lync Server サービスの一覧](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "開始された Lync Server サービスの一覧")</span><span class="sxs-lookup"><span data-stu-id="25acd-111">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="25acd-112">Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="25acd-112">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="25acd-113">Lync server 2013 展開のフロントエンドサーバーから、Lync Server 2013 コントロールパネルを開き、[Lync Server 2010] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="25acd-113">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="25acd-114">この手順を繰り返して、Lync Server 2013 プールを開きます。</span><span class="sxs-lookup"><span data-stu-id="25acd-114">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="25acd-115">**Lync Server 2013 コントロール パネルを開く**</span><span class="sxs-lookup"><span data-stu-id="25acd-115">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="25acd-116">![[URL の選択] ダイアログボックス](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "[URL の選択] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="25acd-116">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25acd-117">Lync Server 2013 では、Lync Server コントロールパネルを使用する前に silverlight バージョン5に Silverlight をアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25acd-117">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="25acd-118">このトポロジには、Lync Server 2010 および Lync Server 2013 のサーバーの役割が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="25acd-118">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="25acd-119">**Lync Server 2013 コントロール パネルの [トポロジ] ページ**</span><span class="sxs-lookup"><span data-stu-id="25acd-119">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="25acd-120">![Lync Server コントロールパネル-トポロジページ](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server コントロールパネル-トポロジページ")</span><span class="sxs-lookup"><span data-stu-id="25acd-120">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="25acd-121">Lync Server 2010 トポロジビルダーでトポロジを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="25acd-121">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="25acd-122">Lync Server 2010 トポロジビルダーを使用してトポロジを開こうとすると、以下のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="25acd-122">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="25acd-123">このトポロジは、Lync Server 2013 トポロジビルダーを使用してのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="25acd-123">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="25acd-124">Lync server 2013 および Lync Server 2010 の両方のプールを作成するには、Lync Server 2013 トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25acd-124">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="25acd-125">**Lync Server 2010 トポロジ ビルダーのエラー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="25acd-125">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="25acd-126">![Lync Server トポロジビルダー MMC スナップエラー](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server トポロジビルダー MMC スナップエラー")</span><span class="sxs-lookup"><span data-stu-id="25acd-126">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

