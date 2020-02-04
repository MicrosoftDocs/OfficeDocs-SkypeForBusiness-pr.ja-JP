---
title: 'Lync Server 2013: ダイヤルインの会議ポリシーを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="17645-102">Lync Server 2013 でダイヤルインの会議ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="17645-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17645-103">_**最終更新日:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="17645-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="17645-p101">会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17645-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="17645-109">会議ポリシーの次のフィールドを確認します。</span><span class="sxs-lookup"><span data-stu-id="17645-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="17645-110">**[参加者に匿名ユーザー**   の招待を許可する] この設定では、会議の開催者が、会議に匿名 (つまり、認証されていない) 参加者を招待することができます。</span><span class="sxs-lookup"><span data-stu-id="17645-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="17645-111">ダイヤルイン会議では、この設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="17645-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="17645-112">既定では、既定で [グローバル会議] ポリシーに設定されています。</span><span class="sxs-lookup"><span data-stu-id="17645-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="17645-113">**[Pstn ダイヤルイン会議**   を有効にする] この設定を使用すると、ユーザーは pstn からダイヤルインして会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="17645-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="17645-114">この設定は、ダイヤルイン会議では必須です。</span><span class="sxs-lookup"><span data-stu-id="17645-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="17645-115">既定では、既定で [グローバル会議] ポリシーに設定されています。</span><span class="sxs-lookup"><span data-stu-id="17645-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="17645-116">**[匿名の参加者にダイヤルアウト**   を許可する] この設定では、既に会議に参加している匿名ユーザーが電話番号にダイヤルアウトして、会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="17645-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="17645-117">ダイヤルイン会議では、この設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="17645-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="17645-118">既定では、既定では、既定では [グローバル会議] ポリシーが選択されていません。</span><span class="sxs-lookup"><span data-stu-id="17645-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="17645-119">**[エンタープライズボイスに対して参加者が有効になっていない**   ] この設定では、エンタープライズ voip が有効になっていない会議の参加者と開催者が電話番号にダイヤルアウトして、会議のオーディオ部分に参加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="17645-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="17645-120">ダイヤルアウト通話は、開催者に割り当てられた音声ポリシーに基づいて承認されます。</span><span class="sxs-lookup"><span data-stu-id="17645-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="17645-121">既定では、既定では、既定では [グローバル会議] ポリシーが選択されていません。</span><span class="sxs-lookup"><span data-stu-id="17645-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="17645-122">設定の既定値が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="17645-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17645-123">この機能を有効にするには、エンタープライズボイスに対して有効になっていない会議開催者には、そのユーザーが開催した会議からのダイヤルアウトを承認する適切な音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17645-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="17645-124">ボイスポリシーは、Lync Server 管理シェルからエンタープライズ Voip が有効になっていないユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="17645-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="17645-125">ユーザーに対して明示的に音声ポリシーが割り当てられていない場合は、サイトのボイスポリシーがダイヤルアウト要求を承認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="17645-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="17645-126">サイトのボイスポリシーがない場合は、グローバルボイスポリシーが使用されます。&nbsp;</span><span class="sxs-lookup"><span data-stu-id="17645-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="17645-127">このセクションの手順では、会議ポリシーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="17645-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="17645-128">既定の会議ポリシーで参加者エクスペリエンスを定義するすべての設定を構成する方法の詳細については、「 [Lync Server 2013 で会議の構成設定のコレクションを作成または変更](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17645-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="17645-129">特定のユーザーまたはユーザーのグループに対して会議ポリシーを作成する方法の詳細については、「 [Lync Server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17645-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="17645-130">利用可能なすべての会議ポリシー設定の一覧については、「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17645-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="17645-131">ダイヤルインの会議ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="17645-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="17645-132">RTCUniversalServerAdmins グループのメンバーとして、または**Cs-serveradministrator**または**csadministrator**の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="17645-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="17645-133">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="17645-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17645-134">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="17645-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17645-135">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17645-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="17645-136">[**会議ポリシー** ] タブで、会議ポリシー名をダブルクリックして、[**会議ポリシーの編集**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="17645-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="17645-137">ダイヤルイン会議のフィールドが組織に適していることを確認し、必要に応じて設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="17645-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="17645-138">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17645-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

