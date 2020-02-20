---
title: 'Lync Server 2013: ダイヤルプランを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3166352556925034d6b947600af99a10570b6933
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="bd544-102">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="bd544-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd544-103">_**トピックの最終更新日:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="bd544-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="bd544-104">新しいダイヤルプランを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd544-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="bd544-105">ダイヤルプランを編集する場合は、「 [Modify a dial plan In Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="bd544-106">ダイヤルプランを作成するには</span><span class="sxs-lookup"><span data-stu-id="bd544-106">To create a dial plan</span></span>

1.  <span data-ttu-id="bd544-107">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bd544-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bd544-108">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bd544-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd544-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bd544-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bd544-111">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="bd544-112">[**ダイヤルプラン**] ページで、[**新規**] をクリックし、ダイヤルプランのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd544-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="bd544-113">**サイトダイヤルプラン**は、ユーザーダイヤルプランに割り当てられているユーザーまたはグループを除く、サイト全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd544-113">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="bd544-114">ダイヤルプランのスコープとして**サイト**を選択する場合は、[サイトの**選択**] ダイアログボックスからサイトを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd544-114">If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="bd544-115">サイトに対して既にダイヤルプランが作成されている場合、そのサイトは **[サイトの選択**] ダイアログボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="bd544-115">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="bd544-116">**プールダイヤルプラン**は、公衆交換電話網 (PSTN) ゲートウェイまたはレジストラーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd544-116">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="bd544-117">ダイヤルプランのスコープに [**プール**] を選択する場合は、[**サービスの選択**] ダイアログボックスから PSTN ゲートウェイまたはレジストラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd544-117">If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="bd544-118">サービス (PSTN ゲートウェイまたはレジストラー) に対して既にダイヤルプランが作成されている場合、そのサービスは一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="bd544-118">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="bd544-119">**ユーザーダイヤルプラン**は、指定したユーザーまたはグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd544-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-120">ダイヤルプランのスコープを選択した後に、そのスコープを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd544-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="bd544-121">ユーザーダイヤルプランを作成している場合は、[**新しいダイヤルプラン**] ダイアログボックスの [**名前**] フィールドにわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd544-121">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="bd544-122">この名前は、保存後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd544-122">After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-123">サイトダイヤルプランの場合、[<STRONG>名前</STRONG>] フィールドにサイト名が事前に設定されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd544-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="bd544-124">プールダイヤルプランの場合、[<STRONG>名前</STRONG>] フィールドに PSTN ゲートウェイまたはレジストラー名が事前に設定されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd544-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="bd544-125">[**簡易名**] フィールドには、[**名前**] フィールドに表示されているものと同じ名前が設定されています。</span><span class="sxs-lookup"><span data-stu-id="bd544-125">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="bd544-126">必要に応じてこのフィールドを編集して、ダイヤルプランを適用するサイト、サービス、またはユーザーを表す、よりわかりやすい名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd544-126">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd544-127">この<STRONG>簡易名</STRONG>は、Lync Server 展開内のすべてのダイヤルプランの中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd544-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="bd544-128">各文字は、アルファベットまたは数字、ハイフン (-)、ピリオド (.)、またはアンダースコア (_) の256の Unicode 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="bd544-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="bd544-129">サポートされて<STRONG>いない</STRONG>文字には、RFC 3966 で定義http://www.ietf.org/rfc/rfc3966.txt)されているように、スペースや予約文字があります。</span><span class="sxs-lookup"><span data-stu-id="bd544-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="bd544-130"><STRONG>簡易名</STRONG>でサポートされ<STRONG>ていない</STRONG>予約文字には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="bd544-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="bd544-131">";""/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="bd544-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="bd544-132">オプション[**説明**] フィールドには、ダイヤルプランに関する補足的な情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="bd544-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="bd544-p110">(オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。 このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="bd544-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-135">ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</span><span class="sxs-lookup"><span data-stu-id="bd544-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="bd544-136">オプション[**外部アクセスプレフィックス**] フィールドに、外部行を取得するためにユーザーが1つまたは複数の追加の番号 (たとえば 9) をダイヤルする必要がある場合にのみ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd544-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="bd544-137">最大4文字のプレフィックス値 (\#、 \*、および 0-9) を入力できます。</span><span class="sxs-lookup"><span data-stu-id="bd544-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-138">外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bd544-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="bd544-139">次のように、ダイヤルプランの正規化ルールを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="bd544-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="bd544-140">エンタープライズ Voip 展開で使用可能なすべての正規化ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bd544-141">[**正規化ルールの選択**] で、ダイヤルプランに関連付けるルールを選択状態にして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="bd544-142">新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="bd544-143">新しいルールの定義の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="bd544-144">既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="bd544-145">ルールの編集の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="bd544-146">既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="bd544-147">コピーの編集の詳細については、「 [Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="bd544-148">ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-149">ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="bd544-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="bd544-150">ダイヤルプランに必要な正規化ルールすべてを決定する方法については、「計画」のドキュメントの「<A href="lync-server-2013-dial-plans-and-normalization-rules.md">ダイヤルプランと正規化ルール (Lync Server 2013</A> )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="bd544-p117">ダイヤル プランの正規化ルールが、正しい順序で並んでいることを確認します。 一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd544-153">Lync Server は、正規化ルールの一覧を上から順にトラバースし、ダイヤル番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd544-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="bd544-154">ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上に並び替えてください。</span><span class="sxs-lookup"><span data-stu-id="bd544-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="bd544-155">既定の [<STRONG>すべて保持</STRONG>] 正規化ルール<STRONG>^{11}(\d) $</STRONG>は、11桁の数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="bd544-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="bd544-156">たとえば、1425で始まる11桁の番号と一致する正規化ルールを追加する場合は、[<STRONG>すべて保持</STRONG>] がより制限の厳しい<STRONG>^ ({7}1425) $</STRONG>ルールの下になるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bd544-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="bd544-p120">(オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd544-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-159">まだテストに成功していないダイヤル プランを保存して、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bd544-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="bd544-160">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="bd544-161">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-161">Click **OK**.</span></span>

14. <span data-ttu-id="bd544-162">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd544-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd544-163">ダイヤルプランを作成するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd544-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="bd544-164">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd544-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd544-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd544-165">See Also</span></span>


[<span data-ttu-id="bd544-166">Lync Server 2013 でダイヤルプランを変更する</span><span class="sxs-lookup"><span data-stu-id="bd544-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="bd544-167">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="bd544-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="bd544-168">Lync Server 2013 での正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="bd544-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

