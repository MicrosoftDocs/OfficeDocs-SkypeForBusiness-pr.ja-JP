---
title: Skype for Business Server でダイヤル プランを作成または変更する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: '概要: Skype for Business Server コントロール パネルを使用してダイヤル プランを作成または変更する方法について学習します。'
ms.openlocfilehash: 718d0733aa5fabc072991708d09983ce8cb4267d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104903"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a><span data-ttu-id="ac277-103">Skype for Business Server でダイヤル プランを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="ac277-103">Create or modify a dial plan in Skype for Business Server</span></span>

<span data-ttu-id="ac277-104">**概要:** Skype for Business Server コントロール パネルを使用してダイヤル プランを作成または変更する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="ac277-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>

### <a name="to-create-a-dial-plan"></a><span data-ttu-id="ac277-105">ダイヤル プランを作成するには</span><span class="sxs-lookup"><span data-stu-id="ac277-105">To create a dial plan</span></span>

1. <span data-ttu-id="ac277-106">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac277-106">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ac277-107">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

3. <span data-ttu-id="ac277-108">[ダイヤル **プラン] ページで** 、[ **新規]** をクリックし、ダイヤル プランのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac277-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>

   - <span data-ttu-id="ac277-109">**サイト ダイヤル プランは** 、ユーザー ダイヤル プランに割り当てられているユーザーまたはグループを除き、サイト全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac277-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="ac277-110">ダイヤル プランのスコープ **として [サイト** ] を選択した場合は、[サイトの選択] ダイアログ ボックスから **サイトを選択する** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac277-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="ac277-111">サイトのダイヤル プランが既に作成されている場合、サイトは [サイトの選択 **] ダイアログ** ボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac277-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="ac277-112">**プール ダイヤル プランは** 、公衆交換電話網 (PSTN) ゲートウェイまたはレジストラーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ac277-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="ac277-113">ダイヤル プランの **スコープで [** プール] を選択した場合は、[サービスの選択] ダイアログ ボックスから PSTN ゲートウェイまたはレジストラー **を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="ac277-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="ac277-114">サービス (PSTN ゲートウェイまたはレジストラー) のダイヤル プランが既に作成されている場合、サービスは一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac277-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>

   - <span data-ttu-id="ac277-115">**ユーザー ダイヤル プランは** 、指定したユーザーまたはグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ac277-115">**User dial plan** can be applied to specified users or groups.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ac277-116">ダイヤル プランのスコープを選択した後は、変更できません。</span><span class="sxs-lookup"><span data-stu-id="ac277-116">After you select the dial plan scope, it cannot be changed.</span></span>

4. <span data-ttu-id="ac277-117">ユーザー ダイヤル プランを作成する場合は、[新しいダイヤル プラン] ダイアログ ボックスの **[名前** ] フィールドにわかりやすい名前 **を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="ac277-117">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="ac277-118">この名前を保存した後は、変更できません。</span><span class="sxs-lookup"><span data-stu-id="ac277-118">After this name is saved, it cannot be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-119">サイト ダイヤル プランの場合、[名前] フィールドにはサイト名が事前設定され、変更できません。> プール ダイヤル プランの場合、Name フィールドには PSTN ゲートウェイまたはレジストラー名が事前設定され、変更できません。</span><span class="sxs-lookup"><span data-stu-id="ac277-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

5. <span data-ttu-id="ac277-120">[ **簡易名]** フィールドには、[名前] フィールドに表示される名前と同じ名前が **事前に入力** されます。</span><span class="sxs-lookup"><span data-stu-id="ac277-120">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="ac277-121">必要に応じて、このフィールドを編集して、ダイヤル プランが適用されるサイト、サービス、またはユーザーを反映するわかりやすい名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac277-121">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ac277-122">簡易 **名は、** 展開内のすべてのダイヤル プランで一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac277-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="ac277-123">Unicode 文字は 256 文字を超えることはできません。これらの文字には、アルファベット文字または数字文字、ハイフン (-)、ピリオド (.)、またはサポートされていないアンダースコア (_).> 文字を指定できます。RFC 3966 ( ) で定義されているスペースと予約文字が含まれます。 <http://www.ietf.org/rfc/rfc3966.txt></span><span class="sxs-lookup"><span data-stu-id="ac277-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>).</span></span> <span data-ttu-id="ac277-124">簡易名でサポート **されていない** 予約文字には、次の ";" >含まれます。"/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="ac277-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

