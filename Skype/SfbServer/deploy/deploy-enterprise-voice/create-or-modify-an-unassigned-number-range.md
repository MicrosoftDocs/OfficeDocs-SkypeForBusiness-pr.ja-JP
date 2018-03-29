---
title: Skype for Business Server 2015 での割り当てられていない番号範囲の作成または変更
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 作成、変更またはビジネス サーバーのエンタープライズ VoIP は、Skype で知らせアプリケーションの割り当てられていない数値の範囲を削除します。 この設定によって、割り当てられていない番号への通話を処理する方法が影響を受けます。
ms.openlocfilehash: e4a62072eeffd1cfe8d1cb81fceeb4e52cc68199
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server-2015"></a><span data-ttu-id="8879d-104">Skype for Business Server 2015 での割り当てられていない番号範囲の作成または変更</span><span class="sxs-lookup"><span data-stu-id="8879d-104">Create or modify an unassigned number range in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8879d-105">作成、変更またはビジネス サーバーのエンタープライズ VoIP は、Skype で知らせアプリケーションの割り当てられていない数値の範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="8879d-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="8879d-106">この設定によって、割り当てられていない番号への通話を処理する方法が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="8879d-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="8879d-107">ビジネス サーバー用の Skype を使用すると、組織にとって有効ですが、ユーザーや電話に割り当てられていない電話番号への着信呼び出しに対する処理と言います。</span><span class="sxs-lookup"><span data-stu-id="8879d-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="8879d-108">そのような通話の処理を構成するには、割り当てられていない番号の表を設定します。</span><span class="sxs-lookup"><span data-stu-id="8879d-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="8879d-109">お知らせアプリケーションまたは Exchange UM サーバーに呼び出しをルーティングするのにテーブルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8879d-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="8879d-p104">割り当てられていない番号の表の構成方法はその使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を変更できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8879d-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="8879d-116">割り当てられていない電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="8879d-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="8879d-117">アナウンス アプリケーションの割り当てられていない番号の範囲を構成するのにには、次の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="8879d-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8879d-118">システムにする必要があります表は、未使用の番号を構成する前にお知らせの定義が既にあるか、または、Exchange ユニファイド メッセージング (UM) の自動応答を設定します。</span><span class="sxs-lookup"><span data-stu-id="8879d-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8879d-119">誰かを呼び出すと、割り当てられていない番号、Skype ビジネス サーバーの上から下への番号の割り当てられていないテーブルを検索し、最初に一致する範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="8879d-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="8879d-120">したがって、最後の手段として実行される処理は、表の最終範囲に指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8879d-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="8879d-121">Skype ビジネス サーバーのコントロール パネルを使用して割り当てられていない電話番号を構成するには</span><span class="sxs-lookup"><span data-stu-id="8879d-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="8879d-122">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8879d-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8879d-123">詳細については、**セットアップのアクセス許可の委任**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8879d-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8879d-124">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8879d-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8879d-125">左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="8879d-126">[**割り当てられていない番号**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8879d-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="8879d-p107">新しい番号範囲を作成するには、[**新規**] をクリックします。[**名前**] にこの番号範囲の識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8879d-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8879d-129">割り当てられていない番号の新しい範囲をデータベースに送信した後は、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8879d-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="8879d-p108">既存の番号範囲を変更するには、番号範囲の名前または名前の一部を検索フィールドに入力します。結果の番号範囲の一覧で、対象の名前をクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8879d-132">最初の [**数値の範囲**] フィールドに範囲の開始番号を入力し、2 番目の [**数値の範囲**] フィールドに範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8879d-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="8879d-133">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8879d-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="8879d-134">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8879d-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="8879d-135">番号が正規表現に一致する必要があります (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?。</span><span class="sxs-lookup"><span data-stu-id="8879d-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="8879d-136">つまり、番号の先頭に文字列 tel: (その文字列を指定しない場合に自動的に追加)、プラス記号 (+) と数字の 1 9 から。</span><span class="sxs-lookup"><span data-stu-id="8879d-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="8879d-137">電話番号が最大 17 桁にすることができ、拡張した形式で続いて ext = 内線番号の後にします。</span><span class="sxs-lookup"><span data-stu-id="8879d-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="8879d-138">[**アナウンス サービス**] で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8879d-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="8879d-139">[**アナウンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="8879d-140">[**Exchange UM**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="8879d-141">前の手順で [**アナウンス**] をクリックした場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8879d-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="8879d-142">a.</span><span class="sxs-lookup"><span data-stu-id="8879d-142">a.</span></span> <span data-ttu-id="8879d-143">**宛先サーバーの FQDN**を [**選択**] をクリックして、[割り当てられていない番号は、この範囲への着信呼び出しを処理し、 **[ok]**をクリックし、アナウンス アプリケーションを実行するアプリケーション サービスのサービス ID] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="8879d-144">b.</span><span class="sxs-lookup"><span data-stu-id="8879d-144">b.</span></span> <span data-ttu-id="8879d-145">[**アナウンス**] で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="8879d-146">前の手順で [**Exchange UM**] をクリックした場合は、[**自動応答の電話番号**] で、[**選択**] をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="8879d-147">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="8879d-p112">[**割り当てられていない番号**] ページで、割り当てられていない番号範囲が希望どおりの順序で並んでいることを確認します。表で範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8879d-150">Skype ビジネス サーバーのでは、上から下への番号の割り当てられていないテーブルを検索し、未使用の番号と一致する最初の範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="8879d-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="8879d-151">重複する範囲があり、そのうちの 1 つが最後のアクションを指定している場合は、その範囲が一覧の一番下にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8879d-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="8879d-152">割り当てられていない番号範囲が希望どおりの順序で並んでいることを確認したら、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="8879d-153">割り当てられていない電話番号を構成するビジネス サーバー管理シェルの Skype を使用するには</span><span class="sxs-lookup"><span data-stu-id="8879d-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="8879d-154">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8879d-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8879d-155">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8879d-156">**新規 CsUnassignedNumber**を使用して、新しい割り当てられていない番号範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="8879d-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="8879d-157">**セット CsUnassignedNumber**を使用すると、既存の割り当てられていない番号範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8879d-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8879d-p115">重複する範囲があり、それらを特定の順序で適用する場合は、Priority パラメーターを含めます。最も優先度の高い範囲が通話に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8879d-p115">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span> 
  
    <span data-ttu-id="8879d-160">コマンド ラインで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8879d-160">At the command line, do one of the following:</span></span>
    
     - <span data-ttu-id="8879d-161">アナウンス サービスの番号範囲を作成するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8879d-161">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="8879d-162">Exchange UM 自動応答の番号範囲を作成するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8879d-162">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="8879d-163">例:</span><span class="sxs-lookup"><span data-stu-id="8879d-163">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="8879d-164">または</span><span class="sxs-lookup"><span data-stu-id="8879d-164">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

    <span data-ttu-id="8879d-165">次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8879d-165">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="8879d-166">未使用の番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="8879d-166">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="8879d-167">未使用の番号の範囲を削除するのにはビジネス サーバーのコントロール パネルの Skype を使用するには</span><span class="sxs-lookup"><span data-stu-id="8879d-167">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="8879d-168">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8879d-168">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8879d-169">詳細については、**セットアップのアクセス許可の委任**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8879d-169">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8879d-170">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8879d-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="8879d-171">左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-171">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="8879d-172">[**割り当てられていない番号**] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="8879d-172">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="8879d-173">結果の番号範囲の一覧で、名前をクリックして、[**編集**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-173">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="8879d-174">[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-174">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="8879d-175">未使用の番号の範囲を削除するのには Skype ビジネス サーバー管理シェルを使用するには</span><span class="sxs-lookup"><span data-stu-id="8879d-175">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="8879d-176">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8879d-176">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8879d-177">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8879d-177">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8879d-178">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8879d-178">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="8879d-179">例:</span><span class="sxs-lookup"><span data-stu-id="8879d-179">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="8879d-180">詳細オプションの詳細については、[削除 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8879d-180">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8879d-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="8879d-181">See also</span></span>

#### 

[<span data-ttu-id="8879d-182">新しい-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="8879d-182">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="8879d-183">セット CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="8879d-183">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="8879d-184">Get CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="8879d-184">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)

