---
title: 'Lync Server 2013: 非公式の音声ルーティングテストを実行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="021ca-102">Lync Server 2013 で非公式の音声ルーティングテストを実行する</span><span class="sxs-lookup"><span data-stu-id="021ca-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="021ca-103">_**最終更新日:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="021ca-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="021ca-104">[**音声ルーティングのテストケース情報の作成**] ダイアログボックスを使用して、実際のテストケースを作成する前に非公式なテストを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="021ca-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="021ca-105">テストの結果に問題がなければ、正式なテストケースとして保存するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="021ca-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="021ca-106">非公式のボイスルーティングテストを実行するには</span><span class="sxs-lookup"><span data-stu-id="021ca-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="021ca-107">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="021ca-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="021ca-108">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ca-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="021ca-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="021ca-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="021ca-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="021ca-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="021ca-111">左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="021ca-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="021ca-112">[**音声ルーティングのテスト**] ページで、[**ボイスルーティングテストケース情報の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="021ca-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="021ca-113">[**ダイヤル先番号**] フィールドに、このテストに使用する電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="021ca-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="021ca-114">この数値は正規化され、[**結果**] ウィンドウの [正規化された**数値**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="021ca-115">[**ダイヤルプラン**] ボックスの一覧で、ダイヤルした番号のテストに使用するダイヤルプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="021ca-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="021ca-116">[既定値はグローバルダイヤルプランです。</span><span class="sxs-lookup"><span data-stu-id="021ca-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="021ca-117">テストを実行すると、ダイヤルした番号に一致するこのダイヤルプランの最初の正規化ルールが、[**結果**] ウィンドウの [**正規化ルール**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="021ca-118">[**音声ポリシー** ] ボックスの一覧で、ダイヤルした番号のテストに使用する音声ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="021ca-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="021ca-119">[既定値はグローバルボイスポリシーです。</span><span class="sxs-lookup"><span data-stu-id="021ca-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="021ca-120">テストを実行すると、この音声ポリシーの最初に一致した PSTN 使用状況レコードが、[**結果**] ウィンドウの**最初の pstn 使用状況**フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="021ca-121">また、この PSTN 使用状況レコードに関連付けられている最初の音声ルートは、 **1 番目の route**フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="021ca-122">省略特定のユーザーに割り当てられている音声ポリシーを使ってダイヤルした番号をテストする場合は、[**ユーザーから**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="021ca-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="021ca-123">[**参照**] をクリックして、[**エンタープライズ Voip ユーザーの選択**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="021ca-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="021ca-124">[**検索**] をクリックすると、エンタープライズ voip が有効になっているユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="021ca-125">このテストに使用する、割り当てられた音声ポリシーを持つユーザー名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="021ca-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="021ca-126">[**ポリシー** ] フィールドに、選択したユーザーに割り当てられた音声ポリシーが設定されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="021ca-127">テストを実行すると、この音声ポリシーの最初に一致する公衆交換電話網 (PSTN) 利用状況レコードが、[**結果**] ウィンドウの**最初の PSTN 使用状況**フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="021ca-128">また、この PSTN 使用状況レコードに関連付けられている最初の音声ルートは、 **1 番目の route**フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="021ca-129">[**実行**] をクリックしてテストケースを実行します。</span><span class="sxs-lookup"><span data-stu-id="021ca-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="021ca-130">結果は、ダイアログボックスの右側のパネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="021ca-131">省略このテスト構成を正式なテストケースとして保存する場合は、[**名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="021ca-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="021ca-132">[**ボイスルーティングテストケース情報の保存**] ダイアログボックスの [**名前**] フィールドに、テストケースの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="021ca-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="021ca-133">この名前は、エンタープライズ Voip 展開では、すべてのボイスルーティングテストケースの間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="021ca-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="021ca-134">長さは最長32文字で、バックスラッシュ (\\)、ピリオド (.)、またはアンダースコア (\_) に加えて、英数字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="021ca-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="021ca-135">[**ボイスルーティングテストケース情報の保存**] ダイアログボックスの残りのフィールドは読み取り専用であり、非公式なテスト構成*と*結果から事前に設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="021ca-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="021ca-136">これが、テストケースに対して保存する構成であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="021ca-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="021ca-137">テスト結果からの値は、[<STRONG>ボイスルーティングテストケース情報の保存</STRONG>] ダイアログボックスで、次のようにフィールドを事前に事前生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="021ca-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="021ca-138"><STRONG>期待される翻訳</STRONG>には、[正規化された<STRONG>数値</STRONG>] フィールドの値があらかじめ表示されています。</span><span class="sxs-lookup"><span data-stu-id="021ca-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="021ca-139"><STRONG>期待されるルート</STRONG>には、[<STRONG>第1ルート</STRONG>] フィールドの値があらかじめ記載されています。</span><span class="sxs-lookup"><span data-stu-id="021ca-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="021ca-140"><STRONG>期待される pstn 使用状況レコード</STRONG>には、<STRONG>最初の pstn 利用状況</STRONG>フィールドの値があらかじめ登録されています。</span><span class="sxs-lookup"><span data-stu-id="021ca-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="021ca-141">テストの実行時にこれらのいずれかの値との一致が見つからなかった場合、[<STRONG>ボイスルーティングテストケース情報の保存</STRONG>] ダイアログボックスで対応するフィールドが空になります。</span><span class="sxs-lookup"><span data-stu-id="021ca-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="021ca-142">[ **Ok]** をクリックしてテストケースを保存するか、[**キャンセル**] をクリックして [**音声ルーティングテストケース情報の表示**] ダイアログボックスに戻り、保存する前にさらにテストを作成します。</span><span class="sxs-lookup"><span data-stu-id="021ca-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="021ca-143">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="021ca-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="021ca-144">ボイスルーティングテストケースを作成するたびに、[<STRONG>すべてコミット</STRONG>] コマンドを実行してテストケースを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="021ca-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="021ca-145">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ca-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="021ca-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="021ca-146">See Also</span></span>


[<span data-ttu-id="021ca-147">Lync Server 2013 での音声ルーティング テスト ケースの作成</span><span class="sxs-lookup"><span data-stu-id="021ca-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="021ca-148">Lync Server 2013 でボイスルーティングテストケースを実行する</span><span class="sxs-lookup"><span data-stu-id="021ca-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="021ca-149">Lync Server 2013 での音声ルーティング テスト ケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="021ca-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="021ca-150">Lync Server 2013 音声ルーティング テスト ケースのインポート</span><span class="sxs-lookup"><span data-stu-id="021ca-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="021ca-151">Lync Server 2013 でのダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="021ca-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="021ca-152">Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="021ca-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

