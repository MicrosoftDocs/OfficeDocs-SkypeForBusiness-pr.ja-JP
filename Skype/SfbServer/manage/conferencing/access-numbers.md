---
title: 'Skype for Business Server でダイヤルイン会議アクセス番号を管理する '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '概要: Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。'
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099153"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="b9aaa-103">Skype for Business Server でダイヤルイン会議アクセス番号を管理する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="b9aaa-104">**概要:** Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="b9aaa-p101">ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="b9aaa-107">このトピックでは、既存のダイヤルイン会議アクセス番号を表示、変更、または削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="b9aaa-108">初期ダイヤルイン アクセス番号を作成する方法の詳細については [、「Configure dial-in conferencing in Skype for Business Server」を参照してください](../../deploy/deploy-conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="b9aaa-109">ダイヤルイン会議アクセス番号の表示</span><span class="sxs-lookup"><span data-stu-id="b9aaa-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="b9aaa-110">Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b9aaa-111">Skype for Business Server コントロール パネルを使用してダイヤルイン アクセス番号を表示する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9aaa-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b9aaa-113">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b9aaa-114">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b9aaa-115">[**ダイヤルイン アクセス番号**] ページで、表示するアクセス番号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="b9aaa-116">[ **編集] で**、[詳細の **表示] チェック ボックス** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b9aaa-117">Skype for Business Server 管理シェルを使用してダイヤルイン アクセス番号を表示する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b9aaa-118">ダイヤルイン アクセス番号に関する情報を表示するには **、Get-CsDialInConferencingAccessNumber コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="b9aaa-119">次のコマンドは、組織内で使用するように構成されたダイヤルイン会議アクセス番号のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b9aaa-120">返される情報の種類の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="b9aaa-121">詳細については [、「Get-CsDialInConferencingAccessNumber」を参照してください](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-121">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="b9aaa-122">ダイヤルイン会議アクセス番号の変更</span><span class="sxs-lookup"><span data-stu-id="b9aaa-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="b9aaa-123">ダイヤルイン アクセス番号は、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b9aaa-124">Skype for Business Server コントロール パネルを使用してダイヤルイン アクセス番号を変更する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9aaa-125">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b9aaa-126">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b9aaa-127">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b9aaa-128">[ダイヤル **イン アクセス** 番号] ページで、リスト内のダイヤルイン アクセス番号のいずれかをクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9aaa-129">検索フィールドを使用して、ダイヤルイン アクセス番号の一覧にある列の内容を検索すると、期待した結果が得られるとは思いません。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="b9aaa-130">代わりに、リストを関心のある列で並べ替え、表示または変更するダイヤルイン アクセス番号を識別します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="b9aaa-131">[ **表示番号]** に、公衆交換電話網 (PSTN) 電話ユーザーが電話会議に参加するためにダイヤルする電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="b9aaa-132">この番号は、会議出席依頼とダイヤルイン会議の設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="b9aaa-133">[ **表示名]** に、ダイヤルイン アクセス番号の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="b9aaa-134">これは、Skype for Business 検索結果のダイヤルイン アクセス番号に関連付けられている名前です。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="b9aaa-135">この名前は、ユーザーがアクセス番号を呼び出す際にクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="b9aaa-136">[ **行 URI]** に、ダイヤルイン アクセス番号の E.164 番号を TEL URI 形式で入力します。この番号の前に + 記号を付け、スペースを除きます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="b9aaa-137">たとえば、tel:+14255550200。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9aaa-138">同じ回線 URI を別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="b9aaa-139">**SIP URI で、** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="b9aaa-140">テキスト ボックスに、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="b9aaa-141">この SIP URI は、呼び出し通知メッセージや以前のバージョンの Lync クライアントなど、さまざまな場所に表示されます。ただし、これらに限定されません。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9aaa-142">同じ SIP URI を別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="b9aaa-143">SIP URI は、アクセス番号の作成後に変更できません。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="b9aaa-144">SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="b9aaa-145">ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議応答アプリケーションのドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="b9aaa-146">[ **プール]** で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行しているプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9aaa-147">アクセス番号の作成後にプールを変更する必要がある場合は **、Move-CsApplicationEndpoint** コマンドレットを使用するか、アクセス番号を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="b9aaa-148">[ **プライマリ言語]** で、このダイヤルイン アクセス番号のプロンプトを再生する言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="b9aaa-149">プライマリ言語は、会議アテンダントが通話に応答するために使用する言語です。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="b9aaa-150">サポートされている言語は、[ダイヤルイン会議の設定] Web ページの各アクセス電話番号と一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="b9aaa-151">(省略可能)[セカンダリ言語 (最大 **4 言語)]** で、[追加] をクリックし、このダイヤルイン アクセス番号の発信者をサポートする 1 つ以上の追加言語を選択し **、[OK]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="b9aaa-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="b9aaa-152">ダイヤルイン アクセス番号ごとに最大 4 つのセカンダリ言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="b9aaa-153">ユーザーは、会議にダイヤルインするときに会議 ID を入力する前に、第 2 言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="b9aaa-154">ダイヤルイン アクセス番号の地域を追加するには、[関連付けられた地域] で、[追加] をクリックし、このダイヤルイン アクセス番号のダイヤル プランに関連付けられている 1 つ以上の地域をクリックし **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="b9aaa-155">ダイヤルイン アクセス番号から地域を削除するには、[関連付けられた地域] で、削除する地域をクリックし、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="b9aaa-156">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b9aaa-157">Skype for Business Server 管理シェルを使用してダイヤルイン アクセス番号を変更する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b9aaa-158">ダイヤルイン アクセス番号を変更するには **、Set-CsDialInConferencingAccessNumber コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="b9aaa-159">次のコマンドは、Id を使用してダイヤルイン会議アクセス番号の DisplayName プロパティを変更 sip:RedmondDialIn@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="b9aaa-160">この例では、表示名は "Redmond Dial-In Access Number" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="b9aaa-161">次の例では、Id サーバーが含まれるダイヤルイン会議アクセス番号 sip:RedmondDialIn@litwareinc.com、Redmond と Seattle の 2 つの地域が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="b9aaa-162">これを行うため、Region パラメーターを呼び出して、その後に 2 つの地域 (コンマで区切られた 2 つの文字列値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="b9aaa-163">このコマンドは、Redmond および Seattle の両地域がダイヤル プランで既に定義されていないと失敗します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="b9aaa-164">詳細については [、「Set-CsDialInConferencingAccessNumber」を参照してください](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-164">For more information, see [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="b9aaa-165">ダイヤルイン会議アクセス番号の削除</span><span class="sxs-lookup"><span data-stu-id="b9aaa-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="b9aaa-166">Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を削除できます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b9aaa-167">Skype for Business Server コントロール パネルを使用してダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b9aaa-168">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="b9aaa-169">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b9aaa-170">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b9aaa-171">[ダイヤルイン アクセス番号] ページの一覧で、削除するダイヤルイン番号をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="b9aaa-172">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b9aaa-173">Skype for Business Server 管理シェルを使用してダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="b9aaa-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b9aaa-174">ダイヤルイン会議アクセス番号を削除するには **、Remove-CsDialInConferencingAccessNumber を使用します**。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="b9aaa-175">次のコマンドは、Id を使用してダイヤルイン会議アクセス番号を削除 sip:RedmondDialInAccess@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="b9aaa-176">次のコマンドは、北西地域に関連付けられているすべてのダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b9aaa-177">次のコマンドは、イタリア語が第一言語であるすべてのダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b9aaa-178">詳細については [、「Remove-CsDialInConferencingAccessNumber」を参照してください](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b9aaa-178">For more information, see [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
