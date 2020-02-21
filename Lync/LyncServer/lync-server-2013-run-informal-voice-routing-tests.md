---
title: 'Lync Server 2013: 非公式の音声ルーティングテストの実行'
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
ms.openlocfilehash: ebd127948ec612be61254d97101c0dcd193eeeee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="6bb10-102">Lync Server 2013 での非公式の音声ルーティングテストの実行</span><span class="sxs-lookup"><span data-stu-id="6bb10-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bb10-103">_**トピックの最終更新日:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="6bb10-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="6bb10-p101">[**音声ルーティング テスト ケース情報の作成**] ダイアログ ボックスを使用して、実際のテスト ケースを作成する前に非公式のテストを実行できます。 テスト結果に問題がなければ、それを公式のテスト ケースとして保存するオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="6bb10-106">非公式の音声ルーティング テストを実行するには</span><span class="sxs-lookup"><span data-stu-id="6bb10-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="6bb10-107">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6bb10-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6bb10-108">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bb10-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6bb10-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6bb10-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bb10-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6bb10-111">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bb10-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="6bb10-112">[**音声ルーティングのテスト**] ページで、[**音声ルーティング テスト ケース情報の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bb10-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="6bb10-p104">[**ダイヤル番号**] フィールドに、このテストで使用する電話番号を入力します。 この番号は正規化され、[**結果**] ページの [**正規化番号**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="6bb10-p105">[**ダイヤル プラン**] リストから、ダイヤル番号のテストで使用するダイヤル プランを選択します。 既定値はグローバル ダイヤル プランです。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="6bb10-117">テストを実行すると、このダイヤル プランでダイヤル番号と一致する最初の正規化ルールが [**結果**] ウィンドウの [**正規化ルール**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="6bb10-p106">[**音声ポリシー**] リストから、ダイヤル番号のテストで使用する音声ポリシーを選択します。 既定値はグローバル音声ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="6bb10-p107">テストを実行すると、この音声ポリシーで最初に一致する PSTN 使用法レコードが [**結果**] ウィンドウの [**最初の PSTN 使用法**] フィールドに表示されます。 また、この PSTN 使用法レコードに関連付けられており、最初に一致するボイス ルートが、[**最初のルート**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="6bb10-122">(オプション) 特定のユーザーに割り当てられた音声ポリシーに対してダイヤル番号をテストする場合は、[**ユーザーから値を入力**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6bb10-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="6bb10-123">[**参照**] をクリックして [**エンタープライズ VoIP ユーザーの選択**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="6bb10-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="6bb10-124">[**検索**] をクリックして、エンタープライズ VoIP が有効なユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6bb10-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="6bb10-p108">このテストで使用する音声ポリシーが割り当てられているユーザーの名前をダブルクリックします。 これにより、選択したユーザーに割り当てられている音声ポリシーが [**ポリシー**] フィールドに入力されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="6bb10-p109">テストを実行すると、この音声ポリシーで最初に一致する PSTN 使用法レコードが [**結果**] ウィンドウの [**最初の PSTN 使用法**] フィールドに表示されます。また、この PSTN 使用法レコードに関連付けられており、最初に一致するボイス ルートが、[**最初のルート**] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="6bb10-p110">[**実行**] をクリックしてテスト ケースを実行します。 結果はダイアログ ボックスの右パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="6bb10-131">(オプション) このテスト構成を公式のテスト ケースとして保存する場合は、[**名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bb10-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="6bb10-132">[**音声ルーティング テスト ケース情報の保存**] ダイアログ ボックスの [**名前**] フィールドに、テスト ケースの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6bb10-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="6bb10-133">名前は、エンタープライズ VoIP 展開内のすべての音声ルーティング テスト ケースの中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bb10-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="6bb10-134">最大で32文字まで指定でき、円記号 (\\)、ピリオド (.)、またはアンダースコア (\_) に加えて、英数字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="6bb10-p112">[**音声ルーティング テスト ケース情報の保存**] ダイアログ ボックスにある残りのフィールドは読み取り専用です。値は、非公式のテスト構成*および*結果から事前に入力されます。 テスト ケースとして保存する構成で間違いないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6bb10-137">テスト結果の値は、次に示すように、[<STRONG>音声ルーティング テスト ケース情報の保存</STRONG>] ダイアログ ボックスのフィールドに値を事前入力するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="6bb10-138">[<STRONG>予期される変換値</STRONG>] には、[<STRONG>正規化番号</STRONG>] フィールドの値が事前入力されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="6bb10-139">[<STRONG>予期されるルート</STRONG>] には、[<STRONG>最初のルート</STRONG>] フィールドの値が事前入力されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="6bb10-140">[<STRONG>予期される PSTN 使用法レコード</STRONG>] には、[<STRONG>最初の PSTN 使用法</STRONG>] フィールドの値が事前入力されます。</span><span class="sxs-lookup"><span data-stu-id="6bb10-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="6bb10-p113">テストの実行中にこれらの値に一致する値が何も検出されなかった場合、[<STRONG>音声ルーティング テスト ケース情報の保存</STRONG>] ダイアログ ボックスの対応するフィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="6bb10-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="6bb10-142">[**OK**] をクリックしてテスト ケースを保存するか、[**キャンセル**] をクリックして [**音声ルーティング テスト ケース情報の表示**] ダイアログ ボックスに戻り、保存する前にテストをさらに構成します。</span><span class="sxs-lookup"><span data-stu-id="6bb10-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="6bb10-143">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bb10-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6bb10-144">音声ルーティング テスト ケースを作成するときにはいつでも、[<STRONG>すべて確定</STRONG>] コマンドを実行してテスト ケースを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bb10-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="6bb10-145">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bb10-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6bb10-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bb10-146">See Also</span></span>


[<span data-ttu-id="6bb10-147">Lync Server 2013 での音声ルーティングテストケースの作成</span><span class="sxs-lookup"><span data-stu-id="6bb10-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="6bb10-148">Lync Server 2013 での音声ルーティングテストケースの実行</span><span class="sxs-lookup"><span data-stu-id="6bb10-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="6bb10-149">Lync Server 2013 での音声ルーティングテストケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="6bb10-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="6bb10-150">Lync Server 2013 での音声ルーティングテストケースのインポート</span><span class="sxs-lookup"><span data-stu-id="6bb10-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="6bb10-151">Lync Server 2013 でのダイヤルプランの構成</span><span class="sxs-lookup"><span data-stu-id="6bb10-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="6bb10-152">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</span><span class="sxs-lookup"><span data-stu-id="6bb10-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

