---
title: Skype for Business Server で割り当てられていない番号範囲を作成または変更する
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Skype for Business Server のアナウンス アプリケーションの割り当てられていない番号範囲を作成、変更、または削除エンタープライズ VoIP。 これは、割り当てられていない番号への呼び出しの処理方法に影響します。
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837087"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="5f65f-104">Skype for Business Server で割り当てられていない番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="5f65f-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="5f65f-105">Skype for Business Server のアナウンス アプリケーションの割り当てられていない番号範囲を作成、変更、または削除エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="5f65f-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="5f65f-106">これは、割り当てられていない番号への呼び出しの処理方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="5f65f-107">Skype for Business Server を使用すると、組織で有効だが、ユーザーまたは電話に割り当てられていない電話番号への着信呼び出しに対する処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="5f65f-108">このような呼び出しを処理するには、割り当てられていない番号の表を設定します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="5f65f-109">この表を使用して、呼び出しをアナウンス アプリケーションまたは Exchange UM サーバーにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="5f65f-110">割り当てられていない番号の表の構成方法はその使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5f65f-110">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="5f65f-111">組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-111">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="5f65f-112">割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-112">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="5f65f-113">有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-113">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="5f65f-114">割り当てられていない内線番号を表に含める場合は、特定の番号に対して発生するアクションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-114">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="5f65f-115">たとえば、カスタマー サービス デスクの内線番号を変更する場合は、古い顧客サービス番号を表に含め、新しい番号を提供するアナウンスに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-115">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="5f65f-116">割り当てられていない電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="5f65f-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="5f65f-117">アナウンス アプリケーションの割り当てられていない番号範囲を構成するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f65f-118">割り当てられていない番号の表を構成する前に、システムでアナウンスが定義されている必要があります。または、Exchange ユニファイド メッセージング (UM) を設定自動応答があります。</span><span class="sxs-lookup"><span data-stu-id="5f65f-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="5f65f-119">割り当てられていない番号に電話がかかっている場合、Skype for Business Server は割り当てられていない番号の表を上から下に検索し、最初に一致する範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="5f65f-120">したがって、最後の方法として実行するアクションは、表の最後の範囲に対して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f65f-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="5f65f-121">Skype for Business Server コントロール パネルを使用して割り当てられていない電話番号を構成するには</span><span class="sxs-lookup"><span data-stu-id="5f65f-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="5f65f-p106">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f65f-p106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="5f65f-124">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5f65f-125">左側のナビゲーション バーで [音声機能] **をクリックし**、[割り当てられていない番号 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5f65f-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="5f65f-126">[割 **り当てられていない番号] ページ** で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5f65f-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="5f65f-127">新しい番号範囲を作成するには、[新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5f65f-127">To create a new number range, click **New**.</span></span> <span data-ttu-id="5f65f-128">[**名前**] に、この番号範囲の識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-128">In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5f65f-129">新しい割り当てられていない番号範囲をデータベースにコミットした後、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f65f-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="5f65f-130">既存の番号範囲を変更するには、検索フィールドに番号範囲の名前のすべてまたは一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-130">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="5f65f-131">表示される番号範囲の一覧で、必要な名前をクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5f65f-131">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5f65f-132">最初の **[数値の範囲]** フィールドに範囲の開始番号を入力し、2 番目の **[数値の範囲]** フィールドに範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="5f65f-133">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5f65f-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="5f65f-134">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f65f-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="5f65f-135">数値は正規表現 (tel:)?( )と一致する必要 \+ があります。[1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="5f65f-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="5f65f-136">つまり、番号は tel という文字列で始まる可能性があります (その文字列を指定しない場合、自動的に追加されます)、プラス記号 (+)、および 1 ~ 9 の数字です。</span><span class="sxs-lookup"><span data-stu-id="5f65f-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="5f65f-137">電話番号は最大 17 桁で、その後に内線番号 ;ext= の後に内線番号を続けることもできます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="5f65f-138">**[アナウンス サービス]** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="5f65f-139">**[アナウンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="5f65f-140">**[Exchange UM]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="5f65f-141">前の手順で **[アナウンス]** をクリックした場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="5f65f-142">a. </span><span class="sxs-lookup"><span data-stu-id="5f65f-142">a.</span></span> <span data-ttu-id="5f65f-143">**[宛先サーバーの FQDN]** で、**[選択]** をクリックし、この割り当てられていない番号範囲への着信通話を処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="5f65f-144">b.</span><span class="sxs-lookup"><span data-stu-id="5f65f-144">b.</span></span> <span data-ttu-id="5f65f-145">**[アナウンス]** で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="5f65f-146">前の手順で **[Exchange UM]** をクリックした場合は、**[自動応答の電話番号]** で、**[選択]** をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="5f65f-147">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="5f65f-148">[ **割り当て** られていない番号] ページで、割り当てられていない番号の範囲が必要な順序で並べ替えられていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-148">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="5f65f-149">テーブル内での範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックし、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-149">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5f65f-150">Skype for Business Server は、割り当てられていない番号の表を上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="5f65f-151">重複する範囲を持ち、1 つの範囲で最後のアクションを指定する場合は、範囲がリストの一番下にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f65f-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="5f65f-152">割り当てられていない番号範囲が必要な順序で表示されている場合は、[すべて確定] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5f65f-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="5f65f-153">Skype for Business Server 管理シェルを使用して割り当てられていない電話番号を構成するには</span><span class="sxs-lookup"><span data-stu-id="5f65f-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="5f65f-154">Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」の説明に従って必要なユーザー権限を使用してログオン **します。**</span><span class="sxs-lookup"><span data-stu-id="5f65f-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="5f65f-155">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5f65f-156">**新しい割り当てられていない番号範囲を作成するには、New-CsUnassignedNumber** を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="5f65f-157">**既存の割り当てられていない番号範囲を変更するには、Set-CsUnassignedNumber** を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5f65f-158">重複する範囲がある場合に、特定の順序で範囲を適用する場合は、Priority パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="5f65f-159">最も優先度の高い範囲が呼び出しに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="5f65f-160">値 0 は最高の優先度を表します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="5f65f-161">コマンド ラインで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5f65f-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="5f65f-162">アナウンス サービスの番号範囲を作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="5f65f-163">または、Exchange UM メールボックスの番号範囲を作成するには自動応答実行します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="5f65f-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="5f65f-165">または</span><span class="sxs-lookup"><span data-stu-id="5f65f-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="5f65f-166">次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f65f-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="5f65f-167">番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="5f65f-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="5f65f-168">Skype for Business Server コントロール パネルを使用して割り当てられていない番号範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="5f65f-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="5f65f-p116">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f65f-p116">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="5f65f-171">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5f65f-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5f65f-172">左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="5f65f-173">[**割り当てられていない番号**] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="5f65f-174">結果の番号範囲の一覧で、名前をクリックして、[**編集**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="5f65f-175">[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="5f65f-176">Skype for Business Server 管理シェルを使用して割り当てられていない番号範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="5f65f-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="5f65f-177">Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**</span><span class="sxs-lookup"><span data-stu-id="5f65f-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="5f65f-178">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f65f-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5f65f-179">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="5f65f-180">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f65f-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="5f65f-181">その他のオプションの詳細については [、「Remove-CsCallParkOrbit」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f65f-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5f65f-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f65f-182">See also</span></span>

[<span data-ttu-id="5f65f-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="5f65f-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="5f65f-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="5f65f-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="5f65f-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="5f65f-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
