---
title: ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: 外部アクセス (フェデレーション) とゲスト アクセスを使用して、Microsoft Teams で組織外のユーザーと電話およびチャットし、ユーザーを検索および追加する方法を説明します。
ms.openlocfilehash: e3524bfeb7e21e18d0d742c7208bbe307bdd16c8
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421322"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a><span data-ttu-id="9f503-103">ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする</span><span class="sxs-lookup"><span data-stu-id="9f503-103">Use guest access and external access to collaborate with people outside your organization</span></span>

<span data-ttu-id="9f503-104">組織外のユーザーとコミュニケーションや共同作業を行う必要がある場合、Microsoft Teams には次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="9f503-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="9f503-105">**外部アクセス** - ユーザーが他の組織のユーザーを検索、通話、およびチャットできるようにするフェデレーションの一種です。</span><span class="sxs-lookup"><span data-stu-id="9f503-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="9f503-106">これらのユーザーは、ゲストとして招待されない限り、チームに追加できません。</span><span class="sxs-lookup"><span data-stu-id="9f503-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="9f503-107">**ゲスト アクセス** - ゲスト アクセスでは、組織外のユーザーをチームに招待できます。</span><span class="sxs-lookup"><span data-stu-id="9f503-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="9f503-108">招待されたユーザーは、Azure Active Directory でゲスト アカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f503-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="9f503-109">Teams を使用すると、組織外のユーザーを会議に招待できます。</span><span class="sxs-lookup"><span data-stu-id="9f503-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="9f503-110">これには、外部アクセスまたはゲスト アクセスを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9f503-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="9f503-111">外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="9f503-111">External access (federation)</span></span>

<span data-ttu-id="9f503-112">Teams、Skype for Business (オンラインまたはオンプレミス)、Skype を使用する組織外のユーザーを検索、電話、チャット、および会議を設定する必要がある場合は、外部アクセスを設定します。</span><span class="sxs-lookup"><span data-stu-id="9f503-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="9f503-113">既定では、すべてのドメインに対して外部アクセスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9f503-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="9f503-114">外部アクセスを制限するには、特定のドメインを許可またはブロックするか、またはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9f503-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![外部アクセス設定のスクリーンショット](media/external-access-federation-settings.png)

