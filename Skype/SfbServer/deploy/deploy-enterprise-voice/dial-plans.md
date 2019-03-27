---
title: 作成またはビジネス サーバーの Skype のダイヤル プランを変更します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: '概要: ビジネス サーバーのコントロール パネルの Skype を使用してダイヤル プランを変更または作成する方法を説明します。'
ms.openlocfilehash: b8f2e2831a611679f74aebcf49bcc24086adef7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895860"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a><span data-ttu-id="a0cf1-103">作成またはビジネス サーバーの Skype のダイヤル プランを変更します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-103">Create or modify a dial plan in Skype for Business Server</span></span>

<span data-ttu-id="a0cf1-104">**の概要:** ビジネス サーバーのコントロール パネルの Skype を使用してダイヤル プランを変更または作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>

### <a name="to-create-a-dial-plan"></a><span data-ttu-id="a0cf1-105">ダイヤル プランを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0cf1-105">To create a dial plan</span></span>

1. <span data-ttu-id="a0cf1-106">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-106">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a0cf1-107">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

3. <span data-ttu-id="a0cf1-108">[**ダイヤル プラン**] ページで、[**新規**] をクリックしてダイヤル プランのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>

   - <span data-ttu-id="a0cf1-109">[**サイト ダイヤル プラン**] は、ユーザー ダイヤル プランが割り当てられているユーザーおよびグループを除く、サイト全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="a0cf1-110">**サイト**のダイヤル プランのスコープを選択する場合は、**サイトの選択**] ダイアログ ボックスからサイトを選んでください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="a0cf1-111">サイトに対して既にダイヤル プランが作成されている場合、そのサイトは [**サイトの選択**] ダイアログ ボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="a0cf1-112">[**プール ダイヤル プラン**] は、公衆交換電話網 (PSTN) ゲートウェイまたはレジストラーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="a0cf1-113">ダイヤル プランのスコープの**プール**を選択する場合は、**サービスの選択**] ダイアログ ボックスから PSTN ゲートウェイまたはレジストラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="a0cf1-114">サービス (PSTN ゲートウェイまたはレジストラー) に対して既にダイヤル プランが作成されている場合、そのサービスは一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>

   - <span data-ttu-id="a0cf1-115">[**ユーザー ダイヤル プラン**] は、特定のユーザーまたはグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-115">**User dial plan** can be applied to specified users or groups.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a0cf1-116">ダイヤル プランのスコープを選択した後で、スコープを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-116">After you select the dial plan scope, it cannot be changed.</span></span>

4. <span data-ttu-id="a0cf1-p103">ユーザー ダイヤル プランを作成する場合、[**新しいダイヤル プラン**] ダイアログ ボックスの [**名前**] フィールドにわかりやすい名前を入力します。名前を保存した後で、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p103">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-119">サイト ダイヤル プランでは、 **[名前**] フィールドを選択し、サイト名があらかじめ設定されてプールに変更された .> のダイヤル プランにすることはできません、 **[名前**] フィールドは、PSTN ゲートウェイまたはレジストラーの名前が表示され、変更できません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

