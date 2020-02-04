---
title: 'Lync Server 2013: サイトのアーカイブオプションを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2b70242388ca00a7bf43ec535ae1231fb77644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="2d7d0-102">Lync Server 2013 でサイトのアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="2d7d0-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d7d0-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2d7d0-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2d7d0-104">特定のサイトに適用されるアーカイブオプションを指定するには、各サイトのアーカイブ構成でオプションを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="2d7d0-105">サイト構成はグローバル構成より優先されますが、その対象はサイト構成に指定されているサイトに限定されます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="2d7d0-106">プール構成がサイト構成を上書きする</span><span class="sxs-lookup"><span data-stu-id="2d7d0-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="2d7d0-107">アーカイブ構成のしくみ (グローバル、サイト、プール構成の階層など) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d7d0-108">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d7d0-109">アーカイブを有効にするには、内部または外部の通信のアーカイブを管理するためのアーカイブ ポリシーを、グローバル レベル (必要に応じて、サイト レベルおよびユーザー レベル) で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="2d7d0-110">ユーザー レベルのポリシーを構成する場合は、ユーザー ポリシーをユーザーに割り当てる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="2d7d0-111">アーカイブポリシーの作成と構成の詳細については、「運用ドキュメントの「 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013 での社内および社外の通信のアーカイブを管理する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="2d7d0-112">サイトレベルでアーカイブオプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="2d7d0-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="2d7d0-113">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d7d0-114">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="2d7d0-115">Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2d7d0-116">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="2d7d0-117">[**アーカイブ構成**] ページで、[**新規作成**] をクリックし、[**サイト構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="2d7d0-118">[**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="2d7d0-119">[**新しいアーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="2d7d0-120">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="2d7d0-121">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="2d7d0-122">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="2d7d0-123">[**新しいアーカイブ設定**] で、次の操作も実行します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="2d7d0-124">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="2d7d0-125">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="2d7d0-126">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="2d7d0-127">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="2d7d0-128">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="2d7d0-129">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