6. <span data-ttu-id="ac277-125">(省略可能)[説明 **] フィールド** に、ダイヤル プランに関するその他の説明情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="ac277-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="ac277-p106">(オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。 このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="ac277-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-128">ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</span><span class="sxs-lookup"><span data-stu-id="ac277-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="ac277-129">(省略可能)[外部アクセス **プレフィックス** ] フィールドで、ユーザーが外部行を取得するために 1 つ以上の先頭の数字 (たとえば、9) をダイヤルする必要がある場合にのみ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac277-129">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="ac277-130">最大 4 文字 (#、\*、0-9) のプレフィックス値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="ac277-130">You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-131">外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac277-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="ac277-132">ダイヤル プランの正規化ルールを次のように関連付け、構成します。</span><span class="sxs-lookup"><span data-stu-id="ac277-132">Associate and configure normalization rules for the dial plan as follows:</span></span>

    - <span data-ttu-id="ac277-133">展開で使用可能なすべての正規化ルールの一覧から 1 つ以上のルールを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ac277-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ac277-134">[ **正規化ルールの選択**] で、ダイヤル プランに関連付けるルールを強調表示し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac277-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="ac277-135">新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="ac277-136">新しいルールの定義の詳細については、「Skype for Business で正規化ルールを作成または [変更する」を参照してください](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ac277-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="ac277-137">既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="ac277-138">既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="ac277-139">ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ac277-140">ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac277-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="ac277-141">ダイヤル プランで必要なすべての正規化ルールを決定する方法については、「Planning」のドキュメントの [「Plan for outbound voice routing in Skype for Business Server」](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac277-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="ac277-142">ダイヤル プランの正規化ルールが正しい順序で配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac277-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="ac277-143">リスト内のルールの位置を変更するには、ルール名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac277-144">Skype for Business Server は、正規化ルールの一覧を上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac277-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="ac277-145">ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上に並び替えてください。</span><span class="sxs-lookup"><span data-stu-id="ac277-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="ac277-146">> 既定の **Keep All 正規化** ルール^(\d )$ は、任意の 11 桁の {11} 数値と一致します。</span><span class="sxs-lookup"><span data-stu-id="ac277-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="ac277-147">たとえば、1425 で始まる 11 桁の数字に一致する正規化ルールを追加する場合は、より制限の厳しい ^(1425\d )$ ルールの下に Keep **All** が並べ替えされます。 {7}</span><span class="sxs-lookup"><span data-stu-id="ac277-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="ac277-p113">(オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac277-p113">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

12. <span data-ttu-id="ac277-150">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-150">Click **OK**.</span></span>

13. <span data-ttu-id="ac277-151">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-152">ダイヤル プランを作成する場合は、すべてのコミット コマンドを実行 **して構成変更** を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac277-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ac277-153">詳細については、「操作」の [ドキュメントの「Skype for Business](voice-route-config-changes.md) の音声ルーティング構成に保留中の変更を公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac277-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="ac277-154">ダイヤル プランを変更するには</span><span class="sxs-lookup"><span data-stu-id="ac277-154">To modify a dial plan</span></span>

1. <span data-ttu-id="ac277-p115">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac277-p115">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="ac277-157">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac277-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ac277-158">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4. <span data-ttu-id="ac277-159">[**ダイヤル プラン**] ページで、ダイヤル プラン名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-p116">ダイヤル プランのスコープと名前は、ダイヤル プラン作成時に設定されています。 これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="ac277-p116">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

5. <span data-ttu-id="ac277-162">(オプション) [**ダイヤル プランの編集**] で [**簡単な名前**] フィールドを編集します。このフィールドには、ダイヤル プランを適用するサイト、サービス、またはユーザーを反映したよりわかりやすい名前を示す、[**名前**] フィールドの表示と同じ名前があらかじめ入力されています。</span><span class="sxs-lookup"><span data-stu-id="ac277-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac277-163">簡易 **名は、Lync** Server 2013 展開内のすべてのダイヤル プランで一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac277-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="ac277-164">Unicode 文字は 256 文字を超えることはできません。それぞれの文字は、アルファベット文字または数字文字、ハイフン (-)、ピリオド (.)、プラス記号 (+)、またはアンダースコア (_).>スペースを [簡易名] フィールドに使用できません。</span><span class="sxs-lookup"><span data-stu-id="ac277-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>

6. <span data-ttu-id="ac277-165">(オプション) [**説明**] フィールドにダイヤル プランの説明情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac277-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="ac277-p118">(オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。 このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="ac277-p118">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-168">ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</span><span class="sxs-lookup"><span data-stu-id="ac277-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="ac277-p119">(オプション) ユーザーが外線に接続する際、先頭に 1 つまたは複数の数字 (9 など) を付けてダイヤルする必要がある場合のみ、[**外部アクセス プレフィックス**] フィールドに値を指定します。 最大 4 文字のプレフィックス値を入力できます (#、\*、および 0 ～ 9)。</span><span class="sxs-lookup"><span data-stu-id="ac277-p119">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9). You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-171">外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac277-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="ac277-172">ダイヤル プランの正規化ルールを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="ac277-172">Associate and configure normalization rules for the dial plan:</span></span>

   - <span data-ttu-id="ac277-173">展開で使用可能なすべての正規化ルールの一覧から 1 つ以上のルールを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ac277-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ac277-174">[**正規化ルールの選択**] ダイアログ ボックスで、ダイヤル プランに関連付けるルールを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="ac277-175">新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="ac277-176">新しいルールの定義の詳細については、「Skype for Business で正規化ルールを作成または [変更する」を参照してください](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ac277-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="ac277-177">既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="ac277-178">既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="ac277-179">ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ac277-180">ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac277-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="ac277-181">ダイヤル プランで必要なすべての正規化ルールを決定する方法の詳細については、「Planning」のドキュメントの [「Plan for outbound voice routing in Skype for Business Server」](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac277-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="ac277-182">ダイヤル プランの正規化ルールが正しい順序で配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac277-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="ac277-183">リスト内のルールの位置を変更するには、ルール名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac277-184">Skype for Business Server は、正規化ルールの一覧を上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac277-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="ac277-185">ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上に並び替えてください。</span><span class="sxs-lookup"><span data-stu-id="ac277-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="ac277-186">> 既定の **Keep All 正規化** ルール^(\d )$ は、任意の 11 桁の {11} 数値と一致します。</span><span class="sxs-lookup"><span data-stu-id="ac277-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="ac277-187">たとえば、1425 で始まる 11 桁の数字に一致する正規化ルールを追加する場合は、キープ All が制限の厳しい^(1425\d )$ ルールの下に並べ替えされます。 {7}</span><span class="sxs-lookup"><span data-stu-id="ac277-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="ac277-p125">(オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac277-p125">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-190">まだテストに成功していないダイヤル プランを保存して、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac277-190">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ac277-191">詳細については、「[Testing Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac277-191">For details, see [Testing Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).</span></span>

12. <span data-ttu-id="ac277-192">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-192">Click **OK**.</span></span>

13. <span data-ttu-id="ac277-193">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac277-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac277-194">ダイヤル プランを作成または変更したときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac277-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ac277-195">詳細については、「操作」の [ドキュメントの「Skype for Business](voice-route-config-changes.md) の音声ルーティング構成に保留中の変更を公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac277-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac277-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac277-196">See also</span></span>

[<span data-ttu-id="ac277-197">Skype for Business の音声ルーティング構成に対する保留中の変更を公開する</span><span class="sxs-lookup"><span data-stu-id="ac277-197">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)