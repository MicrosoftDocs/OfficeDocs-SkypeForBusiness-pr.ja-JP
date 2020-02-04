---
title: 'Lync Server 2013: プールのアーカイブオプションを構成する'
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
ms.openlocfilehash: f63f20dc0ae80584c1eac4489a07925e90fe3e29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="49636-102">Lync Server 2013 でプールのアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="49636-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49636-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="49636-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="49636-104">特定のプールに適用されるアーカイブオプションを指定するには、各プールのアーカイブ構成でオプションを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="49636-104">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools.</span></span> <span data-ttu-id="49636-105">プール構成はグローバル構成とサイト構成より優先されますが、その対象はプール構成に指定されているプールに限定されます。</span><span class="sxs-lookup"><span data-stu-id="49636-105">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="49636-106">アーカイブ構成のしくみ (グローバル、サイト、プール構成の階層など) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49636-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49636-107">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49636-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="49636-108">詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49636-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="49636-109">プールレベルでアーカイブオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="49636-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="49636-110">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="49636-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49636-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="49636-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="49636-112">Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49636-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="49636-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49636-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="49636-114">[**アーカイブ構成**] ページで、[**新規**]、[**プール構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="49636-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="49636-115">[**サービスの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="49636-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="49636-116">[**新規アーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のアーカイブ オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="49636-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="49636-117">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="49636-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="49636-118">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="49636-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="49636-119">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="49636-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="49636-120">また、[**新規アーカイブ設定**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="49636-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="49636-121">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="49636-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="49636-122">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="49636-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="49636-123">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="49636-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="49636-124">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="49636-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="49636-125">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49636-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="49636-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49636-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

