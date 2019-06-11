---
title: 'Lync Server 2013: 音声ルーティング テスト ケースの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="dc14e-102">Lync Server 2013 での音声ルーティング テスト ケースの作成</span><span class="sxs-lookup"><span data-stu-id="dc14e-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc14e-103">_**最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="dc14e-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="dc14e-104">テストケースを作成するには</span><span class="sxs-lookup"><span data-stu-id="dc14e-104">To create a test case</span></span>

1.  <span data-ttu-id="dc14e-105">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc14e-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dc14e-106">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc14e-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dc14e-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc14e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc14e-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc14e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc14e-109">左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc14e-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="dc14e-110">[**テスト用の音声ルーティング**] ページで [**新規**] をクリックして、新しいテストケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="dc14e-111">[**名前**] に、テストケースの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="dc14e-112">この名前は、エンタープライズ Voip 展開では、すべてのボイスルーティングテストケースの間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc14e-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="dc14e-113">長さは最長32文字で、バックスラッシュ (\\)、ピリオド (.)、またはアンダースコア (\_) に加えて、英数字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc14e-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="dc14e-114">[**ダイヤルする番号**] に、このテストケースに指定したルーティング構成のテストに使用するダイヤルされた番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="dc14e-115">この番号は、ダイヤルプラン、ルーティング、および音声ポリシーに基づいて正規化され、出力として表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc14e-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="dc14e-116">[**ダイヤルプラン**] ボックスの一覧で、テストの実行時に使用するダイヤルプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="dc14e-117">[既定値はグローバルダイヤルプランです。</span><span class="sxs-lookup"><span data-stu-id="dc14e-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="dc14e-118">[**音声ポリシー** ] ボックスの一覧で、テストの実行時に使用する音声ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="dc14e-119">[既定値はグローバルボイスポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dc14e-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="dc14e-120">**期待される翻訳**では、翻訳後に表示されるはずの形式で電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="dc14e-121">これは、選択したダイヤルプランで一致する最初の正規化ルールによって翻訳された後に、テストする電話番号の値です。</span><span class="sxs-lookup"><span data-stu-id="dc14e-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="dc14e-122">テストケースを実行したときに、テストしている数値が予期した**翻訳**の値ではない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="dc14e-123">省略[予期される**PSTN 使用量**] ボックスの一覧で、指定したダイヤルプランとボイスポリシーに基づいてテストケースを実行するときに使用されると予想される公衆交換電話網 (PSTN) 利用状況レコードを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="dc14e-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="dc14e-124">別の PSTN 利用状況レコードが使用されている場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="dc14e-125">省略[想定される**ルート**] ボックスの一覧で、指定したダイヤルプランとボイスポリシーに基づいてテストケースを実行するときに使用されると予想されるボイスルートを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="dc14e-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="dc14e-126">別のボイスルートが使用されている場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="dc14e-127">省略[**実行**] をクリックしてテストケースを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="dc14e-128">結果がページの右側のパネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc14e-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="dc14e-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc14e-129">Click **OK**.</span></span>

14. <span data-ttu-id="dc14e-130">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc14e-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc14e-131">ボイスルーティングテストケースを作成するたびに、[<STRONG>すべてコミット</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc14e-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="dc14e-132">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc14e-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="dc14e-133">テストで採用されているダイヤルプランが、プラス記号 (+ 12065551219 など) で始まる電話番号を正規化していない場合、そのプランが原因でボイスルーティングテストが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc14e-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="dc14e-134">(ダイヤルプランとボイスルートは動作しますが、実際にはテスト-CsDialPlan は成功します。</span><span class="sxs-lookup"><span data-stu-id="dc14e-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="dc14e-135">ただし、音声ルーティングテストが失敗することがあります。)ボイスルートをテストするときは、この点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc14e-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc14e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc14e-136">See Also</span></span>


[<span data-ttu-id="dc14e-137">Lync Server 2013 での音声ルーティング テスト ケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="dc14e-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="dc14e-138">Lync Server 2013 音声ルーティング テスト ケースのインポート</span><span class="sxs-lookup"><span data-stu-id="dc14e-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="dc14e-139">Lync Server 2013 でのダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="dc14e-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="dc14e-140">Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="dc14e-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

