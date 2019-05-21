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
ms.openlocfilehash: 98dc47ec66861d2f0c77c0eff45851c09e8bc353
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33356189"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="c0170-103">Microsoft Teams での外部アクセス (フェデレーション) の管理</span><span class="sxs-lookup"><span data-stu-id="c0170-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="c0170-104">Microsoft Teams の外部アクセスを使用すると、他のドメインのユーザーがチャットや通話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="c0170-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="c0170-105">さらに、Skype for Business Online または Skype for Business オンプレミスを使用している外部ユーザーに参加を許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0170-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="c0170-106">外部アクセス (フェデレーション) とゲストアクセスの違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0170-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="c0170-107">ゲストアクセスは、個々のユーザーにアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c0170-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="c0170-108">外部アクセスは、ドメイン全体へのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c0170-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="c0170-109">ゲストアクセスはチーム所有者によって付与されると、ゲストは特定のチームのためのリソース (チャネルディスカッションやファイルなど) に[アクセス](guest-experience.md)し、招待されたチーム内の他のユーザーとチャットすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0170-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="c0170-110">外部アクセス (フェデレーションチャット) を使用している場合、外部チャット参加者は招待組織のチームまたはチームリソースにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c0170-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="c0170-111">1対1のフェデレーションチャットにのみ参加できます。</span><span class="sxs-lookup"><span data-stu-id="c0170-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="c0170-112">テナント管理者は、外部関係者に適したコラボレーションのレベルに応じて、2つの通信オプションのいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c0170-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="c0170-113">管理者は、組織のニーズに応じて、いずれか一方または両方の方法を選ぶことができますが、すべてのチームでの共同作業にゲストアクセスを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0170-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="c0170-114">外部とゲストのアクセス機能の比較については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0170-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="c0170-115">機能</span><span class="sxs-lookup"><span data-stu-id="c0170-115">Feature</span></span> | <span data-ttu-id="c0170-116">外部アクセスユーザー</span><span class="sxs-lookup"><span data-stu-id="c0170-116">External access users</span></span> | <span data-ttu-id="c0170-117">ゲストアクセスユーザー</span><span class="sxs-lookup"><span data-stu-id="c0170-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="c0170-118">ユーザーは別の会社の他のユーザーとチャットすることができます</span><span class="sxs-lookup"><span data-stu-id="c0170-118">User can chat with someone in another company</span></span> | <span data-ttu-id="c0170-119">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-119">Yes</span></span> |<span data-ttu-id="c0170-120">可</span><span class="sxs-lookup"><span data-stu-id="c0170-120">Yes</span></span> |
| <span data-ttu-id="c0170-121">ユーザーが別の会社のユーザーに電話をかけることができる</span><span class="sxs-lookup"><span data-stu-id="c0170-121">User can call someone in another company</span></span> | <span data-ttu-id="c0170-122">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-122">Yes</span></span> | <span data-ttu-id="c0170-123">可</span><span class="sxs-lookup"><span data-stu-id="c0170-123">Yes</span></span> |
| <span data-ttu-id="c0170-124">他の会社のユーザーが通話またはチャットできるかどうかを確認できる</span><span class="sxs-lookup"><span data-stu-id="c0170-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="c0170-125">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-125">Yes</span></span> | <span data-ttu-id="c0170-126">Yes<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0170-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="c0170-127">ユーザーは外部テナント全体でユーザーを検索できます</span><span class="sxs-lookup"><span data-stu-id="c0170-127">User can search for users across external tenants</span></span> | <span data-ttu-id="c0170-128">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c0170-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="c0170-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-129">No</span></span> |
| <span data-ttu-id="c0170-130">ユーザーはファイルを共有できます</span><span class="sxs-lookup"><span data-stu-id="c0170-130">User can share files</span></span> | <span data-ttu-id="c0170-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-131">No</span></span> | <span data-ttu-id="c0170-132">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-132">Yes</span></span> |
| <span data-ttu-id="c0170-133">ユーザーはチームリソースにアクセスできます</span><span class="sxs-lookup"><span data-stu-id="c0170-133">User can access Teams resources</span></span> | <span data-ttu-id="c0170-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-134">No</span></span> | <span data-ttu-id="c0170-135">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-135">Yes</span></span> |
| <span data-ttu-id="c0170-136">ユーザをグループチャットに追加できます</span><span class="sxs-lookup"><span data-stu-id="c0170-136">User can be added to a group chat</span></span> | <span data-ttu-id="c0170-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-137">No</span></span> | <span data-ttu-id="c0170-138">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-138">Yes</span></span> |
| <span data-ttu-id="c0170-139">ユーザーを会議に追加できる</span><span class="sxs-lookup"><span data-stu-id="c0170-139">User can be added to a meeting</span></span> | <span data-ttu-id="c0170-140">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-140">Yes</span></span> | <span data-ttu-id="c0170-141">可</span><span class="sxs-lookup"><span data-stu-id="c0170-141">Yes</span></span> |
| <span data-ttu-id="c0170-142">外部ユーザーとのチャットに追加のユーザーを追加できる</span><span class="sxs-lookup"><span data-stu-id="c0170-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="c0170-143">なし<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="c0170-143">No<sup>3</sup></span></span> | <span data-ttu-id="c0170-144">N/A</span><span class="sxs-lookup"><span data-stu-id="c0170-144">N/A</span></span> |
| <span data-ttu-id="c0170-145">ユーザーは外部関係者として識別される</span><span class="sxs-lookup"><span data-stu-id="c0170-145">User is identified as an external party</span></span> | <span data-ttu-id="c0170-146">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-146">Yes</span></span> | <span data-ttu-id="c0170-147">可</span><span class="sxs-lookup"><span data-stu-id="c0170-147">Yes</span></span> |
| <span data-ttu-id="c0170-148">プレゼンスが表示される</span><span class="sxs-lookup"><span data-stu-id="c0170-148">Presence is displayed</span></span> | <span data-ttu-id="c0170-149">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-149">Yes</span></span> | <span data-ttu-id="c0170-150">可</span><span class="sxs-lookup"><span data-stu-id="c0170-150">Yes</span></span> |
| <span data-ttu-id="c0170-151">不在時のメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="c0170-151">Out of office message is shown</span></span> | <span data-ttu-id="c0170-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-152">No</span></span> | <span data-ttu-id="c0170-153">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-153">Yes</span></span> |
| <span data-ttu-id="c0170-154">個々のユーザーをブロックすることができます</span><span class="sxs-lookup"><span data-stu-id="c0170-154">Individual user can be blocked</span></span> | <span data-ttu-id="c0170-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-155">No</span></span> | <span data-ttu-id="c0170-156">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-156">Yes</span></span> |
| <span data-ttu-id="c0170-157">@mentions はサポートされています</span><span class="sxs-lookup"><span data-stu-id="c0170-157">@mentions are supported</span></span> | <span data-ttu-id="c0170-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0170-158">No</span></span> | <span data-ttu-id="c0170-159">はい</span><span class="sxs-lookup"><span data-stu-id="c0170-159">Yes</span></span> |
||||

