---
title: 'Lync Server 2013: 保留中の変更を音声ルーティング構成に公開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22cabe1725d899ace42e5b525105c1753c3d9925
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="586e5-102">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="586e5-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="586e5-103">_**最終更新日:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="586e5-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="586e5-104">[**音声ルーティング**] グループの各ページで会議設定のいずれかを変更した後は、ここでの手順を実行して、保留中の変更を確認、公開、またはキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="586e5-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="586e5-105">必ず、一度に 1 人のユーザーだけが音声ルーティング構成の設定を変更するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="586e5-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="586e5-p101">保留中の変更すべては、[<STRONG>すべて確定</STRONG>] コマンドを実行することによって同時に公開する必要があります。保留中の変更のどれかを選択して公開することはできません。保留中の変更を公開する前に、[<STRONG>未確定の変更の確認</STRONG>] コマンドを実行し、公開しない保留中の変更をすべてキャンセルしてください。</span><span class="sxs-lookup"><span data-stu-id="586e5-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="586e5-109">保留中の変更を確定する前に [<STRONG>音声ルーティング</STRONG>] グループのページから移動して離れると、すべての保留中の変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="586e5-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="586e5-110">ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートしておき、後でインポートして更新された構成を公開することができます。</span><span class="sxs-lookup"><span data-stu-id="586e5-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="586e5-111">詳細については、「 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013 でボイスルート構成ファイルをエクスポートする</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="586e5-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="586e5-112">音声ルーティング構成の変更を確認、公開、または取り消すには</span><span class="sxs-lookup"><span data-stu-id="586e5-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="586e5-113">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="586e5-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="586e5-114">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="586e5-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="586e5-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="586e5-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="586e5-116">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="586e5-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="586e5-117">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="586e5-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="586e5-118">[**音声ルーティング**] グループの各ページの設定について、必要な構成の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="586e5-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="586e5-119">公開せずに保留中の変更を確認するには、[**確定**] メニューで [**未確定の変更の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="586e5-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="586e5-120">保留中の変更のいずれかを取り消す場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="586e5-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="586e5-121">[**確定**] メニューで [**すべての未確定の変更のキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="586e5-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="586e5-122">取り消す保留中の変更が含まれる [**音声ルーティング**] ページのタブに移動し、保留中の変更を含む項目を選択し、[**確定**] をクリックして、[**選択した変更のキャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="586e5-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="586e5-123">保留中の変更をすべて確認し、公開しない変更をすべてキャンセルしたら、[**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="586e5-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="586e5-124">保留中の変更すべての一覧が表示された [**未確定の音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="586e5-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="586e5-125">Lync Server コントロールパネルで変更をコミットすると、**正常に公開された音声ルーティング構成**のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="586e5-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

