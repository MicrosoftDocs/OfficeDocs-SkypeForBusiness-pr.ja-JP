---
title: 'Lync Server 2013: アーカイブオプションをグローバルレベルで構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59ab58cbee3479bff424e7d69d475e1d83fdd3bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="ff726-102">Lync Server 2013 のグローバルレベルでアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="ff726-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff726-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="ff726-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="ff726-104">トポロジにアーカイブを追加してトポロジを公開すると、Lync Server によってアーカイブ用のグローバル構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ff726-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="ff726-105">既定では、グローバル構成ではアーカイブオプションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="ff726-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="ff726-106">グローバル構成より優先されるサイト構成またはプール構成を設定しない限り、グローバル構成は、展開全体に対して有効化されるオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="ff726-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="ff726-107">アーカイブ構成のしくみ (グローバル、サイト、プール構成の階層など) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff726-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff726-108">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff726-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="ff726-109">グローバルレベルでアーカイブオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="ff726-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="ff726-110">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ff726-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff726-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ff726-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="ff726-112">Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff726-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff726-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff726-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="ff726-114">[**アーカイブ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff726-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ff726-115">[**編集アーカイブ設定 - Global**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかのアーカイブ オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff726-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="ff726-116">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="ff726-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="ff726-117">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="ff726-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="ff726-118">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="ff726-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="ff726-119">また、[**アーカイブ設定 - グローバル**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff726-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="ff726-120">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ff726-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="ff726-121">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ff726-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="ff726-122">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff726-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="ff726-123">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff726-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="ff726-124">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff726-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="ff726-125">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff726-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

