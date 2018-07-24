---
title: ビジネス サーバーのため、Skype で会議ポリシーを作成します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: '概要: は、Skype のビジネス サーバーの会議ポリシーを作成する方法を説明します。'
ms.openlocfilehash: 3c71962e42e083ada13b14bdecbefafbbc44f72b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996602"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="2ff26-103">ビジネス サーバーのため、Skype で会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="2ff26-104">**の概要:** ビジネス サーバーの Skype での会議ポリシーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="2ff26-105">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2ff26-106">ビジネス サーバーのコントロール パネルの Skype を使用して、会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2ff26-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2ff26-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2ff26-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="2ff26-110">[**新規**] をクリックし、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2ff26-p101">ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。[**新しい会議ポリシー**] の [**名前**] で、ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="2ff26-p102">サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。サイトの一覧で、対象のサイトをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ff26-116">サイト名は電話会議ポリシー名となり、変更できません。</span><span class="sxs-lookup"><span data-stu-id="2ff26-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="2ff26-117">[**説明**] にポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="2ff26-p103">[**開催者ポリシー**] の [**最大会議サイズ**] に、会議で許可する最大ユーザー数を入力します。既定では、最大会議サイズは 250 です。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="2ff26-120">ユーザーが匿名ユーザーを会議に招待できないようにするには、[**参加者に匿名ユーザーの招待を許可する**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="2ff26-121">匿名ユーザーは、したがって、組織の Active Directory ドメイン サービスと、ユーザーの資格情報がない、認証されていないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="2ff26-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="2ff26-122">既定では、ユーザーは匿名ユーザーを会議に招待できます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="2ff26-123">[**レコーディング**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="2ff26-p105">参加者が会議をレコーディングできないようにするには、[**なし**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="2ff26-126">参加者による会議のレコーディングを許可するには、[**レコーディングを有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="2ff26-p106">外部の参加者による会議のレコーディングを許可するには、[**フェデレーションと匿名の参加者によるレコーディングを許可する**] チェック ボックスをオンにします。既定では、外部の参加者は会議をレコーディングできません。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="2ff26-129">[**音声ビデオ**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="2ff26-130">音声とビデオを使用できないようにするには、[**なし**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="2ff26-131">音声の使用は許可するが、ビデオの使用は許可しない場合は、[**IP オーディオを有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="2ff26-p107">音声とビデオの使用を許可する場合は、[**IP オーディオ/ビデオを有効にする**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="2ff26-134">[**音声ビデオ**] で音声の使用の許可を選択する場合、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="2ff26-p108">ユーザーがダイヤル インで会議に参加できないようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオフにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤル インできます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="2ff26-p109">ユーザーによる会議へのダイヤル インを許可し、未認証 (匿名) のユーザーがダイヤル アウト番号を使用して会議に参加できるようにするには、[**匿名の参加者によるダイヤル アウトを許可する**] チェック ボックスをオンにします。会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し会議に参加します。既定では、匿名ユーザーはダイヤル アウト番号を使用して、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="2ff26-140">[**音声ビデオ**] でビデオの使用を許可することを選択した場合は、[**複数のビデオ ストリームを許可する**] をチェックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="2ff26-141">[**共同作業データ**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="2ff26-142">共同作業データを使用できないようにするには、[**なし**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="2ff26-p110">共同作業データを許可するには、[**共同作業データの有効化**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="2ff26-145">[**共同作業データ**] で共同作業データの許可を選択した場合、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="2ff26-p111">外部ダウンロードを使用できないようにするには、[**フェデレーションと匿名の参加者によるコンテンツのダウンロードを許可する**] チェック ボックスをオフにします。既定では、外部ユーザーはコンテンツをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="2ff26-p112">ファイル転送を使用できないようにするには、[**参加者によるファイルの転送を許可する**] チェック ボックスをオフにします。既定では、ユーザーはファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="2ff26-p113">コメントを使用できないようにするには、[**コメントを有効にする**] チェック ボックスをオフにします。PowerPoint 共有プレゼンテーションでコメントを使用するには、[**PowerPoint のコメントを有効にする**] をオフにします。コメントは既定で許可されています。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p113">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="2ff26-p114">ポーリングを使用できないようにするには、[**ポーリングを有効にする**] チェック ボックスをオフにします。既定では、ポーリングは許可されます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="2ff26-155">[**アプリケーション共有**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="2ff26-156">アプリケーション共有を使用できないようにするには、[**アプリケーションの共有を無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="2ff26-p115">アプリケーション共有の使用を許可するには、[**アプリケーションの共有を有効にする**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="2ff26-159">[**アプリケーション共有**] でアプリケーション共有の許可を選択した場合、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="2ff26-p116">会議の参加者がアプリケーション共有を制御できないようにするには、[**参加者による制御を許可する**] チェック ボックスをオフにします。既定では、参加者はアプリケーション共有を制御できます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="2ff26-p117">会議の参加者によるアプリケーション共有の制御の許可を選択した場合、外部ユーザーによるアプリケーション共有の制御を許可するには、[**フェデレーションと匿名の参加者による制御を許可する**] チェック ボックスをオンにします。既定では、外部ユーザーはアプリケーション共有を制御できません。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="2ff26-164">[**参加者ポリシー**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="2ff26-165">アプリケーション共有とデスクトップ共有を両方使用できないようにするには、[**アプリケーションとデスクトップの共有を無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="2ff26-166">アプリケーション共有は許可するが、デスクトップ共有は許可しない場合は、[**アプリケーションの共有を有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="2ff26-p118">アプリケーション共有とデスクトップ共有を両方許可するには、[**アプリケーションとデスクトップの共有を有効にする**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="2ff26-p119">ピアツーピアのファイル転送を使用できないようにするには、[**ピアツーピアのファイル転送を有効にする**] チェック ボックスをオフにします。既定では、ピアツーピアのファイル転送は許可されます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="2ff26-p120">ピアツーピアのレコーディングを許可するには、[**ピアツーピアのレコーディングを有効にする**] チェック ボックスをオンにします。既定では、ピアツーピアのレコーディングは許可されません。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="2ff26-p121">参加者が複数のビデオ ストリームに参加できるようにするには、[**複数のビデオ ストリームでの参加を参加者に許可する**] チェック ボックスをオンにします。複数のビデオ ストリームは既定で許可されています。</span><span class="sxs-lookup"><span data-stu-id="2ff26-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="2ff26-175">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2ff26-176">Skype ビジネス サーバー管理シェルを使用して会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2ff26-177">電話会議ポリシーを作成するには、**New-CsConferencingPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2ff26-178">Id SalesConferencingPolicy を持つ新しい会議ポリシーを作成する例を次にします。</span><span class="sxs-lookup"><span data-stu-id="2ff26-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="2ff26-179">このポリシーは MaxMeetingSize を除き、電話会議ポリシーのすべての既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ff26-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="2ff26-180">この例では、会議の最大サイズは既定値の 250 ではなく 50 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2ff26-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="2ff26-181">詳細については、完全な構文の説明と、パラメーターの一覧を含む[新しい CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff26-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

