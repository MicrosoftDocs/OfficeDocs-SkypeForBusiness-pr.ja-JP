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
description: IT 管理者は、他のドメインの外部アクセス (フェデレーション) を構成して、これらのドメインのユーザーが Teams に参加できるようにすることができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702721"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="c2a9d-103">Microsoft Teams での外部アクセス (フェデレーション) の管理</span><span class="sxs-lookup"><span data-stu-id="c2a9d-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="c2a9d-104">Microsoft Teams の外部アクセスを使用すると、他のドメインのユーザーがチャットや通話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="c2a9d-105">さらに、Skype for Business Online または Skype for Business オンプレミスを使用している外部ユーザーに参加を許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="c2a9d-106">外部アクセス (フェデレーション) とゲストアクセスの違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="c2a9d-107">ゲストアクセスは、個々のユーザーにアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="c2a9d-108">外部アクセスは、ドメイン全体へのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="c2a9d-109">ゲストアクセスはチーム所有者によって付与されると、ゲストは特定のチームのためのリソース (チャネルディスカッションやファイルなど) に[アクセス](guest-experience.md)し、招待されたチーム内の他のユーザーとチャットすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="c2a9d-110">外部アクセス (フェデレーションチャット) を使用している場合、外部チャット参加者は招待組織のチームまたはチームリソースにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="c2a9d-111">1対1のフェデレーションチャットにのみ参加できます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="c2a9d-112">テナント管理者は、外部関係者に適したコラボレーションのレベルに応じて、2つの通信オプションのいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="c2a9d-113">管理者は、組織のニーズに応じて、いずれか一方または両方の方法を選ぶことができますが、すべてのチームでの共同作業にゲストアクセスを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="c2a9d-114">外部とゲストのアクセス機能の比較については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="c2a9d-115">機能</span><span class="sxs-lookup"><span data-stu-id="c2a9d-115">Feature</span></span> | <span data-ttu-id="c2a9d-116">外部アクセスユーザー</span><span class="sxs-lookup"><span data-stu-id="c2a9d-116">External access users</span></span> | <span data-ttu-id="c2a9d-117">ゲストアクセスユーザー</span><span class="sxs-lookup"><span data-stu-id="c2a9d-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="c2a9d-118">ユーザーは別の会社の他のユーザーとチャットすることができます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-118">User can chat with someone in another company</span></span> | <span data-ttu-id="c2a9d-119">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-119">Yes</span></span> |<span data-ttu-id="c2a9d-120">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-120">Yes</span></span> |
| <span data-ttu-id="c2a9d-121">ユーザーが別の会社のユーザーに電話をかけることができる</span><span class="sxs-lookup"><span data-stu-id="c2a9d-121">User can call someone in another company</span></span> | <span data-ttu-id="c2a9d-122">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-122">Yes</span></span> | <span data-ttu-id="c2a9d-123">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-123">Yes</span></span> |
| <span data-ttu-id="c2a9d-124">他の会社のユーザーが通話またはチャットできるかどうかを確認できる</span><span class="sxs-lookup"><span data-stu-id="c2a9d-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="c2a9d-125">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-125">Yes</span></span> | <span data-ttu-id="c2a9d-126">Yes<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c2a9d-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="c2a9d-127">ユーザーは外部テナント全体でユーザーを検索できます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-127">User can search for users across external tenants</span></span> | <span data-ttu-id="c2a9d-128">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c2a9d-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="c2a9d-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-129">No</span></span> |
| <span data-ttu-id="c2a9d-130">ユーザーはファイルを共有できます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-130">User can share files</span></span> | <span data-ttu-id="c2a9d-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-131">No</span></span> | <span data-ttu-id="c2a9d-132">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-132">Yes</span></span> |
| <span data-ttu-id="c2a9d-133">ユーザーはチームリソースにアクセスできます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-133">User can access Teams resources</span></span> | <span data-ttu-id="c2a9d-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-134">No</span></span> | <span data-ttu-id="c2a9d-135">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-135">Yes</span></span> |
| <span data-ttu-id="c2a9d-136">ユーザをグループチャットに追加できます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-136">User can be added to a group chat</span></span> | <span data-ttu-id="c2a9d-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-137">No</span></span> | <span data-ttu-id="c2a9d-138">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-138">Yes</span></span> |
| <span data-ttu-id="c2a9d-139">ユーザーを会議に追加できる</span><span class="sxs-lookup"><span data-stu-id="c2a9d-139">User can be added to a meeting</span></span> | <span data-ttu-id="c2a9d-140">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-140">Yes</span></span> | <span data-ttu-id="c2a9d-141">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-141">Yes</span></span> |
| <span data-ttu-id="c2a9d-142">外部ユーザーとのチャットに追加のユーザーを追加できる</span><span class="sxs-lookup"><span data-stu-id="c2a9d-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="c2a9d-143">なし<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="c2a9d-143">No<sup>3</sup></span></span> | <span data-ttu-id="c2a9d-144">N/A</span><span class="sxs-lookup"><span data-stu-id="c2a9d-144">N/A</span></span> |
| <span data-ttu-id="c2a9d-145">ユーザーは外部関係者として識別される</span><span class="sxs-lookup"><span data-stu-id="c2a9d-145">User is identified as an external party</span></span> | <span data-ttu-id="c2a9d-146">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-146">Yes</span></span> | <span data-ttu-id="c2a9d-147">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-147">Yes</span></span> |
| <span data-ttu-id="c2a9d-148">プレゼンスが表示される</span><span class="sxs-lookup"><span data-stu-id="c2a9d-148">Presence is displayed</span></span> | <span data-ttu-id="c2a9d-149">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-149">Yes</span></span> | <span data-ttu-id="c2a9d-150">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-150">Yes</span></span> |
| <span data-ttu-id="c2a9d-151">不在時のメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="c2a9d-151">Out of office message is shown</span></span> | <span data-ttu-id="c2a9d-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-152">No</span></span> | <span data-ttu-id="c2a9d-153">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-153">Yes</span></span> |
| <span data-ttu-id="c2a9d-154">個々のユーザーをブロックすることができます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-154">Individual user can be blocked</span></span> | <span data-ttu-id="c2a9d-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-155">No</span></span> | <span data-ttu-id="c2a9d-156">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-156">Yes</span></span> |
| <span data-ttu-id="c2a9d-157">@mentions はサポートされています</span><span class="sxs-lookup"><span data-stu-id="c2a9d-157">@mentions are supported</span></span> | <span data-ttu-id="c2a9d-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-158">No</span></span> | <span data-ttu-id="c2a9d-159">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-159">Yes</span></span> |
| <span data-ttu-id="c2a9d-160">プライベート通話を行う</span><span class="sxs-lookup"><span data-stu-id="c2a9d-160">Make Private Calls</span></span> | <span data-ttu-id="c2a9d-161">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-161">Yes</span></span> | <span data-ttu-id="c2a9d-162">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-162">Yes</span></span> |
| <span data-ttu-id="c2a9d-163">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="c2a9d-163">Allow IP Video</span></span> | <span data-ttu-id="c2a9d-164">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-164">Yes</span></span> | <span data-ttu-id="c2a9d-165">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-165">Yes</span></span> |
| <span data-ttu-id="c2a9d-166">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="c2a9d-166">Screen Sharing Mode</span></span> | <span data-ttu-id="c2a9d-167">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-167">Yes</span></span> | <span data-ttu-id="c2a9d-168">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-168">Yes</span></span> |
| <span data-ttu-id="c2a9d-169">今すぐ会議を許可する</span><span class="sxs-lookup"><span data-stu-id="c2a9d-169">Allow Meet Now</span></span> | <span data-ttu-id="c2a9d-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2a9d-170">No</span></span> | <span data-ttu-id="c2a9d-171">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-171">Yes</span></span> |
| <span data-ttu-id="c2a9d-172">送信済みメッセージを編集する</span><span class="sxs-lookup"><span data-stu-id="c2a9d-172">Edit Sent Messages</span></span> | <span data-ttu-id="c2a9d-173">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-173">Yes</span></span> | <span data-ttu-id="c2a9d-174">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-174">Yes</span></span> |
| <span data-ttu-id="c2a9d-175">送信したメッセージを削除できます</span><span class="sxs-lookup"><span data-stu-id="c2a9d-175">Can Delete Sent Messages</span></span> | <span data-ttu-id="c2a9d-176">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-176">Yes</span></span> | <span data-ttu-id="c2a9d-177">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-177">Yes</span></span> |
| <span data-ttu-id="c2a9d-178">会話で Giphy を使う</span><span class="sxs-lookup"><span data-stu-id="c2a9d-178">Use Giphy In Conversation</span></span> | <span data-ttu-id="c2a9d-179">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-179">Yes</span></span> | <span data-ttu-id="c2a9d-180">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-180">Yes</span></span> |
| <span data-ttu-id="c2a9d-181">スレッドで Memes を使う</span><span class="sxs-lookup"><span data-stu-id="c2a9d-181">Use Memes In Conversation</span></span> | <span data-ttu-id="c2a9d-182">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-182">Yes</span></span> | <span data-ttu-id="c2a9d-183">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-183">Yes</span></span> |
| <span data-ttu-id="c2a9d-184">会話でステッカーを使用する</span><span class="sxs-lookup"><span data-stu-id="c2a9d-184">Use Stickers In Conversation</span></span> | <span data-ttu-id="c2a9d-185">はい</span><span class="sxs-lookup"><span data-stu-id="c2a9d-185">Yes</span></span> | <span data-ttu-id="c2a9d-186">可</span><span class="sxs-lookup"><span data-stu-id="c2a9d-186">Yes</span></span> |
||||

