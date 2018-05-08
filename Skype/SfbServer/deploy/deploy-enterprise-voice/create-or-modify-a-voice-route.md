---
title: Skype for Business 2015 でのボイス ルートの作成または変更
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '概要: ビジネス サーバー 2015 のビジネス サーバーのコントロール パネルの Skype を使用して、Skype でのボイス ルートを変更または作成する方法を説明します。'
ms.openlocfilehash: a999cf8ce068aeca217995bf9f8b0395beaa1d2b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business-2015"></a><span data-ttu-id="ae3b9-103">Skype for Business 2015 でのボイス ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="ae3b9-103">Create or modify a voice route in Skype for Business 2015</span></span>
 
<span data-ttu-id="ae3b9-104">**の概要:** ビジネス サーバー 2015 のビジネス サーバーのコントロール パネルの Skype を使用して、Skype でのボイス ルートを変更または作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-104">**Summary:** Learn how to create or modify a voice route in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="ae3b9-105">ビジネス サーバーのコントロール パネルの Skype を使用してボイス ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ae3b9-105">To create a voice route by using the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ae3b9-106">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ae3b9-107">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-107">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ae3b9-108">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-108">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="ae3b9-109">[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-109">Click **Route**.</span></span>
    
5. <span data-ttu-id="ae3b9-110">[**新規**] をクリックして、[**新規音声ルート**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-110">Click **New** to display the **New Voice Route** dialog box.</span></span>
    
6. <span data-ttu-id="ae3b9-111">[**名前**] に、音声ルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-111">In **Name**, type a descriptive name for the voice route.</span></span>
    
7. <span data-ttu-id="ae3b9-112">(オプション) [**説明**] に、音声ルートのわかりやすい追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-112">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>
    
8. <span data-ttu-id="ae3b9-113">このルートが対応するパターンを指定するには、**照合するパターンの作成**ツールを使用して正規表現を生成するか、手動で正規表現を記述します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-113">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="ae3b9-p101">**照合するパターンの作成**ツールを使用して正規表現を生成するには、次の値を入力します。次の 2 種類の照合パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-p101">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="ae3b9-116">**許可する番号の先頭の数字**: このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-116">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="ae3b9-117">たとえば、+425 と入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-117">For example, type +425, and then click **Add**.</span></span> <span data-ttu-id="ae3b9-118">このルートに含める各プレフィックス値について、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-118">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="ae3b9-119">**例外**: プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、[**例外**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-119">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="ae3b9-120">一致するパターンを 1 つまたは複数の値のタイプは*ない*場合がこれに対応するためにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-120">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="ae3b9-121">やなどのルートから +425237 で始まる番号を除外するには、[**例外**] フィールドで値の + 425237 を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-121">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ae3b9-122">照合パターンを手動で定義するには、**照合するパターンの作成**ツールの [**編集**] をクリックし、.NET Framework の正規表現を入力して、ルートが適用される相手電話番号の照合パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-122">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="ae3b9-123">正規表現を記述する方法の詳細については、 [「.NET Framework の正規表現」](https://go.microsoft.com/fwlink/p/?linkId=140927)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-123">For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
9. <span data-ttu-id="ae3b9-124">通話を発信する電話の ID を呼び出し先に表示しない場合は、[**発信者番号を表示しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-124">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="ae3b9-125">このオプションを選択すると、受信者の呼び出し元の ID の表示に表示される**代替の呼び出し元の ID**を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-125">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
10. <span data-ttu-id="ae3b9-126">1 つまたは複数のトランクを音声ルートに関連付けるには、[**追加**] をクリックして、一覧からトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-126">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
11. <span data-ttu-id="ae3b9-127">1 つまたは複数の公衆交換電話網 (PSTN) 使用法を音声ルートに関連付けるには、[**選択**] をクリックして、エンタープライズ VoIP 展開用に定義されている PSTN 使用法レコードの一覧からレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-127">To associate one or more Public Switched Telephone Network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae3b9-128">使用可能な PSTN 使用法レコードの各プロパティを表示するには、[ビジネス 2015年の Skype でのビューの PSTN 使用法レコード](view-pstn-usage-records.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-128">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business 2015](view-pstn-usage-records.md).</span></span> <span data-ttu-id="ae3b9-129">> を作成するか、PSTN 使用法レコードを編集を参照してください[を作成する音声ポリシーを変更してビジネス 2015年の Skype の PSTN 使用法レコードを構成する](voice-policy-and-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="ae3b9-129">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](voice-policy-and-pstn-usage-records.md)</span></span>
  
12. <span data-ttu-id="ae3b9-130">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-130">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="ae3b9-131">リスト内のレコードの位置を変更するには、レコード名を強調表示しをクリックして印または下矢印。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-131">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae3b9-132">PSTN 使用法レコードが表示される順序が重要な場合、ボイス ポリシーとは異なり、ボイス ルートでどの PSTN の使用法レコードが表示されている順序は、意味はありません。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-132">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="ae3b9-133">ただし、使用頻度によってリストを整理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-133">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="ae3b9-134">例: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-134">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="ae3b9-135">(Skype ビジネス サーバーのリストを走査、上から下です。)</span><span class="sxs-lookup"><span data-stu-id="ae3b9-135">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
13. <span data-ttu-id="ae3b9-p109">(オプション) "**テストする変換後の番号**" フィールドに値を入力して、[**実行**] をクリックします。テスト結果がフィールドの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-p109">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
14. <span data-ttu-id="ae3b9-138">[**OK**] をクリックして音声ルートを保存します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-138">Click **OK** to save the voice route.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae3b9-139">音声ルートを作成したときは毎回、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-139">Whenever you create a voice route, you must run the **Commit All** command to publish the configuration change.</span></span> <span data-ttu-id="ae3b9-140">詳細については、[発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-140">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md).</span></span> 
  
### <a name="to-modify-a-voice-route"></a><span data-ttu-id="ae3b9-141">音声ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="ae3b9-141">To modify a voice route</span></span>

1. <span data-ttu-id="ae3b9-142">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-142">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ae3b9-143">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-143">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>
    
3. <span data-ttu-id="ae3b9-144">[**ルート**] ページで、次のいずれかの方法を使用して音声ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-144">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
   - <span data-ttu-id="ae3b9-145">音声ルート名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-145">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="ae3b9-p111">音声ルート名をクリックし、[**編集**] をクリックし、[**コピー**] をクリックしてから、[**貼り付け**] をクリックします。直前に作成した音声ルートの新しいコピーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-p111">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>
    
4. <span data-ttu-id="ae3b9-148">[**音声ルートの編集**] ページの "**名前**" フィールドに、音声ルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-148">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>
    
5. <span data-ttu-id="ae3b9-149">(オプション) "**説明**" フィールドに、音声ルートのわかりやすい追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-149">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>
    
6. <span data-ttu-id="ae3b9-150">このルートが対応するパターンを指定するには、**照合するパターンの作成**ツールを使用して正規表現を生成するか、手動で正規表現を記述します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-150">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="ae3b9-p112">**照合するパターンの作成**ツールを使用して正規表現を生成するには、次の値を入力します。次の 2 種類の照合パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-p112">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="ae3b9-153">**許可する番号の先頭の数字**: このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-153">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="ae3b9-154">+425 を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-154">For example, type +425 and then click **Add**.</span></span> <span data-ttu-id="ae3b9-155">このルートに含める各プレフィックス値について、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-155">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="ae3b9-156">**例外**: プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、[**例外**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-156">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="ae3b9-157">一致するパターンを 1 つまたは複数の値のタイプは*ない*場合がこれに対応するためにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-157">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="ae3b9-158">やなどのルートから +425237 で始まる番号を除外するには、[**例外**] フィールドで値の + 425237 を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-158">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ae3b9-159">手動で一致するパターンを定義するに**一致させるパターンを構築**ツールの [**編集**] をクリックし、工順を適用する変換先の電話番号に一致するパターンを指定するのには、.NET Framework の正規表現を入力します。正規表現を記述する方法の詳細については、 [「.NET Framework の正規表現」](https://go.microsoft.com/fwlink/p/?linkId=140927)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-159">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
7. <span data-ttu-id="ae3b9-160">通話を発信する電話の ID を呼び出し先に表示しない場合は、[**発信者番号を表示しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-160">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="ae3b9-161">このオプションを選択すると、受信者の呼び出し元の ID の表示に表示される**代替の呼び出し元の ID**を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-161">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
8. <span data-ttu-id="ae3b9-162">1 つまたは複数の公衆交換電話網 (PSTN) トランクを音声ルートに関連付けるには、[**追加**] をクリックして、一覧からトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-162">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
9. <span data-ttu-id="ae3b9-163">ボイス ルートに関連付ける 1 つまたは複数の PSTN 使用法には、[**選択**] をクリックしてエンタープライズ VoIP を展開するために定義されている PSTN 使用法レコードの一覧からレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-163">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae3b9-164">使用可能な PSTN 使用法レコードの各プロパティを表示するには、[ビジネス 2015年の Skype でのビューの PSTN 使用法レコード](view-pstn-usage-records.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-164">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business 2015](view-pstn-usage-records.md).</span></span> <span data-ttu-id="ae3b9-165">> を作成するか、PSTN 使用法レコードを編集を参照してください[を作成する音声ポリシーを変更してビジネス 2015年の Skype の PSTN 使用法レコードを構成する](voice-policy-and-pstn-usage-records.md)です。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-165">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](voice-policy-and-pstn-usage-records.md).</span></span> 
  
10. <span data-ttu-id="ae3b9-166">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-166">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="ae3b9-167">リスト内のレコードの位置を変更するには、レコード名を強調表示しをクリックして印または下矢印。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-167">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae3b9-168">どの PSTN 使用法レコードが表示されている順序が重要となる音声ポリシーとは異なり、ボイス ルートには、PSTN 使用法レコードの順序は、意味はありません。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-168">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="ae3b9-169">ただし、たとえば使用頻度によってリストを整理することを推奨します。 RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-169">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="ae3b9-170">(Skype ビジネス サーバーのリストを走査、上から下です。)</span><span class="sxs-lookup"><span data-stu-id="ae3b9-170">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
11. <span data-ttu-id="ae3b9-p119">(オプション) "**テストする変換後の番号**" フィールドに値を入力して、[**実行**] をクリックします。テスト結果がフィールドの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-p119">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
12. <span data-ttu-id="ae3b9-173">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-173">Click **OK**.</span></span>
    
13. <span data-ttu-id="ae3b9-174">[**ルート**] ページの [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-174">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ae3b9-175">音声ルートを作成または変更するときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-175">Whenever you create or modify a voice route, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ae3b9-176">詳細については、操作マニュアルの[発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-176">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ae3b9-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae3b9-177">See also</span></span>

#### 

[<span data-ttu-id="ae3b9-178">ビジネス 2015年の Skype の PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="ae3b9-178">View PSTN usage records in Skype for Business 2015</span></span>](view-pstn-usage-records.md)
  
[<span data-ttu-id="ae3b9-179">作成し、音声ポリシーを変更またはビジネス 2015年の Skype の PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae3b9-179">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)
  
[<span data-ttu-id="ae3b9-180">発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更</span><span class="sxs-lookup"><span data-stu-id="ae3b9-180">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)

