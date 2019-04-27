---
title: Microsoft Teams での外部アクセス (フェデレーション) の管理
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: IT 管理者は、これらのドメインからのユーザーがチームに参加できるようにするのには他のドメイン (フェデレーション) の外部アクセスを構成できます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98dc47ec66861d2f0c77c0eff45851c09e8bc353
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33356189"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="05bfe-103">Microsoft Teams での外部アクセス (フェデレーション) の管理</span><span class="sxs-lookup"><span data-stu-id="05bfe-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="05bfe-104">マイクロソフト チームの外部アクセス、他のドメインからのユーザーのチャットと通話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="05bfe-105">外部のユーザーもを使用している Skype のオンライン ビジネスやビジネス上の prem の Skype への参加を許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="05bfe-106">(フェデレーション) の外部アクセスおよびゲスト アクセスは、異なります。</span><span class="sxs-lookup"><span data-stu-id="05bfe-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="05bfe-107">ゲスト アクセスは、個々 のアクセスのアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="05bfe-108">外部からのアクセスは、ドメイン全体へのアクセス許可を示します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="05bfe-109">特定のチームと他のユーザーに招待されているチームでのチャットなどの[リソースへのアクセス](guest-experience.md)、チャネルのディスカッション、およびファイルへのゲストは、ゲスト アクセス、1 回、チームの所有者によって与えられているができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="05bfe-110">外部アクセス (連合チャット)、外部のチャットに参加しての招待側の組織のチームまたはチームのリソースへのアクセスはあるないです。</span><span class="sxs-lookup"><span data-stu-id="05bfe-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="05bfe-111">連合の 1 対 1 のチャットに参加できるだけです。</span><span class="sxs-lookup"><span data-stu-id="05bfe-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="05bfe-112">テナント管理者は、コラボレーションのレベルによっては、外部の関係者に望ましい通信の 2 つのオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="05bfe-113">アプローチまたはその両方の組織のニーズに応じて管理者が選択できますが、詳細、共同作業によるチームの経験のゲスト アクセスを有効にすることをお勧めです。</span><span class="sxs-lookup"><span data-stu-id="05bfe-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="05bfe-114">テーブル外部の比較については、以下の機能にアクセスするゲストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05bfe-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="05bfe-115">機能</span><span class="sxs-lookup"><span data-stu-id="05bfe-115">Feature</span></span> | <span data-ttu-id="05bfe-116">外部アクセスのユーザー</span><span class="sxs-lookup"><span data-stu-id="05bfe-116">External access users</span></span> | <span data-ttu-id="05bfe-117">ゲスト アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="05bfe-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="05bfe-118">ユーザーが別の会社で他の人とチャットできます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-118">User can chat with someone in another company</span></span> | <span data-ttu-id="05bfe-119">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-119">Yes</span></span> |<span data-ttu-id="05bfe-120">可</span><span class="sxs-lookup"><span data-stu-id="05bfe-120">Yes</span></span> |
| <span data-ttu-id="05bfe-121">ユーザーは別の会社で他の人を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-121">User can call someone in another company</span></span> | <span data-ttu-id="05bfe-122">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-122">Yes</span></span> | <span data-ttu-id="05bfe-123">可</span><span class="sxs-lookup"><span data-stu-id="05bfe-123">Yes</span></span> |
| <span data-ttu-id="05bfe-124">ユーザーが通話やチャットを利用可能な別の会社から誰かが確認できます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="05bfe-125">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-125">Yes</span></span> | <span data-ttu-id="05bfe-126">Yes<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="05bfe-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="05bfe-127">ユーザーは、外部のテナント間でユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-127">User can search for users across external tenants</span></span> | <span data-ttu-id="05bfe-128">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="05bfe-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="05bfe-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-129">No</span></span> |
| <span data-ttu-id="05bfe-130">ユーザーがファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-130">User can share files</span></span> | <span data-ttu-id="05bfe-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-131">No</span></span> | <span data-ttu-id="05bfe-132">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-132">Yes</span></span> |
| <span data-ttu-id="05bfe-133">ユーザーがチーム リソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-133">User can access Teams resources</span></span> | <span data-ttu-id="05bfe-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-134">No</span></span> | <span data-ttu-id="05bfe-135">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-135">Yes</span></span> |
| <span data-ttu-id="05bfe-136">ユーザーは、グループ チャットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-136">User can be added to a group chat</span></span> | <span data-ttu-id="05bfe-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-137">No</span></span> | <span data-ttu-id="05bfe-138">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-138">Yes</span></span> |
| <span data-ttu-id="05bfe-139">会議にユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-139">User can be added to a meeting</span></span> | <span data-ttu-id="05bfe-140">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-140">Yes</span></span> | <span data-ttu-id="05bfe-141">可</span><span class="sxs-lookup"><span data-stu-id="05bfe-141">Yes</span></span> |
| <span data-ttu-id="05bfe-142">外部のユーザーにチャットに他のユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="05bfe-143">なし<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="05bfe-143">No<sup>3</sup></span></span> | <span data-ttu-id="05bfe-144">N/A</span><span class="sxs-lookup"><span data-stu-id="05bfe-144">N/A</span></span> |
| <span data-ttu-id="05bfe-145">ユーザーが外部の関係者として識別されます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-145">User is identified as an external party</span></span> | <span data-ttu-id="05bfe-146">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-146">Yes</span></span> | <span data-ttu-id="05bfe-147">可</span><span class="sxs-lookup"><span data-stu-id="05bfe-147">Yes</span></span> |
| <span data-ttu-id="05bfe-148">プレゼンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-148">Presence is displayed</span></span> | <span data-ttu-id="05bfe-149">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-149">Yes</span></span> | <span data-ttu-id="05bfe-150">可</span><span class="sxs-lookup"><span data-stu-id="05bfe-150">Yes</span></span> |
| <span data-ttu-id="05bfe-151">不在時メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-151">Out of office message is shown</span></span> | <span data-ttu-id="05bfe-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-152">No</span></span> | <span data-ttu-id="05bfe-153">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-153">Yes</span></span> |
| <span data-ttu-id="05bfe-154">個々 のユーザーをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-154">Individual user can be blocked</span></span> | <span data-ttu-id="05bfe-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-155">No</span></span> | <span data-ttu-id="05bfe-156">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-156">Yes</span></span> |
| <span data-ttu-id="05bfe-157">@mentions がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="05bfe-157">@mentions are supported</span></span> | <span data-ttu-id="05bfe-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="05bfe-158">No</span></span> | <span data-ttu-id="05bfe-159">はい</span><span class="sxs-lookup"><span data-stu-id="05bfe-159">Yes</span></span> |
||||