5. <span data-ttu-id="a0cf1-p104">[**簡単な名前**] フィールドには、[**名前**] フィールドに表示されたのと同じ名前が設定されます。必要に応じてこのフィールドを編集し、ダイヤル プランを適用するサイト、サービス、またはユーザーを説明する、よりわかりやすい名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p104">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a0cf1-122">[**簡単な名前**] は、展開内のすべてのダイヤル プランの中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="a0cf1-123">アルファベット順または数値文字は、それぞれの Unicode 文字に 256 を超えることはできない場合は、ハイフン (-)、ピリオド (.)、または、アンダー スコア (_) .> 文字は**サポートされていない**スペースや予約文字 RFC 3966 で定義されている (<http://www.ietf.org/rfc/rfc3966.txt>)。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>).</span></span> <span data-ttu-id="a0cf1-124">**簡易名**で**サポートされていません**が、予約済みの文字は、次: _gt「;」「/」"?"":""@""&amp;"「=」「+「\」、」</span><span class="sxs-lookup"><span data-stu-id="a0cf1-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

6. <span data-ttu-id="a0cf1-125">(オプション) [**説明**] フィールドに、追加する、ダイヤル プランに関するわかりやすい情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="a0cf1-p106">(オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-128">ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="a0cf1-p107">(オプション) ユーザーが外線に接続する際、先頭に 1 つまたは複数の数字 (9 など) を付けてダイヤルする必要がある場合のみ、[**外部アクセス プレフィックス**] フィールドに値を指定します。最大 4 文字のプレフィックス値を入力できます (#、\*、および 0 ～ 9)。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p107">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line. You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-131">外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="a0cf1-132">次の手順でダイヤル プランの正規化ルールを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-132">Associate and configure normalization rules for the dial plan as follows:</span></span>

    - <span data-ttu-id="a0cf1-133">エンタープライズ VoIP 展開で利用可能なすべての正規化ルールの一覧から 1 つまたは複数のルールを選択するのには [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a0cf1-134">[**正規化ルールの選択**] で、ダイヤル プランに関連付けるルールをハイライトしてから、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="a0cf1-135">新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="a0cf1-136">新しいルールを定義する方法についてを参照してください[を作成するまたはビジネス用の Skype の正規化ルールを変更する](normalization-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="a0cf1-137">既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="a0cf1-138">既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="a0cf1-139">ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a0cf1-140">ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="a0cf1-141">計画に必要なすべての正規化ルールをダイヤルを確認する方法については、計画ドキュメントの[送信音声の計画が Skype のビジネス サーバーでルーティング](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="a0cf1-142">ダイヤル プランの正規化ルールが正しい順序で配置されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="a0cf1-143">位置を変更するルールの一覧で、ルールの名前を強調表示しをクリックして上下矢印。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a0cf1-144">Skype ビジネス サーバーのでは、ダウン上から正規化ルールの一覧を走査し、ダイヤルした番号と一致する最初の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a0cf1-145">ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上になるように並び替えてください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="a0cf1-146">_gt 既定の**すべてを保持**正規化規則 ^(\d{11})$ には、任意の 11 桁の番号が一致します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="a0cf1-147">たとえば、1425 で始まる 11 桁の番号に一致する正規化ルールを追加する場合ことを確認**すべてを保持**されているより制限の厳しい下 ^(1425\d{7})$ のルールです。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="a0cf1-p113">(オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。テスト結果が [**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p113">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

12. <span data-ttu-id="a0cf1-150">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-150">Click **OK**.</span></span>

13. <span data-ttu-id="a0cf1-151">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-152">ダイヤル プランを作成したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a0cf1-153">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="a0cf1-154">ダイヤル プランを変更するには</span><span class="sxs-lookup"><span data-stu-id="a0cf1-154">To modify a dial plan</span></span>

1. <span data-ttu-id="a0cf1-p115">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p115">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="a0cf1-157">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a0cf1-158">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4. <span data-ttu-id="a0cf1-159">[**ダイヤル プラン**] ページで、ダイヤル プラン名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-p116">ダイヤル プランのスコープと名前は、ダイヤル プラン作成時に設定されています。これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p116">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

5. <span data-ttu-id="a0cf1-162">(オプション) [**ダイヤル プランの編集**] で [**簡単な名前**] フィールドを編集します。このフィールドには、ダイヤル プランを適用するサイト、サービス、またはユーザーを反映したよりわかりやすい名前を示す、[**名前**] フィールドの表示と同じ名前があらかじめ入力されています。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a0cf1-163">**簡易名**は、Lync Server 2013 展開内のすべてのダイヤル プランの間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a0cf1-164">ピリオド (.)、プラス記号 (+)、またはアンダー スコア (_)、アルファベット順または数値文字、ハイフン (-) は、それぞれの Unicode 文字に 256 を超えることはできません、.>**簡単な [名前**] フィールドにスペースは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>

6. <span data-ttu-id="a0cf1-165">(オプション) [**説明**] フィールドにダイヤル プランの説明情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="a0cf1-p118">(オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p118">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-168">ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="a0cf1-p119">(オプション) ユーザーが外線に接続する際、先頭に 1 つまたは複数の数字 (9 など) を付けてダイヤルする必要がある場合のみ、[**外部アクセス プレフィックス**] フィールドに値を指定します。最大 4 文字のプレフィックス値を入力できます (#、\*、および 0 ～ 9)。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p119">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9). You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-171">外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="a0cf1-172">ダイヤル プランの正規化ルールを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-172">Associate and configure normalization rules for the dial plan:</span></span>

   - <span data-ttu-id="a0cf1-173">エンタープライズ VoIP 展開で利用可能なすべての正規化ルールの一覧から 1 つまたは複数のルールを選択するのには [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a0cf1-174">[**正規化ルールの選択**] ダイアログ ボックスで、ダイヤル プランに関連付けるルールを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="a0cf1-175">新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="a0cf1-176">新しいルールを定義する方法についてを参照してください[を作成するまたはビジネス用の Skype の正規化ルールを変更する](normalization-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="a0cf1-177">既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="a0cf1-178">既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="a0cf1-179">ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a0cf1-180">ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="a0cf1-181">計画に必要なすべての正規化ルールをダイヤルを確認する方法の詳細については、計画ドキュメントの[送信音声の計画が Skype のビジネス サーバーでルーティング](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="a0cf1-182">ダイヤル プランの正規化ルールが正しい順序で配置されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="a0cf1-183">位置を変更するルールの一覧で、ルールの名前を強調表示しをクリックして上下矢印。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a0cf1-184">Skype ビジネス サーバーのでは、ダウン上から正規化ルールの一覧を走査し、ダイヤルした番号と一致する最初の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a0cf1-185">ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上になるように並び替えてください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="a0cf1-186">_gt 既定の**すべてを保持**正規化規則 ^(\d{11})$ には、任意の 11 桁の番号が一致します。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="a0cf1-187">たとえば、1425 で始まる 11 桁の番号に一致する正規化ルールを追加する場合は、**すべてを保持**されているより制限の厳しい下確認 ^(1425\d{7})$ のルールです。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="a0cf1-p125">(オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。テスト結果が [**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p125">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-p126">まだテストに成功していないダイヤル プランを保存して、後で再構成することができます。詳細については、「[Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-p126">You can save a dial plan that does not yet pass the test and then reconfigure it later. For details, see [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

12. <span data-ttu-id="a0cf1-192">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-192">Click **OK**.</span></span>

13. <span data-ttu-id="a0cf1-193">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf1-194">ダイヤル プランを作成または変更したときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a0cf1-195">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cf1-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0cf1-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0cf1-196">See also</span></span>

[<span data-ttu-id="a0cf1-197">発行保留中のビジネス用の Skype で音声ルーティング構成の変更</span><span class="sxs-lookup"><span data-stu-id="a0cf1-197">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