<span data-ttu-id="9f503-116">外部アクセスを構成するには、「[外部アクセスの管理](manage-external-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f503-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

## <a name="guest-access"></a><span data-ttu-id="9f503-117">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="9f503-117">Guest access</span></span>

<span data-ttu-id="9f503-118">ゲスト アクセスを使用して、チャット、通話、会議、およびファイル上での共同作業が可能な、組織外のユーザーをチームに追加します。</span><span class="sxs-lookup"><span data-stu-id="9f503-118">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="9f503-119">ゲストには、ネイティブ チーム メンバーとほぼ同じ Teams 機能を使用できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="9f503-119">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="9f503-120">ゲストは組織の Azure Active Directory に B2B ユーザーとして追加され、ゲスト アカウントを使用して Teams にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f503-120">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="9f503-121">つまり、ゲストがお客様の組織にサインインするには、ゲスト自身の組織からサインアウトする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f503-121">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="9f503-122">Teams のゲスト アクセスを構成する方法については、「[チームでゲストと共同作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f503-122">To configure guest access for Teams, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="9f503-123">外部アクセスとゲスト アクセスの比較</span><span class="sxs-lookup"><span data-stu-id="9f503-123">Compare external and guest access</span></span>

<span data-ttu-id="9f503-124">次の表に、外部アクセス (フェデレーション) とゲストの使用の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="9f503-124">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="9f503-125">いずれの場合も、組織外のユーザーは外部のユーザーとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="9f503-125">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="9f503-126">ユーザーが実行できる操作</span><span class="sxs-lookup"><span data-stu-id="9f503-126">Things your users can do</span></span>

| <span data-ttu-id="9f503-127">ユーザーは、次のことを実行できます</span><span class="sxs-lookup"><span data-stu-id="9f503-127">Users can</span></span> | <span data-ttu-id="9f503-128">外部アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="9f503-128">External access users</span></span> | <span data-ttu-id="9f503-129">ゲスト</span><span class="sxs-lookup"><span data-stu-id="9f503-129">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="9f503-130">別の組織のユーザーとチャットする</span><span class="sxs-lookup"><span data-stu-id="9f503-130">Chat with someone in another organization</span></span> | <span data-ttu-id="9f503-131">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-131">Yes</span></span> | <span data-ttu-id="9f503-132">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-132">Yes</span></span> |
| <span data-ttu-id="9f503-133">別の組織のユーザーに電話をかける</span><span class="sxs-lookup"><span data-stu-id="9f503-133">Call someone in another organization</span></span> | <span data-ttu-id="9f503-134">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-134">Yes</span></span> | <span data-ttu-id="9f503-135">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-135">Yes</span></span> |
| <span data-ttu-id="9f503-136">別の組織のユーザーが通話またはチャットできるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="9f503-136">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="9f503-137">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-137">Yes</span></span> | <span data-ttu-id="9f503-138">はい<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-138">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="9f503-139">別の組織内のユーザーを検索する</span><span class="sxs-lookup"><span data-stu-id="9f503-139">Search for people in other organizations</span></span> | <span data-ttu-id="9f503-140">はい<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-140">Yes<sup>2</sup></span></span> | <span data-ttu-id="9f503-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-141">No</span></span> |
| <span data-ttu-id="9f503-142">ファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="9f503-142">Share files</span></span> | <span data-ttu-id="9f503-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-143">No</span></span> | <span data-ttu-id="9f503-144">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-144">Yes</span></span> |
| <span data-ttu-id="9f503-145">不在メッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="9f503-145">See the out-of-office message of</span></span> | <span data-ttu-id="9f503-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-146">No</span></span> | <span data-ttu-id="9f503-147">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-147">Yes</span></span> |
| <span data-ttu-id="9f503-148">別の組織のユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="9f503-148">Block someone in another organization someone in another organization</span></span> | <span data-ttu-id="9f503-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-149">No</span></span> | <span data-ttu-id="9f503-150">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-150">Yes</span></span> |
| <span data-ttu-id="9f503-151">@メンションを使用する</span><span class="sxs-lookup"><span data-stu-id="9f503-151">Use @mentions</span></span> | <span data-ttu-id="9f503-152">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-152">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-153">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-153">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="9f503-154">組織外のユーザーが実行できる操作</span><span class="sxs-lookup"><span data-stu-id="9f503-154">Things people outside your organization can do</span></span>

| <span data-ttu-id="9f503-155">組織外のユーザーは、次のことを実行できます</span><span class="sxs-lookup"><span data-stu-id="9f503-155">People outside your organization can</span></span> | <span data-ttu-id="9f503-156">外部アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="9f503-156">External access users</span></span> | <span data-ttu-id="9f503-157">ゲスト</span><span class="sxs-lookup"><span data-stu-id="9f503-157">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="9f503-158">Teams のリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="9f503-158">Access Teams resources</span></span> | <span data-ttu-id="9f503-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-159">No</span></span> | <span data-ttu-id="9f503-160">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-160">Yes</span></span> |
| <span data-ttu-id="9f503-161">グループ チャットに追加される</span><span class="sxs-lookup"><span data-stu-id="9f503-161">Be added to a group chat</span></span> | <span data-ttu-id="9f503-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-162">No</span></span> | <span data-ttu-id="9f503-163">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-163">Yes</span></span> |
| <span data-ttu-id="9f503-164">会議に招待される</span><span class="sxs-lookup"><span data-stu-id="9f503-164">Be invited to a meeting</span></span> | <span data-ttu-id="9f503-165">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-165">Yes</span></span> | <span data-ttu-id="9f503-166">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-166">Yes</span></span> |
| <span data-ttu-id="9f503-167">プライベート通話をする</span><span class="sxs-lookup"><span data-stu-id="9f503-167">Make private calls</span></span> | <span data-ttu-id="9f503-168">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-168">Yes</span></span> | <span data-ttu-id="9f503-169">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-169">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-170">ダイヤルイン会議の参加者の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="9f503-170">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="9f503-171">いいえ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-171">No<sup>4</sup></span></span> | <span data-ttu-id="9f503-172">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-172">Yes</span></span> |
| <span data-ttu-id="9f503-173">IP ビデオを使う</span><span class="sxs-lookup"><span data-stu-id="9f503-173">Use IP video</span></span> | <span data-ttu-id="9f503-174">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-174">Yes</span></span> | <span data-ttu-id="9f503-175">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-175">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-176">画面共有を使う</span><span class="sxs-lookup"><span data-stu-id="9f503-176">Use screen sharing</span></span> | <span data-ttu-id="9f503-177">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-177">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-178">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-178">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-179">今すぐ会議を使う</span><span class="sxs-lookup"><span data-stu-id="9f503-179">Use meet now</span></span> | <span data-ttu-id="9f503-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f503-180">No</span></span> | <span data-ttu-id="9f503-181">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-181">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-182">送信済みメッセージを編集する</span><span class="sxs-lookup"><span data-stu-id="9f503-182">Edit sent messages</span></span> | <span data-ttu-id="9f503-183">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-183">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-184">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-184">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-185">送信済みメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="9f503-185">Delete sent messages</span></span> | <span data-ttu-id="9f503-186">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-186">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-187">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-187">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-188">会話で Giphy を使用する</span><span class="sxs-lookup"><span data-stu-id="9f503-188">Use Giphy in conversation</span></span> | <span data-ttu-id="9f503-189">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-189">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-190">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-190">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-191">会話でミームを使用する</span><span class="sxs-lookup"><span data-stu-id="9f503-191">Use memes in conversation</span></span> | <span data-ttu-id="9f503-192">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-192">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-193">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-193">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-194">会話でステッカーを使用する</span><span class="sxs-lookup"><span data-stu-id="9f503-194">Use stickers in conversation</span></span> | <span data-ttu-id="9f503-195">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-195">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-196">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-196">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="9f503-197">プレゼンスが表示される</span><span class="sxs-lookup"><span data-stu-id="9f503-197">Presence is displayed</span></span> | <span data-ttu-id="9f503-198">Yes</span><span class="sxs-lookup"><span data-stu-id="9f503-198">Yes</span></span> | <span data-ttu-id="9f503-199">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-199">Yes</span></span> |
| <span data-ttu-id="9f503-200">@メンションを使用する</span><span class="sxs-lookup"><span data-stu-id="9f503-200">Use @mentions</span></span> | <span data-ttu-id="9f503-201">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9f503-201">Yes<sup>3</sup></span></span> | <span data-ttu-id="9f503-202">はい</span><span class="sxs-lookup"><span data-stu-id="9f503-202">Yes</span></span> |

<br>

<span data-ttu-id="9f503-203"><sup>1</sup> ユーザーがゲストとして追加され、ゲスト アカウントでサインインされている場合。</span><span class="sxs-lookup"><span data-stu-id="9f503-203"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="9f503-204"><sup>2</sup> メールまたはセッション開始プロトコル (SIP) アドレスのみ。</span><span class="sxs-lookup"><span data-stu-id="9f503-204"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="9f503-205"><sup>3</sup> 2 つの異なる組織の Teams のみユーザーの Teams のみの 1:1 チャットでサポートされる。</span><span class="sxs-lookup"><span data-stu-id="9f503-205"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="9f503-206"><sup>4</sup> 既定では、外部ユーザーはダイヤル インした参加者の電話番号は見ることができません。</span><span class="sxs-lookup"><span data-stu-id="9f503-206"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="9f503-207">これらの電話番号のプライバシーを維持したい場合は、**開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。</span><span class="sxs-lookup"><span data-stu-id="9f503-207">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="9f503-208">詳細については、「[Microsoft Teams で会議の入退室通知をオンまたはオフにする](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f503-208">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="9f503-209"><sup>5</sup> 既定で許可されていますが、Teams 管理者がオフにすることができます</span><span class="sxs-lookup"><span data-stu-id="9f503-209"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f503-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f503-210">Related topics</span></span>

[<span data-ttu-id="9f503-211">Teams での外部アクセス</span><span class="sxs-lookup"><span data-stu-id="9f503-211">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="9f503-212">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="9f503-212">Guest access in Teams</span></span>](guest-access.md)