<span data-ttu-id="05bfe-160"><sup>1</sup>は、ユーザーがゲストとして追加されているし、ゲストのテナントにゲストとしてサインインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="05bfe-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="05bfe-161"><sup>2</sup>のみ、電子メール、またはセッション開始プロトコル (SIP) アドレスです。</span><span class="sxs-lookup"><span data-stu-id="05bfe-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="05bfe-162"><sup>3</sup> (連合) の外部のチャットは、1 対 1 のみです。</span><span class="sxs-lookup"><span data-stu-id="05bfe-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="05bfe-163">有効にするか (企業やチームのユーザーが Skype で通信できるように) 外部からのアクセスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="05bfe-163">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="05bfe-164">マイクロソフト チーム & Skype ビジネス管理センターの外部からのアクセスを管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="05bfe-165">マイクロソフトのチームの & ビジネス管理センターの Skype では、**組織全体の設定**を選択します。 > **外部からアクセス**します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![組織全体にわたる設定の外部アクセスのスクリーン ショット](media/manage-external-access-1.png)<span data-ttu-id="05bfe-167">.</span><span class="sxs-lookup"><span data-stu-id="05bfe-167"></span></span>

2. <span data-ttu-id="05bfe-168">**ユーザーが企業やチームの Skype で通信できるように**スイッチを**オン**または**オフ**を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-168">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![外部アクセス スイッチをオンのスクリーン ショット](media/manage-external-access-2.png)<span data-ttu-id="05bfe-170">.</span><span class="sxs-lookup"><span data-stu-id="05bfe-170"></span></span>

3. <span data-ttu-id="05bfe-171">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05bfe-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="05bfe-172">追加またはドメインをブロックします。</span><span class="sxs-lookup"><span data-stu-id="05bfe-172">Add or block a domain</span></span>

<span data-ttu-id="05bfe-173">ドメインを追加またはドメインの外部のアクセスを無効にするこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="05bfe-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="05bfe-174">マイクロソフトのチームの & ビジネス管理センターの Skype では、**組織全体の設定**を選択します。 > **外部からアクセス**します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="05bfe-175">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-175">Select **Add a domain**.</span></span> 
 
    ![スクリーン ショットの外部アクセスのページでは、ドメインのリンクを追加します。](media/manage-external-access-3.png)<span data-ttu-id="05bfe-177">.</span><span class="sxs-lookup"><span data-stu-id="05bfe-177"></span></span>

   <span data-ttu-id="05bfe-178">**ドメインの追加**] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-178">The **Add a domain** pane appears.</span></span>

    ![追加ドメイン ウィンドウのスクリーン ショット](media/manage-external-access-4.png)<span data-ttu-id="05bfe-180">.</span><span class="sxs-lookup"><span data-stu-id="05bfe-180"></span></span>


3. <span data-ttu-id="05bfe-181">[**ドメインの追加**] で、ドメインの名前を入力しますたとえば、Contoso.com を入力します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="05bfe-182">[**許可**] または [**禁止**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="05bfe-183">いつでもこの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="05bfe-184">**実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="05bfe-184">Select **Done**.</span></span>

<span data-ttu-id="05bfe-185">ドメインを追加すると、ドメイン名] と [外部アクセス] ページで、ドメインの一覧に追加のステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05bfe-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="05bfe-186">詳細情報</span><span class="sxs-lookup"><span data-stu-id="05bfe-186">More information</span></span>

<span data-ttu-id="05bfe-187">マイクロソフトのチームでのゲスト アクセスの詳細については、[マイクロソフトのチームでのゲスト アクセスの管理](manage-guests.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05bfe-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
