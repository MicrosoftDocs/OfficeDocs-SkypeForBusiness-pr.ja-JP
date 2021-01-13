---
title: Skype for Business でボイス ルートを作成または変更する
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '概要: Skype for Business Server コントロール パネルを使用して、Skype for Business Server でボイス ルートを作成または変更する方法について学習します。'
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820457"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a><span data-ttu-id="acc15-103">Skype for Business でボイス ルートを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="acc15-103">Create or modify a voice route in Skype for Business</span></span>
 
<span data-ttu-id="acc15-104">**概要:** Skype for Business Server コントロール パネルを使用して、Skype for Business Server でボイス ルートを作成または変更する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="acc15-104">**Summary:** Learn how to create or modify a voice route in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="acc15-105">Skype for Business Server コントロール パネルを使用してボイス ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="acc15-105">To create a voice route by using the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="acc15-106">RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、\*\*\*\*または\*\*\*\*CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="acc15-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="acc15-107">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="acc15-107">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="acc15-108">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-108">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="acc15-109">[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-109">Click **Route**.</span></span>
    
5. <span data-ttu-id="acc15-110">[ **新規] を** クリックして [新 **しいボイス ルート] ダイアログ** ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="acc15-110">Click **New** to display the **New Voice Route** dialog box.</span></span>
    
6. <span data-ttu-id="acc15-111">[ **名前]** に、音声ルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="acc15-111">In **Name**, type a descriptive name for the voice route.</span></span>
    
7. <span data-ttu-id="acc15-112">(省略可能)[ **説明] に**、音声ルートに関するその他の説明情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="acc15-112">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>
    
8. <span data-ttu-id="acc15-113">このルートに対応するパターンを指定するには、[パターンの作成] ツールを使用して正規表現を生成するか、正規表現を手動で記述します。</span><span class="sxs-lookup"><span data-stu-id="acc15-113">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="acc15-p101">**一致パターン構築** ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc15-p101">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="acc15-116">**許可する番号の開始番号**: このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。</span><span class="sxs-lookup"><span data-stu-id="acc15-116">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="acc15-117">たとえば、「+425」と入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="acc15-117">For example, type +425, and then click **Add**.</span></span> <span data-ttu-id="acc15-118">このルートに含める各プレフィックス値について、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="acc15-118">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="acc15-119">**例外**: プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、**[例外]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-119">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="acc15-120">このルートに対応しない一致パターンの 1 つ以上の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="acc15-120">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="acc15-121">たとえば、+425237 で始まる番号をルートから除外するには、[例外] フィールドに値 +425237 を入力し **、[OK]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="acc15-121">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="acc15-122">一致パターンを手動で定義するには、**一致パターン構築** ツールの **[編集]** をクリックし、.NET Framework 正規表現を入力して、ルートが適用される相手電話番号の一致パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc15-122">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="acc15-123">正規表現を記述する方法の詳細については [、「".NET Framework Regular Expressions"」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="acc15-123">For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
9. <span data-ttu-id="acc15-124">通話を発信する電話の ID を呼び出し先に表示しない場合は、**[発信者 ID を表示しない]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc15-124">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="acc15-125">このオプションを選択する場合は、受信者の発信者 **番号** の表示に表示される代替発信者番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc15-125">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
10. <span data-ttu-id="acc15-126">1 つ以上のトランクをボイス ルートに関連付ける場合は、[追加] **をクリックし** 、一覧からトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="acc15-126">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
11. <span data-ttu-id="acc15-127">1 つ以上の公衆交換電話網 (PSTN) 使用法をボイス ルートに関連付ける場合は、[選択] をクリックして、エンタープライズ VoIP 展開用に定義されている PSTN 使用法レコードの一覧からレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="acc15-127">To associate one or more Public Switched Telephone Network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acc15-128">使用可能な各 PSTN 使用法レコードのプロパティを表示するには、「Skype for Business での PSTN 使用法 [レコードの表示」を参照してください](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="acc15-128">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="acc15-129">> PSTN 使用法レコードを作成または編集するには[、「Create or modify a voice policy and configure PSTN usage records in Skype for Business」を参照してください](voice-policy-and-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="acc15-129">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)</span></span>
  
12. <span data-ttu-id="acc15-130">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="acc15-130">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="acc15-131">リスト内でのレコードの位置を変更するには、レコード名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-131">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acc15-132">PSTN 使用法レコードの一覧の順序が重要である音声ポリシーとは対照的に、PSTN 使用法レコードがボイス ルートに表示される順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="acc15-132">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="acc15-133">ただし、使用頻度で一覧を整理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="acc15-133">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="acc15-134">例: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="acc15-134">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="acc15-135">(Skype for Business Server は一覧を上から下にスキャンします)。</span><span class="sxs-lookup"><span data-stu-id="acc15-135">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
13. <span data-ttu-id="acc15-p109">(オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc15-p109">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
14. <span data-ttu-id="acc15-138">**[OK] を** クリックしてボイス ルートを保存します。</span><span class="sxs-lookup"><span data-stu-id="acc15-138">Click **OK** to save the voice route.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="acc15-139">ボイス ルートを作成するたびに、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc15-139">Whenever you create a voice route, you must run the **Commit All** command to publish the configuration change.</span></span> <span data-ttu-id="acc15-140">詳細については [、「Publish pending changes to the voice routing configuration in Skype for Business 」を参照してください](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="acc15-140">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md).</span></span> 
  
### <a name="to-modify-a-voice-route"></a><span data-ttu-id="acc15-141">ボイス ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="acc15-141">To modify a voice route</span></span>

1. <span data-ttu-id="acc15-142">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="acc15-142">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="acc15-143">左側のナビゲーション バーで [**音声ルート**] をクリックし、[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-143">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>
    
3. <span data-ttu-id="acc15-144">**[ルート]** ページで、次のいずれかの方法を使用してボイス ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="acc15-144">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
   - <span data-ttu-id="acc15-145">ボイス ルート名をクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-145">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="acc15-p111">ボイス ルート名をクリックし、**[編集]** をクリックし、**[コピー]** をクリックしてから、**[貼り付け]** をクリックします。 直前に作成したボイス ルートの新しいコピーをクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-p111">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>
    
4. <span data-ttu-id="acc15-148">**[ボイス ルートの編集]** ページの **[名前]** フィールドに、ボイス ルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="acc15-148">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>
    
5. <span data-ttu-id="acc15-149">(オプション) **[説明]** フィールドに、ボイス ルートのわかりやすい追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="acc15-149">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>
    
6. <span data-ttu-id="acc15-150">このルートが対応するパターンを指定するには、**一致パターン構築** ツールを使用して正規表現を生成するか、手動で正規表現を記述します。</span><span class="sxs-lookup"><span data-stu-id="acc15-150">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="acc15-p112">**一致パターン構築** ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc15-p112">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="acc15-153">**許可する番号の開始番号**: このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。</span><span class="sxs-lookup"><span data-stu-id="acc15-153">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="acc15-154">たとえば、「+425」と入力して、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-154">For example, type +425 and then click **Add**.</span></span> <span data-ttu-id="acc15-155">このルートに含める各プレフィックス値について、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="acc15-155">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="acc15-156">**例外**: プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、**[例外]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-156">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="acc15-157">このルートに対応しない一致パターンの 1 つ以上の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="acc15-157">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="acc15-158">たとえば、+425237 で始まる番号をルートから除外するには、[例外] フィールドに値 +425237 を入力し **、[OK]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="acc15-158">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="acc15-159">一致パターンを手動で定義するには、[一致するパターンの作成] ツールで [編集] をクリックし、.NET Framework 正規表現を入力して、ルートが適用される宛先電話番号の照合パターンを指定します。正規表現を記述する方法の詳細については[、「".NET Framework Regular Expressions"」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="acc15-159">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
7. <span data-ttu-id="acc15-160">発信 **呼び出しを** 行っている電話の ID を呼び出し先に表示しない場合は、[発信者番号を表示しない] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc15-160">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="acc15-161">このオプションを選択する場合は、受信者の発信者 **番号** の表示に表示される代替発信者番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc15-161">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
8. <span data-ttu-id="acc15-162">1 つ以上の公衆交換電話網 (PSTN) トランクをボイス ルートに関連付ける場合は、[追加] をクリックし、一覧からトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="acc15-162">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
9. <span data-ttu-id="acc15-163">1 つ以上の PSTN 使用法をボイス ルートに関連付ける場合は、[選択] をクリックして、展開用に定義されている PSTN 使用法レコードの一覧からレコードエンタープライズ VoIPします。</span><span class="sxs-lookup"><span data-stu-id="acc15-163">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acc15-164">使用可能な各 PSTN 使用法レコードのプロパティを表示するには、「Skype for Business での PSTN 使用法 [レコードの表示」を参照してください](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="acc15-164">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="acc15-165">> PSTN 使用法レコードを作成または編集するには、「Create [or modify a voice policy and configure PSTN usage records in Skype for Business」を参照してください](voice-policy-and-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="acc15-165">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md).</span></span> 
  
10. <span data-ttu-id="acc15-166">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="acc15-166">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="acc15-167">リスト内でのレコードの位置を変更するには、レコード名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-167">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acc15-168">PSTN 使用法レコードの一覧の順序が重要な音声ポリシーとは対照的に、ボイス ルートでの PSTN 使用法レコードの順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="acc15-168">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="acc15-169">ただし、使用頻度で一覧を整理することをお勧めします。例: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="acc15-169">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="acc15-170">(Skype for Business Server は一覧を上から下にスキャンします)。</span><span class="sxs-lookup"><span data-stu-id="acc15-170">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
11. <span data-ttu-id="acc15-p119">(オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc15-p119">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
12. <span data-ttu-id="acc15-173">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-173">Click **OK**.</span></span>
    
13. <span data-ttu-id="acc15-174">**[ルート]** ページの **[確定]** をクリックして、**[すべて確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc15-174">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="acc15-175">ボイス ルートを作成または変更するたびに、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc15-175">Whenever you create or modify a voice route, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="acc15-176">詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc15-176">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="acc15-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="acc15-177">See also</span></span>

[<span data-ttu-id="acc15-178">Skype for Business での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="acc15-178">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
  
[<span data-ttu-id="acc15-179">音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="acc15-179">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
  
[<span data-ttu-id="acc15-180">Skype for Business での音声ルーティング構成に対する保留中の変更の公開</span><span class="sxs-lookup"><span data-stu-id="acc15-180">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

