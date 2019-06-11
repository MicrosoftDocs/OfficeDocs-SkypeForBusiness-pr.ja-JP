---
title: 'Lync Server 2013: 音声ルーティングテストケースを実行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="1b246-102">Lync Server 2013 でボイスルーティングテストケースを実行する</span><span class="sxs-lookup"><span data-stu-id="1b246-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b246-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="1b246-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="1b246-104">ボイスルーティングテストケーススイートですべてのテストケースを実行するか、1つ以上の選択されたテストケースを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1b246-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="1b246-105">すべての音声ルーティングテストケースを実行するには</span><span class="sxs-lookup"><span data-stu-id="1b246-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="1b246-106">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1b246-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1b246-107">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b246-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1b246-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b246-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b246-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b246-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b246-110">左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="1b246-111">[**ボイスルーティングのテスト**] ページで、[**アクション**] をクリックし、[**すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="1b246-112">各テストケースの合格状態または失敗状態は、 **pass/fail**列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b246-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="1b246-113">テストケースがまだ実行されていない場合は、**合格/失敗**列に該当する N/a が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b246-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="1b246-114">省略各テストケースの詳細な結果を確認するには、テストケースの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="1b246-115">結果は、[**テストケースの編集**] ページの右側の影付きの領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b246-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="1b246-116">**テスト結果:** テストケース実行の全体の合否または失敗の状態。</span><span class="sxs-lookup"><span data-stu-id="1b246-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="1b246-117">**正規化ルール:** ダイヤルされた番号 ([指定した**番号**] フィールドの値) と一致する、このテストケースに対して選択したダイヤルプランの最初の正規化ルール。</span><span class="sxs-lookup"><span data-stu-id="1b246-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="1b246-118">正規化された**数値:** 正規化ルールによって翻訳されたダイヤルされた番号の値。</span><span class="sxs-lookup"><span data-stu-id="1b246-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="1b246-119">**第1の PSTN 使用量:** ダイヤルされた番号に一致する、このテストケースで選択された音声ポリシーの最初の公衆交換電話網 (PSTN) 使用状況レコード。</span><span class="sxs-lookup"><span data-stu-id="1b246-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="1b246-120">**第1のルート:** ダイヤルされた番号に一致する最初の PSTN 利用状況レコードの最初のボイスルート。</span><span class="sxs-lookup"><span data-stu-id="1b246-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1b246-121">ボイスルーティングテストケース構成では、予期される<STRONG>PSTN 使用状況レコード</STRONG>と予期される<STRONG>ルート</STRONG>フィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1b246-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="1b246-122">テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="1b246-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="1b246-123">選択した1つ以上のボイスルーティングテストケースを実行するには</span><span class="sxs-lookup"><span data-stu-id="1b246-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="1b246-124">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1b246-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1b246-125">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b246-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1b246-126">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b246-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b246-127">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b246-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b246-128">左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="1b246-129">[**ボイスルーティングのテスト**] ページで、実行するテストケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="1b246-130">[**操作**] メニューの [**選択**して実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="1b246-131">各テストケースの合格状態または失敗状態は、 **pass/fail**列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b246-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="1b246-132">テストケースがまだ実行されていない場合は、**合格/失敗**列に該当する N/a が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b246-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="1b246-133">省略各テストケースの詳細な結果を確認するには、テストケースの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b246-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="1b246-134">結果は、[**テストケースの編集**] ページの右側の影付きの領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b246-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="1b246-135">**テスト結果:** テストケース実行の全体の合否または失敗の状態。</span><span class="sxs-lookup"><span data-stu-id="1b246-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="1b246-136">**正規化ルール:** ダイヤルされた番号 ([指定した**番号**] フィールドの値) と一致する、このテストケースに対して選択したダイヤルプランの最初の正規化ルール。</span><span class="sxs-lookup"><span data-stu-id="1b246-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="1b246-137">正規化された**数値:** 正規化ルールによって翻訳されたダイヤルされた番号の値。</span><span class="sxs-lookup"><span data-stu-id="1b246-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="1b246-138">**第1の PSTN 使用量:** このテストケースで、ダイヤルされた番号と一致するボイスポリシーの最初の PSTN 使用状況レコード。</span><span class="sxs-lookup"><span data-stu-id="1b246-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="1b246-139">**第1のルート:** ダイヤルされた番号に一致する最初の PSTN 利用状況レコードの最初のボイスルート。</span><span class="sxs-lookup"><span data-stu-id="1b246-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1b246-140">ボイスルーティングテストケース構成では、予期される<STRONG>PSTN 使用状況レコード</STRONG>と予期される<STRONG>ルート</STRONG>フィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1b246-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="1b246-141">テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="1b246-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b246-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b246-142">See Also</span></span>


[<span data-ttu-id="1b246-143">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="1b246-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="1b246-144">Lync Server 2013 での音声ルーティング テストの実行</span><span class="sxs-lookup"><span data-stu-id="1b246-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

