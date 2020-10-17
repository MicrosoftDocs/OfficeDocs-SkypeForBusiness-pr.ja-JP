---
title: 'Lync Server 2013: 音声ルーティングテストケースの実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06c7119d8b011a805ffbc19c3b63f8832f302556
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511150"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="315dc-102">Lync Server 2013 での音声ルーティングテストケースの実行</span><span class="sxs-lookup"><span data-stu-id="315dc-102">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="315dc-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="315dc-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="315dc-104">音声ルーティングテストケーススイートですべてのテストケースを実行することも、1つ以上の選択したテストケースを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="315dc-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="315dc-105">すべての音声ルーティングテストケースを実行するには</span><span class="sxs-lookup"><span data-stu-id="315dc-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="315dc-106">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="315dc-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="315dc-107">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="315dc-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="315dc-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="315dc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="315dc-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="315dc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="315dc-110">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="315dc-111">[ **音声ルーティングのテスト** ] ページで、[ **アクション** ] をクリックし、[ **すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="315dc-112">各テストケースの成功または失敗の状態は、[ **成功/失敗** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="315dc-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="315dc-113">テストケースがまだ実行されていない場合は、[ **成功/失敗** ] 列に N/a が表示されます。</span><span class="sxs-lookup"><span data-stu-id="315dc-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="315dc-114">オプション各テストケースの詳細な結果を確認するには、テストケース名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="315dc-115">結果は、[ **テストケースの編集** ] ページの右側の影付き領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="315dc-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="315dc-116">**テスト結果:** テストケース実行の全体的な合格または失敗の状態。</span><span class="sxs-lookup"><span data-stu-id="315dc-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="315dc-117">**正規化ルール:** ダイヤル番号 ([ **テストする番号** ] フィールドの値) と一致する、このテストケースで選択されているダイヤルプランの最初の正規化ルール。</span><span class="sxs-lookup"><span data-stu-id="315dc-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="315dc-118">正規化された**数値:** 正規化ルールによって変換された後のダイヤル番号の値。</span><span class="sxs-lookup"><span data-stu-id="315dc-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="315dc-119">**最初の PSTN 使用法:** ダイヤル番号に一致する、このテストケースで選択した音声ポリシーに含まれる最初の公衆交換電話網 (PSTN) 使用法レコード。</span><span class="sxs-lookup"><span data-stu-id="315dc-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="315dc-120">**最初のルート:** ダイヤル番号に一致する最初の PSTN 使用法レコードの最初のボイスルート。</span><span class="sxs-lookup"><span data-stu-id="315dc-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="315dc-121">音声ルーティングテストケース構成では、予想される <STRONG>PSTN 使用法レコード</STRONG> および予想される <STRONG>ルート</STRONG> フィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="315dc-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="315dc-122">テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="315dc-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="315dc-123">選択した1つ以上の音声ルーティングテストケースを実行するには</span><span class="sxs-lookup"><span data-stu-id="315dc-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="315dc-124">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="315dc-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="315dc-125">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="315dc-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="315dc-126">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="315dc-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="315dc-127">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="315dc-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="315dc-128">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="315dc-129">[ **音声ルーティングのテスト** ] ページで、実行するテストケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="315dc-130">[ **アクション** ] メニューの [ **選択した**ものを実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="315dc-131">各テストケースの成功または失敗の状態は、[ **成功/失敗** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="315dc-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="315dc-132">テストケースがまだ実行されていない場合は、[ **成功/失敗** ] 列に N/a が表示されます。</span><span class="sxs-lookup"><span data-stu-id="315dc-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="315dc-133">オプション各テストケースの詳細な結果を確認するには、テストケース名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="315dc-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="315dc-134">結果は、[ **テストケースの編集** ] ページの右側の影付き領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="315dc-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="315dc-135">**テスト結果:** テストケース実行の全体的な合格または失敗の状態。</span><span class="sxs-lookup"><span data-stu-id="315dc-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="315dc-136">**正規化ルール:** ダイヤル番号 ([ **テストする番号** ] フィールドの値) と一致する、このテストケースで選択されているダイヤルプランの最初の正規化ルール。</span><span class="sxs-lookup"><span data-stu-id="315dc-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="315dc-137">正規化された**数値:** 正規化ルールによって変換された後のダイヤル番号の値。</span><span class="sxs-lookup"><span data-stu-id="315dc-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="315dc-138">**最初の PSTN 使用法:** ダイヤル番号と一致する、このテストケースで選択されている音声ポリシーの最初の PSTN 使用法レコード。</span><span class="sxs-lookup"><span data-stu-id="315dc-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="315dc-139">**最初のルート:** ダイヤル番号に一致する最初の PSTN 使用法レコードの最初のボイスルート。</span><span class="sxs-lookup"><span data-stu-id="315dc-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="315dc-140">音声ルーティングテストケース構成では、予想される <STRONG>PSTN 使用法レコード</STRONG> および予想される <STRONG>ルート</STRONG> フィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="315dc-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="315dc-141">テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="315dc-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="315dc-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="315dc-142">See Also</span></span>


[<span data-ttu-id="315dc-143">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="315dc-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="315dc-144">Lync Server 2013 での音声ルーティングテストの実行</span><span class="sxs-lookup"><span data-stu-id="315dc-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