<span data-ttu-id="c0170-160"><sup>1</sup>ユーザーがゲストとして追加され、ゲストテナントにゲストとしてサインインしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c0170-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="c0170-161"><sup>2</sup>メールまたはセッションの開始プロトコル (SIP) アドレスのみ。</span><span class="sxs-lookup"><span data-stu-id="c0170-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="c0170-162"><sup>3</sup>外部 (フェデレーション) チャットは1:1 のみです。</span><span class="sxs-lookup"><span data-stu-id="c0170-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="c0170-163">外部アクセスを有効または無効にする (ユーザーは Skype for Business および Teams ユーザーと通信できます)</span><span class="sxs-lookup"><span data-stu-id="c0170-163">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="c0170-164">Microsoft Teams & Skype for Business 管理センターを使って、外部アクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c0170-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="c0170-165">Microsoft Teams & Skype for business 管理センターで、[**組織全体の設定** > ] の [**外部アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0170-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![組織全体の設定の外部アクセスのスクリーンショット](media/manage-external-access-1.png)<span data-ttu-id="c0170-167">.</span><span class="sxs-lookup"><span data-stu-id="c0170-167"></span></span>

2. <span data-ttu-id="c0170-168">ユーザーが**Skype For business および Teams ユーザーと通信できるよう**に切り替えるには、 **[オン**] または [**オフ**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c0170-168">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![外部アクセススイッチがオンになっているスクリーンショット](media/manage-external-access-2.png)<span data-ttu-id="c0170-170">.</span><span class="sxs-lookup"><span data-stu-id="c0170-170"></span></span>

3. <span data-ttu-id="c0170-171">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0170-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="c0170-172">ドメインを追加またはブロックする</span><span class="sxs-lookup"><span data-stu-id="c0170-172">Add or block a domain</span></span>

<span data-ttu-id="c0170-173">ドメインを追加する、またはドメインの外部アクセスを無効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0170-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="c0170-174">Microsoft Teams & Skype for business 管理センターで、[**組織全体の設定** > ] の [**外部アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0170-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="c0170-175">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0170-175">Select **Add a domain**.</span></span> 
 
    ![[ドメインの追加] リンクが表示された外部アクセスページのスクリーンショット](media/manage-external-access-3.png)<span data-ttu-id="c0170-177">.</span><span class="sxs-lookup"><span data-stu-id="c0170-177"></span></span>

   <span data-ttu-id="c0170-178">[**ドメインの追加**] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0170-178">The **Add a domain** pane appears.</span></span>

    ![[ドメインの追加] ウィンドウのスクリーンショット](media/manage-external-access-4.png)<span data-ttu-id="c0170-180">.</span><span class="sxs-lookup"><span data-stu-id="c0170-180"></span></span>


3. <span data-ttu-id="c0170-181">[**ドメインの追加**] で、ドメインの名前を入力します。たとえば、「Contoso.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c0170-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="c0170-182">[**許可**] または [**禁止**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0170-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="c0170-183">この設定はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="c0170-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="c0170-184">[**完了**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c0170-184">Select **Done**.</span></span>

<span data-ttu-id="c0170-185">ドメインを追加した後、[外部アクセス] ページのドメインの一覧に、[ドメイン名] と [状態] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0170-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="c0170-186">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c0170-186">More information</span></span>

<span data-ttu-id="c0170-187">Microsoft Teams のゲストアクセスの詳細については、「 [Microsoft teams でゲストアクセスを管理](manage-guests.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0170-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
