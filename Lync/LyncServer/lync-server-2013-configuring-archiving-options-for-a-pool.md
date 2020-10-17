---
title: 'Lync Server 2013: プールのアーカイブオプションの構成'
description: 'Lync Server 2013: プールのアーカイブオプションの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3b28fd12fab5883e3be319bec169d13c539b1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562573"
---
# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="07933-103">Lync Server 2013 でのプールのアーカイブオプションの構成</span><span class="sxs-lookup"><span data-stu-id="07933-103">Configuring Archiving options for a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07933-104">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="07933-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="07933-p101">特定のプールそれぞれのアーカイブ構成を作成してオプションを構成することによって、これらのプールに適用するアーカイブ オプションを指定できます。プール構成はグローバル構成とサイト構成より優先されますが、プール構成で指定したプールにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="07933-p101">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="07933-107">グローバル構成、サイト構成、およびプール構成の階層など、アーカイブ構成のしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07933-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07933-108">アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07933-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="07933-109">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07933-109">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="07933-110">プール レベルでアーカイブ オプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="07933-110">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="07933-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="07933-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07933-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07933-112">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="07933-113">Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07933-113">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="07933-114">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07933-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="07933-115">[**アーカイブ構成**] ページで、[**新規**]、[**プール構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="07933-115">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="07933-116">[**サービスの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="07933-116">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="07933-117">[**新規 アーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リストで、次のアーカイブ オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="07933-117">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="07933-118">[**アーカイブを無効にする**]</span><span class="sxs-lookup"><span data-stu-id="07933-118">**Disable archiving**</span></span>
    
      - <span data-ttu-id="07933-119">[**IM セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="07933-119">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="07933-120">[**IM および Web 会議セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="07933-120">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="07933-121">また、[**新規 アーカイブ設定**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="07933-121">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="07933-122">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="07933-122">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="07933-123">Microsoft Exchange Server を使用してアーカイブデータを保存するには、[ **Microsoft exchange 統合** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="07933-123">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="07933-124">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="07933-124">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="07933-125">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="07933-125">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="07933-126">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07933-126">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="07933-127">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07933-127">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

