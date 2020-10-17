---
title: 'Lync Server 2013: 音声ルーティングテストケースを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da110d7e3bfb7188384163cb572591d0bf7f8ff3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501774"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="1b670-102">Lync Server 2013 での音声ルーティングテストケースの作成</span><span class="sxs-lookup"><span data-stu-id="1b670-102">Create a voice routing test case in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b670-103">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="1b670-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="1b670-104">テスト ケースを作成するには</span><span class="sxs-lookup"><span data-stu-id="1b670-104">To create a test case</span></span>

1.  <span data-ttu-id="1b670-105">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1b670-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1b670-106">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b670-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1b670-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b670-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b670-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b670-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b670-109">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b670-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="1b670-110">[**音声ルーティングのテスト**] ページで、[**新規**] をクリックして、新しいテスト ケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b670-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="1b670-111">[**名前**] フィールドに、テスト ケースの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1b670-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="1b670-112">名前は、エンタープライズ VoIP 展開内のすべての音声ルーティング テスト ケースの中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b670-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="1b670-113">最大で32文字まで指定でき、円記号 ( \\ )、ピリオド (.)、またはアンダースコア () に加えて、英数字を含めることができ \_ ます。</span><span class="sxs-lookup"><span data-stu-id="1b670-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="1b670-p104">[**テスト対象のダイヤル番号**] に、このテスト ケースで指定しているルーティング構成のテストに使用されるダイヤル番号を入力します。この番号は、ダイヤル プラン、ルート、および音声ポリシーに基づいて正規化され、出力として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b670-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="1b670-p105">[**ダイヤル プラン**] リストで、テスト実行時に使用するダイヤル プランを選択します。 既定値はグローバル ダイヤル プランです。</span><span class="sxs-lookup"><span data-stu-id="1b670-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="1b670-p106">[**音声ポリシー**] リストで、テスト実行時に使用する音声ポリシーを選択します。 既定値はグローバル音声ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="1b670-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="1b670-p107">[**予想される変換**] に、変換後の予想表示形式で電話番号を入力します。これは、選択したダイヤル プランで最初に一致する正規化ルールによって変換された後の、テスト対象の電話番号の値です。テスト ケースの実行時に、テスト対象の番号が [**予想される変換**] の値にならない場合、テストは不合格です。</span><span class="sxs-lookup"><span data-stu-id="1b670-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="1b670-p108">(オプション) [**予想される PSTN 使用法**] リストで、指定したダイヤル プランおよび音声ポリシーに基づいて、テスト ケースの実行時に使用されることが予想される公衆交換電話網 (PSTN) 使用法レコードを選択できます。別の PSTN 使用法レコードが使用される場合、テストは不合格です。</span><span class="sxs-lookup"><span data-stu-id="1b670-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="1b670-p109">(オプション) [**予想されるルート**] リストで、指定したダイヤル プランおよび音声ポリシーに基づいて、テスト ケースの実行時に使用されることが予想されるボイス ルートを選択できます。 別のボイス ルートが使用される場合、テストは不合格です。</span><span class="sxs-lookup"><span data-stu-id="1b670-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="1b670-p110">(オプション) [**実行**] をクリックして、テスト ケースを実行します。 結果は、ページの右パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b670-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="1b670-129">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b670-129">Click **OK**.</span></span>

14. <span data-ttu-id="1b670-130">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b670-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b670-131">音声ルーティング テスト ケースを作成するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b670-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="1b670-132">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b670-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="1b670-133">テストで採用されているダイヤルプランが、プラス記号 (+ 12065551219 など) で始まる電話番号を正規化している場合、そのプランでは音声ルーティングテストが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b670-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="1b670-134">(実際には、ダイヤルプランと音声ルートは機能しますが、実際には Test-CsDialPlan は成功します。</span><span class="sxs-lookup"><span data-stu-id="1b670-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="1b670-135">ただし、音声ルーティングテストは失敗する可能性があります。)これは、音声ルートをテストするときに留意すべきことです。</span><span class="sxs-lookup"><span data-stu-id="1b670-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b670-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b670-136">See Also</span></span>


[<span data-ttu-id="1b670-137">Lync Server 2013 での音声ルーティングテストケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="1b670-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="1b670-138">Lync Server 2013 での音声ルーティングテストケースのインポート</span><span class="sxs-lookup"><span data-stu-id="1b670-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="1b670-139">Lync Server 2013 でのダイヤルプランの構成</span><span class="sxs-lookup"><span data-stu-id="1b670-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="1b670-140">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</span><span class="sxs-lookup"><span data-stu-id="1b670-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

