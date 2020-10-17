---
title: 'Lync Server 2013: 会議ポリシーの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc01c8bed503f06806c873431ef201e03c31811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516894"
---
# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="12f18-102">Lync Server 2013 での会議ポリシーの作成または変更</span><span class="sxs-lookup"><span data-stu-id="12f18-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f18-103">_**トピックの最終更新日:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="12f18-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="12f18-104">ユーザーレベルまたはサイトレベルの会議ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="12f18-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="12f18-105">ユーザーレベルのポリシーをユーザーに割り当てる方法の詳細については、「 [Lync Server 2013 でユーザー単位の会議ポリシーを割り当てる](lync-server-2013-assign-a-per-user-conferencing-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12f18-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="12f18-106">利用可能なすべての電話会議ポリシー設定の一覧については、「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12f18-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="12f18-107">新しいユーザーまたはサイトポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="12f18-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="12f18-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="12f18-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12f18-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="12f18-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12f18-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12f18-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12f18-111">左側のナビゲーション バーで [**会議**] をクリックし、[**電話会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="12f18-112">[**新規**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="12f18-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="12f18-113">ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="12f18-114">[ **新しい会議ポリシー**] の [ **名前**] に、ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="12f18-114">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="12f18-115">サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="12f18-116">[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="12f18-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="12f18-117">サイトの一覧で、対象のサイトをクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-117">In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12f18-118">サイト名は会議ポリシー名になり、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="12f18-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="12f18-119">[ **説明**] にポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="12f18-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="12f18-p105">**[開催者ポリシー]** の **[最大会議サイズ]** に、会議で許可する最大ユーザー数を入力します。 既定では、最大会議サイズは 250 です。</span><span class="sxs-lookup"><span data-stu-id="12f18-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="12f18-122">ユーザーが匿名ユーザーを会議に招待できないようにするには、**[参加者に匿名ユーザーの招待を許可する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="12f18-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="12f18-123">匿名ユーザーとは、組織の Active Directory ドメインサービスに資格情報を持たず、そのために認証されないユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="12f18-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="12f18-124">既定では、ユーザーは匿名ユーザーを会議に招待できます。</span><span class="sxs-lookup"><span data-stu-id="12f18-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="12f18-125">**[レコーディング]** で、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="12f18-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="12f18-p107">参加者が会議をレコーディングできないようにするには、**[なし]** をクリックします。 これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="12f18-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="12f18-128">参加者による会議のレコーディングを許可するには、**[レコーディングを有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="12f18-p108">外部の参加者による会議のレコーディングを許可するには、**[フェデレーションと匿名の参加者によるレコーディングを許可する]** チェック ボックスをオンにします。 既定では、外部の参加者は会議をレコーディングできません。</span><span class="sxs-lookup"><span data-stu-id="12f18-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="12f18-131">**[オーディオ/ビデオ]** で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="12f18-132">音声とビデオを使用できないようにするには、**[なし]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="12f18-133">音声の使用は許可するが、ビデオの使用は許可しない場合は、**[IP オーディオを有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="12f18-p109">音声とビデオの使用を許可する場合は、**[IP オーディオ/ビデオを有効にする]** をクリックします。 これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="12f18-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="12f18-136">**[オーディオ/ビデオ]** で音声の使用の許可を選択する場合、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="12f18-p110">ユーザーがダイヤル インで会議に参加できないようにするには、**[PSTN ダイヤルイン会議を有効にする]** チェック ボックスをオフにします。 既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤル インできます。</span><span class="sxs-lookup"><span data-stu-id="12f18-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="12f18-p111">ユーザーによる会議へのダイヤル インを許可し、未認証 (匿名) のユーザーがダイヤル アウト番号を使用して会議に参加できるようにするには、**[匿名の参加者によるダイヤル アウトを許可する]** チェック ボックスをオンにします。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し会議に参加します。 既定では、匿名ユーザーはダイヤル アウト番号を使用して、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="12f18-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="12f18-142">[ **音声**ビデオ] でビデオの使用を許可することを選択した場合は、[ **複数のビデオストリームを許可** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12f18-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="12f18-143">**[共同作業データ]** で、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="12f18-144">共同作業データを使用できないようにするには、**[なし]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="12f18-p112">共同作業データを許可するには、**[共同作業データの有効化]** をクリックします。 これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="12f18-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="12f18-147">**[共同作業データ]** で共同作業データの許可を選択した場合、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="12f18-p113">外部ダウンロードを使用できないようにするには、**[フェデレーションと匿名の参加者によるコンテンツのダウンロードを許可する]** チェック ボックスをオフにします。 既定では、外部ユーザーはコンテンツをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="12f18-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="12f18-p114">ファイル転送を使用できないようにするには、**[参加者によるファイルの転送を許可する]** チェック ボックスをオフにします。 既定では、ユーザーはファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="12f18-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="12f18-152">コメントを使用できないようにするには、**[コメントを有効にする]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="12f18-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="12f18-153">シャード PowerPoint プレゼンテーションで注釈を使用するには、[ **powerpoint のコメントを有効**にする] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="12f18-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="12f18-154">既定では、コメントは許可されます。</span><span class="sxs-lookup"><span data-stu-id="12f18-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="12f18-p116">ポーリングを使用できないようにするには、**[ポーリングを有効にする]** チェック ボックスをオフにします。 既定では、ポーリングは許可されます。</span><span class="sxs-lookup"><span data-stu-id="12f18-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="12f18-157">**[アプリケーション共有]** で、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="12f18-158">アプリケーション共有を使用できないようにするには、**[アプリケーションの共有を無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="12f18-p117">アプリケーション共有の使用を許可するには、**[アプリケーションの共有を有効にする]** をクリックします。 これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="12f18-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="12f18-161">**[アプリケーション共有]** でアプリケーション共有の許可を選択した場合、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="12f18-p118">会議の参加者がアプリケーション共有を制御できないようにするには、**[参加者による制御を許可する]** チェック ボックスをオフにします。 既定では、参加者はアプリケーション共有を制御できます。</span><span class="sxs-lookup"><span data-stu-id="12f18-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="12f18-p119">会議の参加者によるアプリケーション共有の制御の許可を選択した場合、外部ユーザーによるアプリケーション共有の制御を許可するには、**[フェデレーションと匿名の参加者による制御を許可する]** チェック ボックスをオンにします。 既定では、外部ユーザーはアプリケーション共有を制御できません。</span><span class="sxs-lookup"><span data-stu-id="12f18-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="12f18-166">**[参加者ポリシー]** で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f18-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="12f18-167">アプリケーション共有とデスクトップ共有を両方使用できないようにするには、**[アプリケーションとデスクトップの共有を無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="12f18-168">アプリケーション共有は許可するが、デスクトップ共有は許可しない場合は、**[アプリケーションの共有を有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="12f18-p120">アプリケーション共有とデスクトップ共有を両方許可するには、**[アプリケーションとデスクトップの共有を有効にする]** をクリックします。 これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="12f18-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="12f18-p121">ピアツーピアのファイル転送を使用できないようにするには、**[ピアツーピアのファイル転送を有効にする]** チェック ボックスをオフにします。 既定では、ピアツーピアのファイル転送は許可されます。</span><span class="sxs-lookup"><span data-stu-id="12f18-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="12f18-p122">ピアツーピアのレコーディングを許可するには、**[ピアツーピアのレコーディングを有効にする]** チェック ボックスをオンにします。 既定では、ピアツーピアのレコーディングは許可されません。</span><span class="sxs-lookup"><span data-stu-id="12f18-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="12f18-175">参加者が複数のビデオストリームと参加できるようにするには、[ **参加者が複数のビデオストリームで参加** できるようにする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12f18-175">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="12f18-176">既定では、複数のビデオストリームが許可されています。</span><span class="sxs-lookup"><span data-stu-id="12f18-176">By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="12f18-177">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="12f18-178">既存のユーザーまたはサイトポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="12f18-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="12f18-179">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="12f18-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12f18-180">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="12f18-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12f18-181">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12f18-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12f18-182">左側のナビゲーション バーで [**会議**] をクリックし、[**電話会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="12f18-183">電話会議ポリシーの一覧で、変更するポリシーをクリックし、[ **編集**] をクリックして、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="12f18-184">[ **会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定のいずれかを変更します。</span><span class="sxs-lookup"><span data-stu-id="12f18-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="12f18-185">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12f18-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

