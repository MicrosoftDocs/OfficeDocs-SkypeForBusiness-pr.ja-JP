---
title: 'Lync Server 2013: 音声ルーティングテストケースのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bb5d8e8f29edf0397c9bb9fa12592087ea517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="b6763-102">Lync Server 2013 での音声ルーティングテストケースのインポート</span><span class="sxs-lookup"><span data-stu-id="b6763-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6763-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b6763-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b6763-104">テストケースでは、組織内のボイスルートをテストする方法が提供されます。ダイヤルする番号、使用するダイヤルプランと音声ポリシーなどを定義し、Lync Server 2013 は、これらの条件が満たされた場合に、指定された数の successfully に PSTN ネットワークにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6763-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="b6763-105">Lync Server コントロールパネルを使用して作成できるテストケースは、通常、ケースが最初に作成されて実行されたサーバーにのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="b6763-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="b6763-106">ただし、これらのテスト ケースは XML ファイル (拡張子 .vtest) としてエクスポートし、他のサーバーにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b6763-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="b6763-107">これにより、同じテストをトポロジの別の地点に配置された別のコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6763-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="b6763-108">音声ルーティングのテスト ケースをインポートするには</span><span class="sxs-lookup"><span data-stu-id="b6763-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="b6763-109">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b6763-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b6763-110">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6763-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b6763-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b6763-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b6763-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6763-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b6763-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6763-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="b6763-114">[**操作**] メニューの [**テスト ケースのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6763-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="b6763-115">インポートするテスト ケースのファイル (.vtest) を探して、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6763-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="b6763-116">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6763-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6763-117">.vtest ファイルをインポートするときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、テスト ケースを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6763-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="b6763-118">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6763-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b6763-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6763-119">See Also</span></span>


[<span data-ttu-id="b6763-120">Lync Server 2013 での音声ルーティングテストケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b6763-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

