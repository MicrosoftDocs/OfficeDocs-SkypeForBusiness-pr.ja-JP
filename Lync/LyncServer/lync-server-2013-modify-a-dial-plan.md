---
title: 'Lync Server 2013: ダイヤル プランの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4c007933eb7186e412ada1a3f4c35b241f5eff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="c0cf4-102">Lync Server 2013 でのダイヤル プランの変更</span><span class="sxs-lookup"><span data-stu-id="c0cf4-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0cf4-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c0cf4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c0cf4-104">既存のダイヤルプランを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="c0cf4-105">新しいダイヤルプランを作成する場合は、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="c0cf4-106">ダイヤル プランを変更するには</span><span class="sxs-lookup"><span data-stu-id="c0cf4-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="c0cf4-107">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c0cf4-108">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c0cf4-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c0cf4-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c0cf4-111">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="c0cf4-112">[**ダイヤル プラン**] ページで、ダイヤル プラン名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0cf4-p104">ダイヤル プランのスコープと名前は、ダイヤル プラン作成時に設定されています。これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="c0cf4-115">(オプション) [**ダイヤル プランの編集**] で [**簡単な名前**] フィールドを編集します。このフィールドには、ダイヤル プランを適用するサイト、サービス、またはユーザーを反映したよりわかりやすい名前を示す、[**名前**] フィールドの表示と同じ名前があらかじめ入力されています。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0cf4-116"><STRONG>簡易名</STRONG>は、Lync Server 2013 展開内のすべてのダイヤルプランの間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="c0cf4-117">英字、数字、ハイフン (-)、ピリオド (.)、正符号 (+)、またはアンダースコア (_) の Unicode 文字を 256 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="c0cf4-118">スペースは [<STRONG>簡単な名前</STRONG>] フィールドでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="c0cf4-119">(オプション) [**説明**] フィールドにダイヤル プランの説明情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="c0cf4-p106">(オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0cf4-122">ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="c0cf4-123">(オプション) ユーザーが外線に接続する際、先頭に 1 つまたは複数の数字 (9 など) を付けてダイヤルする必要がある場合のみ、[**外部アクセス プレフィックス**] フィールドに値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="c0cf4-124">最大4文字のプレフィックス値 ( \# \*、、、および 0-9) を入力できます。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0cf4-125">外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="c0cf4-126">ダイヤル プランの正規化ルールを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="c0cf4-127">エンタープライズ Voip 展開で利用できるすべての正規化ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="c0cf4-128">[**正規化ルールの選択**] ダイアログ ボックスで、ダイヤル プランに関連付けるルールを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="c0cf4-129">新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="c0cf4-130">新しいルールの定義の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="c0cf4-131">既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="c0cf4-132">ルールの編集の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="c0cf4-133">既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="c0cf4-134">コピーの編集の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="c0cf4-135">ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0cf4-136">ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="c0cf4-137">ダイヤルプランで必要なすべての正規化ルールを決定する方法の詳細については、計画ドキュメントの「 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 でのダイヤルプランと正規化ルール</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="c0cf4-p113">ダイヤル プランの正規化ルールが、正しい順序で並んでいることを確認します。一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0cf4-140">Lync Server は、[正規化ルール] リストを上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="c0cf4-141">ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上になるように並び替えてください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="c0cf4-142">既定では、<STRONG>すべて</STRONG>の正規化ルール<STRONG>^{11}(\d) $</STRONG>は11桁の数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="c0cf4-143">たとえば、1425で始まる11桁の数字と一致する正規化ルールを追加する場合は、[<STRONG>すべて保持</STRONG>] が、より制限された<STRONG>^ (1425 \{7}d) $</STRONG>ルールの下に並べ替えられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="c0cf4-p116">(オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。テスト結果が [**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0cf4-146">まだテストに成功していないダイヤル プランを保存して、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="c0cf4-147">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="c0cf4-148">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-148">Click **OK**.</span></span>

13. <span data-ttu-id="c0cf4-149">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0cf4-150">ダイヤル プランを作成または変更したときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c0cf4-151">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0cf4-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0cf4-152">See Also</span></span>


[<span data-ttu-id="c0cf4-153">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="c0cf4-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="c0cf4-154">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="c0cf4-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="c0cf4-155">Lync Server 2013 の正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="c0cf4-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