<span data-ttu-id="c2a9d-187"><sup>1</sup>ユーザーがゲストとして追加され、ゲストテナントにゲストとしてサインインしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-187"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="c2a9d-188"><sup>2</sup>メールまたはセッションの開始プロトコル (SIP) アドレスのみ。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-188"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="c2a9d-189"><sup>3</sup>外部 (フェデレーション) チャットは1:1 のみです。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-189"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

> [!NOTE]
> <span data-ttu-id="c2a9d-190">ゲスト機能とゲストエクスペリエンスの詳細については、「 [Microsoft Teams へのゲストアクセスを有効または無効にする](https://docs.microsoft.com/microsoftteams/set-up-guests)」および「[ゲストエクスペリエンスの概要](https://docs.microsoft.com/microsoftteams/guest-experience)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-190">For more information on guest features and the guest experience, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) and [What the guest experience is like](https://docs.microsoft.com/microsoftteams/guest-experience).</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="c2a9d-191">外部アクセスを有効または無効にする (ユーザーは Skype for Business および Teams ユーザーと通信できます)</span><span class="sxs-lookup"><span data-stu-id="c2a9d-191">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="c2a9d-192">Microsoft Teams & Skype for Business 管理センターを使用して、外部アクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-192">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="c2a9d-193">Microsoft Teams & Skype for business 管理センターで、[**組織全体の設定** > ] の [**外部アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-193">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![組織全体の設定の外部アクセスのスクリーンショット](media/manage-external-access-1.png)<span data-ttu-id="c2a9d-195">.</span><span class="sxs-lookup"><span data-stu-id="c2a9d-195"></span></span>

2. <span data-ttu-id="c2a9d-196">ユーザーが**Skype For business および Teams ユーザーと通信できるよう**に切り替えるには、 **[オン**] または [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-196">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![外部アクセススイッチがオンになっているスクリーンショット](media/manage-external-access-2.png)<span data-ttu-id="c2a9d-198">.</span><span class="sxs-lookup"><span data-stu-id="c2a9d-198"></span></span>

3. <span data-ttu-id="c2a9d-199">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-199">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="c2a9d-200">ドメインを追加またはブロックする</span><span class="sxs-lookup"><span data-stu-id="c2a9d-200">Add or block a domain</span></span>

<span data-ttu-id="c2a9d-201">ドメインを追加する、またはドメインの外部アクセスを無効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-201">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="c2a9d-202">Microsoft Teams & Skype for business 管理センターで、[**組織全体の設定** > ] の [**外部アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-202">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="c2a9d-203">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-203">Select **Add a domain**.</span></span> 
 
    ![[ドメインの追加] リンクが表示された外部アクセスページのスクリーンショット](media/manage-external-access-3.png)<span data-ttu-id="c2a9d-205">.</span><span class="sxs-lookup"><span data-stu-id="c2a9d-205"></span></span>

   <span data-ttu-id="c2a9d-206">[**ドメインの追加**] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-206">The **Add a domain** pane appears.</span></span>

    ![[ドメインの追加] ウィンドウのスクリーンショット](media/manage-external-access-4.png)<span data-ttu-id="c2a9d-208">.</span><span class="sxs-lookup"><span data-stu-id="c2a9d-208"></span></span>


3. <span data-ttu-id="c2a9d-209">[**ドメインの追加**] で、ドメインの名前を入力します。たとえば、「Contoso.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-209">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="c2a9d-210">[**許可**] または [**禁止**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-210">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="c2a9d-211">この設定はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-211">You can change this setting at any time.</span></span>

2. <span data-ttu-id="c2a9d-212">[**完了**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-212">Select **Done**.</span></span>

<span data-ttu-id="c2a9d-213">ドメインを追加した後、[外部アクセス] ページのドメインの一覧に、[ドメイン名] と [状態] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-213">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="c2a9d-214">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c2a9d-214">More information</span></span>

<span data-ttu-id="c2a9d-215">Microsoft Teams のゲストアクセスの詳細については、「 [Microsoft teams でゲストアクセスを管理](manage-guests.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2a9d-215">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
