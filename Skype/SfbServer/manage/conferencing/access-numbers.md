---
title: 'Skype for Business Server でダイヤルイン会議アクセス番号を管理する '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '概要: Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。'
ms.openlocfilehash: bd2aff1789c040667062d34b8bc037fd0543c029
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991922"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="fd98c-103">Skype for Business Server でダイヤルイン会議アクセス番号を管理する</span><span class="sxs-lookup"><span data-stu-id="fd98c-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="fd98c-104">**概要:** Skype for Business Server でダイヤルイン会議アクセス番号を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="fd98c-105">ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="fd98c-106">それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="fd98c-107">このトピックでは、既存のダイヤルイン会議アクセス番号を表示、変更、または削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="fd98c-108">最初のダイヤルインアクセス番号の作成方法の詳細については、「 [Skype For Business Server でダイヤルイン会議を構成](../../deploy/deploy-conferencing/dial-in-conferencing.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="fd98c-109">ダイヤルイン会議アクセス番号の表示</span><span class="sxs-lookup"><span data-stu-id="fd98c-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="fd98c-110">Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fd98c-111">Skype for Business Server コントロールパネルを使用して、ダイヤルインアクセス番号を表示する</span><span class="sxs-lookup"><span data-stu-id="fd98c-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="fd98c-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="fd98c-113">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fd98c-114">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="fd98c-115">[**ダイヤルイン アクセス番号**] ページで、表示するアクセス番号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="fd98c-116">[**編集**] で、[**詳細の表示**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fd98c-117">Skype for Business Server 管理シェルを使用して、ダイヤルインアクセス番号を表示する</span><span class="sxs-lookup"><span data-stu-id="fd98c-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="fd98c-118">ダイヤルイン アクセス番号に関する情報を表示するには、**Get-CsDialInConferencingAccessNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="fd98c-119">次のコマンドは、組織で使用できるように構成されているすべてのダイヤルイン会議アクセス番号のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="fd98c-120">次に、戻される情報の種類に関する例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="fd98c-121">詳細については、「 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="fd98c-122">ダイヤルイン会議アクセス番号の変更</span><span class="sxs-lookup"><span data-stu-id="fd98c-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="fd98c-123">Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルインアクセス番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fd98c-124">Skype for Business Server コントロールパネルを使用して、ダイヤルインアクセス番号を変更する</span><span class="sxs-lookup"><span data-stu-id="fd98c-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="fd98c-125">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="fd98c-126">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fd98c-127">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="fd98c-128">[**ダイヤルイン アクセス番号**] ページで、リスト内にあるダイヤルイン アクセス番号のいずれかをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd98c-p103">検索フィールドを使用してダイヤルイン アクセス番号のリストの列の内容を検索しても、結果が予想どおりにならない場合があります。代わりに、対象の列を基にしてリストを並べ替えて、表示または変更するダイヤルイン アクセス番号を特定してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="fd98c-131">[**表示番号**] に、公衆交換電話網 (PSTN) 電話を使用するユーザーが会議に参加するときにダイヤルする、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="fd98c-132">この番号は、会議出席依頼とダイヤルイン会議設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="fd98c-133">[**表示名**] に、ダイヤルイン アクセス番号の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="fd98c-134">これは、Skype for Business の検索結果のダイヤルインアクセス番号と関連付けられた名前です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="fd98c-135">この名前は、ユーザーがアクセス番号を呼び出すとき、クライアントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="fd98c-p105">[**回線 URI**] に、ダイヤルイン アクセス番号の E.164 番号を、電話番号の前に + 記号を付加し、スペースを含めない電話 URI 形式で入力します。たとえば、tel:+14255550200 のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd98c-138">同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fd98c-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="fd98c-139">[**SIP URI**] で、次の操作を行ってください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="fd98c-140">テキスト ボックスで、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="fd98c-141">この SIP URI は、通話通知メッセージや以前のバージョンの Lync クライアントのように、さまざまな場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd98c-p107">同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。SIP URI を、アクセス番号の作成後に変更することはできません。SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="fd98c-145">ドロップダウンリストボックスで、ダイヤルインアクセス番号をサポートする会議アテンダントアプリケーションのドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="fd98c-146">[**プール**] で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd98c-147">アクセス番号の作成後にプールを変更する必要がある場合は、**Move-CsApplicationEndpoint** コマンドレットを使用するか、またはアクセス番号をいったん削除して作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="fd98c-148">[**第 1 言語**] で、このダイヤルイン アクセス番号の案内を再生するときに使用される言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="fd98c-p108">第 1 言語とは、会議アテンダントが着信への応答に使用する言語のことです。サポートされている言語は、各アクセス電話番号と共に、ダイヤルイン会議の設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="fd98c-151">(オプション) [**第 2 言語 (4 つまで)**] で、[**追加**] をクリックして、このダイヤルイン アクセス番号への発信者用にサポートする 1 つ以上の追加言語を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="fd98c-p109">ダイヤルイン アクセス番号ごとに最大 4 つの第 2 言語を選択できます。ユーザーは、会議にダイヤルインする際に会議 ID を入力する前に、第 2 言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="fd98c-154">ダイヤルインアクセス番号の領域を追加するには、[**関連付けられた地域**] の [**追加**] をクリックし、このダイヤルインアクセス番号のダイヤルプランに関連付けられている1つ以上の領域をクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="fd98c-155">ダイヤルイン アクセス番号から地域を削除するには、[**関連付けられている地域**] で削除する地域をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="fd98c-156">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fd98c-157">Skype for Business Server 管理シェルを使用して、ダイヤルインアクセス番号を変更する</span><span class="sxs-lookup"><span data-stu-id="fd98c-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="fd98c-158">ダイヤルイン アクセス番号を変更するには、**Set-CsDialInConferencingAccessNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="fd98c-p110">次のコマンドにより、Identity が sip:RedmondDialIn@litwareinc.com になっているダイヤルイン会議アクセス番号の DisplayName プロパティが変更されます。この例では、表示名が「Redmond Dial-In Access Number」に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p110">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="fd98c-p111">次の例では、sip:RedmondDialIn@litwareinc.com という ID を持つダイヤルイン会議アクセス番号が 2 つの地域 (Redmond および Seattle) を含むように変更します。これを行うため、Region パラメーターを呼び出して、その後に 2 つの地域 (コンマで区切られた 2 つの文字列値) を指定します。このコマンドは、Redmond および Seattle の両地域がダイヤル プランで既に定義されていないと失敗します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-p111">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="fd98c-164">詳細については、「 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="fd98c-165">ダイヤルイン会議アクセス番号の削除</span><span class="sxs-lookup"><span data-stu-id="fd98c-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="fd98c-166">Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を削除できます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fd98c-167">Skype for Business Server コントロールパネルを使用して、ダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="fd98c-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fd98c-168">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="fd98c-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="fd98c-169">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fd98c-170">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="fd98c-171">[ダイヤルイン アクセス番号] ページの一覧で、削除するダイヤルイン番号をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="fd98c-172">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fd98c-173">Skype for Business Server 管理シェルを使用して、ダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="fd98c-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="fd98c-174">ダイヤルイン会議アクセス番号を削除するには、**Remove-CsDialInConferencingAccessNumber** を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="fd98c-175">次のコマンドは、ID が sip:RedmondDialInAccess@litwareinc.com であるダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="fd98c-176">次のコマンドは、Northwest 地域に関連するすべてのダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="fd98c-177">次のコマンドは、第 1 言語がイタリア語であるすべてのダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="fd98c-178">詳細については、「 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

