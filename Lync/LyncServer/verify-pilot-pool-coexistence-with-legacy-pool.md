---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de258bff926e2e100fa7c9a4952a4d70ca64373
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="2dc36-102">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="2dc36-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dc36-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="2dc36-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="2dc36-104">パイロットプールを展開した後、管理ツールを使用してプール情報を表示し、2つのプールの共存を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dc36-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="2dc36-105">Lync Server 2013 プールと従来のプールについては、「Lync Server 2013 コントロールパネル」および「トポロジビルダーツール」を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dc36-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="2dc36-106">Lync Server 2013 サービスが開始されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="2dc36-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="2dc36-107">Lync Server 2013 フロントエンドサーバーから、管理ツール\\の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="2dc36-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2dc36-108">フロントエンドサーバーで次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2dc36-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="2dc36-109">**Lync Server 2013 サービス**</span><span class="sxs-lookup"><span data-stu-id="2dc36-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="2dc36-110">![開始された Lync Server サービスの一覧](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "開始された Lync Server サービスの一覧")</span><span class="sxs-lookup"><span data-stu-id="2dc36-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="2dc36-111">Lync Server 2013 コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="2dc36-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="2dc36-112">Lync server 2013 展開のフロントエンドサーバーから、Lync Server 2013 コントロールパネルを開き、Lync Server 2010 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2dc36-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="2dc36-113">手順を繰り返して Lync Server 2013 プールを開きます。</span><span class="sxs-lookup"><span data-stu-id="2dc36-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="2dc36-114">**Lync Server 2013 コントロールパネルを開く**</span><span class="sxs-lookup"><span data-stu-id="2dc36-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="2dc36-115">![[URL の選択] ダイアログボックス](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "[URL の選択] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="2dc36-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2dc36-116">Lync server 2013 では、Lync Server コントロールパネルを使用する前に Silverlight のバージョン5に Silverlight をアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dc36-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="2dc36-117">このトポロジには、Lync Server 2010 および Lync Server 2013 サーバーの役割が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2dc36-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="2dc36-118">**Lync Server 2013 コントロールパネルのトポロジページ**</span><span class="sxs-lookup"><span data-stu-id="2dc36-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="2dc36-119">![Lync Server コントロールパネル-トポロジページ](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server コントロールパネル-トポロジページ")</span><span class="sxs-lookup"><span data-stu-id="2dc36-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="2dc36-120">Lync Server 2010 トポロジビルダーでトポロジを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="2dc36-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="2dc36-121">Lync Server 2010 トポロジビルダーを使用してトポロジを開こうとすると、以下のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2dc36-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="2dc36-122">トポロジを表示できるのは、Lync Server 2013 Topology Builder を使用している場合のみです。</span><span class="sxs-lookup"><span data-stu-id="2dc36-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="2dc36-123">Lync server 2013 と Lync Server 2010 の両方のプールを作成するには、Lync Server 2013 トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dc36-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="2dc36-124">**Lync Server 2010 トポロジビルダーのエラーメッセージ**</span><span class="sxs-lookup"><span data-stu-id="2dc36-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="2dc36-125">![Lync Server Topology BUILDER MMC スナップエラー](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology BUILDER MMC スナップエラー")</span><span class="sxs-lookup"><span data-stu-id="2dc36-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

