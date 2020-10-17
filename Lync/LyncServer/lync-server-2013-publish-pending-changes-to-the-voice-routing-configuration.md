---
title: 'Lync Server 2013: 音声ルーティング構成に対する保留中の変更の公開'
description: 'Lync Server 2013: 保留中の変更を音声ルーティング構成に公開します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565453"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="dfff0-103">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="dfff0-103">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfff0-104">_**トピックの最終更新日:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="dfff0-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="dfff0-105">**音声ルーティング**グループのページで構成設定を変更した後、次の手順を実行して、保留中の変更を確認、公開、またはキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dfff0-106">一度に1人のユーザーだけが音声ルーティング構成設定を変更するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="dfff0-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="dfff0-107">すべての保留中の変更は、[ <STRONG>すべて確定</STRONG> ] コマンドを実行することによって同時に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfff0-107">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command.</span></span> <span data-ttu-id="dfff0-108">保留中の変更を選択的に発行することはできません。</span><span class="sxs-lookup"><span data-stu-id="dfff0-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="dfff0-109">保留中の変更を公開する前に、[ <STRONG>未確定の変更の確認</STRONG> ] コマンドを実行して、公開しない構成の変更をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-109">Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="dfff0-110">保留中の変更をコミットする前に、 <STRONG>音声ルーティング</STRONG> グループのページから移動すると、保留中の変更はすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="dfff0-110">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="dfff0-111">ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートして、更新された構成をインポートして公開することができます。</span><span class="sxs-lookup"><span data-stu-id="dfff0-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="dfff0-112">詳細については、「 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013 で音声ルート構成ファイルをエクスポートする</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfff0-112">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="dfff0-113">音声ルーティング構成の変更を確認、公開、または取り消すには</span><span class="sxs-lookup"><span data-stu-id="dfff0-113">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="dfff0-114">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dfff0-115">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfff0-115">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dfff0-116">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dfff0-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dfff0-117">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfff0-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dfff0-118">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-118">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="dfff0-119">**音声ルーティング**グループの各ページの設定に対して、必要な構成の変更を行います。</span><span class="sxs-lookup"><span data-stu-id="dfff0-119">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="dfff0-120">保留中の変更を公開せずに確認するには、[**コミット**] メニューの [**未確定の変更を確認**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfff0-120">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="dfff0-121">保留中の変更をすべて取り消す場合は、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfff0-121">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="dfff0-122">[**コミット**] メニューから [コミットされていない**変更をすべてキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfff0-122">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="dfff0-123">保留中の変更がある [ **音声ルーティング** ] ページのタブに移動して、保留中の変更があるアイテムを選択し、[ **確定**] をクリックして、[ **選択した変更のキャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-123">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="dfff0-124">保留中の変更をすべて確認し、公開しない変更をすべてキャンセルしたら、[ **確定**] をクリックし、[ **すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-124">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="dfff0-125">保留中の変更すべての一覧を表示する、[コミットされていない **音声構成設定** ] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfff0-125">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="dfff0-126">Lync Server コントロールパネルが変更をコミットすると、[ **音声ルーティング構成の発行に成功しまし** た] というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfff0-126">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

