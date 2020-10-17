---
title: 'Lync Server 2013: ダイヤルインの会議ポリシーの構成'
description: 'Lync Server 2013: ダイヤルインの会議ポリシーを構成します。'
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
ms.openlocfilehash: dd8dee1d9e7e6391c6420b15a895199dfc7a8791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564393"
---
# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="dca02-103">Lync Server 2013 でのダイヤルインの会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="dca02-103">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dca02-104">_**トピックの最終更新日:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="dca02-104">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="dca02-p101">会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。 会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。 会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。 複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。 ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dca02-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="dca02-110">会議ポリシーの次のフィールドを確認します。</span><span class="sxs-lookup"><span data-stu-id="dca02-110">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="dca02-111">**参加者に匿名ユーザー**     の招待を許可するこの設定により、会議の開催者は匿名 (つまり、認証されていない) 参加者を会議に招待することができます。</span><span class="sxs-lookup"><span data-stu-id="dca02-111">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="dca02-112">ダイヤルイン会議では、この設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="dca02-112">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="dca02-113">既定では、この設定は既定で [グローバル電話会議ポリシー] で選択されています。</span><span class="sxs-lookup"><span data-stu-id="dca02-113">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="dca02-114">**PSTN ダイヤルイン会議**     を有効にするこの設定では、ユーザーは PSTN からダイヤルインすることによって、電話会議の音声部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="dca02-114">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="dca02-115">この設定は、ダイヤルイン会議には必須です。</span><span class="sxs-lookup"><span data-stu-id="dca02-115">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="dca02-116">既定では、この設定は既定で [グローバル電話会議ポリシー] で選択されています。</span><span class="sxs-lookup"><span data-stu-id="dca02-116">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="dca02-117">**匿名参加者にダイヤルアウト**     を許可するこの設定では、既に会議に参加している匿名ユーザーが、電話番号にダイヤルアウトして会議の音声部分に参加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="dca02-117">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="dca02-118">ダイヤルイン会議では、この設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="dca02-118">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="dca02-119">既定では、この設定は既定のグローバル電話会議ポリシーで選択されていません。</span><span class="sxs-lookup"><span data-stu-id="dca02-119">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="dca02-120">**エンタープライズ voip が有効になっていない参加者にダイヤルアウト**     を許可するこの設定により、エンタープライズ Voip が有効になっていない会議参加者と開催者は、電話番号にダイヤルアウトして会議の音声部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="dca02-120">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="dca02-121">ダイヤルアウト呼び出しは、開催者に割り当てられた音声ポリシーに基づいて承認されます。</span><span class="sxs-lookup"><span data-stu-id="dca02-121">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="dca02-122">既定では、この設定は既定のグローバル電話会議ポリシーで選択されていません。</span><span class="sxs-lookup"><span data-stu-id="dca02-122">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="dca02-123">設定の既定値は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="dca02-123">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dca02-124">この機能を有効にするには、エンタープライズ Voip が有効になっていない会議開催者に、そのユーザーによって開催された会議からのダイヤルアウトを承認するために、適切な音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dca02-124">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="dca02-125">音声ポリシーは、Lync Server 管理シェルからエンタープライズ Voip が有効になっていないユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dca02-125">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="dca02-126">ユーザーに明示的に割り当てられた音声ポリシーがない場合は、サイトの音声ポリシーを使用してダイヤルアウト要求が承認されます。</span><span class="sxs-lookup"><span data-stu-id="dca02-126">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="dca02-127">サイトの音声ポリシーがない場合は、グローバル音声ポリシーが使用されます。&nbsp;</span><span class="sxs-lookup"><span data-stu-id="dca02-127">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="dca02-128">このセクションの手順では、会議ポリシーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dca02-128">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="dca02-129">既定の会議ポリシーでの参加者の操作を定義するすべての設定を構成する方法の詳細については、「 [Lync Server 2013 の会議構成設定のコレクションを作成または変更](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca02-129">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="dca02-130">特定のユーザーまたはユーザーグループに対して会議ポリシーを作成する方法の詳細については、「 [Lync Server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca02-130">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="dca02-131">利用可能なすべての電話会議ポリシー設定の一覧については、「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca02-131">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="dca02-132">ダイヤルインの会議ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="dca02-132">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="dca02-133">RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dca02-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="dca02-134">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dca02-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dca02-135">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca02-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dca02-136">左側のナビゲーション バーで [**会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dca02-136">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="dca02-137">[**会議ポリシー**] タブで、会議ポリシー名をダブルクリックし、[**会議ポリシーの編集**] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="dca02-137">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="dca02-138">ダイヤルイン会議のフィールドが組織に適切に設定されていることを確認します。必要に応じて、設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="dca02-138">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="dca02-139">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dca02-139">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

