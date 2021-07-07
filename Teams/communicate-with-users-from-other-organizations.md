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
ms.openlocfilehash: bda5652aedd8d071984334a3851e50ba52400943
ms.sourcegitcommit: 89e26d9ffca180e56233984bf0a341b3c3ec7208
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2021
ms.locfileid: "53302002"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a><span data-ttu-id="ed788-103">ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする</span><span class="sxs-lookup"><span data-stu-id="ed788-103">Use guest access and external access to collaborate with people outside your organization</span></span>

<span data-ttu-id="ed788-104">組織外のユーザーとコミュニケーションや共同作業を行う必要がある場合、Microsoft Teams には次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ed788-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="ed788-105">**外部アクセス** - ユーザーが他の組織のユーザーを検索、通話、およびチャットできるようにするフェデレーションの一種です。</span><span class="sxs-lookup"><span data-stu-id="ed788-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="ed788-106">これらのユーザーは、ゲストとして招待されない限り、チームに追加できません。</span><span class="sxs-lookup"><span data-stu-id="ed788-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="ed788-107">**ゲスト アクセス** - ゲスト アクセスでは、組織外のユーザーをチームに招待できます。</span><span class="sxs-lookup"><span data-stu-id="ed788-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="ed788-108">招待されたユーザーは、Azure Active Directory でゲスト アカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="ed788-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="ed788-109">Teams を使用すると、組織外のユーザーを会議に招待できます。</span><span class="sxs-lookup"><span data-stu-id="ed788-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="ed788-110">これには、外部アクセスまたはゲスト アクセスを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed788-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="ed788-111">外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="ed788-111">External access (federation)</span></span>

<span data-ttu-id="ed788-112">Teams、Skype for Business (オンラインまたはオンプレミス)、Skype を使用する組織外のユーザーを検索、電話、チャット、および会議を設定する必要がある場合は、外部アクセスを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed788-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="ed788-113">既定では、すべてのドメインに対して外部アクセスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ed788-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="ed788-114">外部アクセスを制限するには、特定のドメインを許可またはブロックするか、またはオフにします。</span><span class="sxs-lookup"><span data-stu-id="ed788-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![外部アクセス設定のスクリーンショット](media/external-access-federation-settings.png)

<span data-ttu-id="ed788-116">外部アクセスを構成するには、「[外部アクセスの管理](manage-external-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed788-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

>[!NOTE]
><span data-ttu-id="ed788-117">Microsoft Teams の無料ライセンスでは、外部アクセスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ed788-117">Microsoft Teams free licenses do not support external access.</span></span>

## <a name="guest-access"></a><span data-ttu-id="ed788-118">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="ed788-118">Guest access</span></span>

<span data-ttu-id="ed788-119">ゲスト アクセスを使用して、チャット、通話、会議、およびファイル上での共同作業が可能な、組織外のユーザーをチームに追加します。</span><span class="sxs-lookup"><span data-stu-id="ed788-119">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="ed788-120">ゲストには、ネイティブ チーム メンバーとほぼ同じ Teams 機能を使用できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="ed788-120">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="ed788-121">ゲストは組織の Azure Active Directory に B2B ユーザーとして追加され、ゲスト アカウントを使用して Teams にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed788-121">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="ed788-122">つまり、ゲストがお客様の組織にサインインするには、ゲスト自身の組織からサインアウトする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed788-122">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="ed788-123">Teams のゲスト アクセスを構成する方法については、「[チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed788-123">To configure guest access for Teams, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="ed788-124">外部アクセスとゲスト アクセスの比較</span><span class="sxs-lookup"><span data-stu-id="ed788-124">Compare external and guest access</span></span>

<span data-ttu-id="ed788-125">次の表に、外部アクセス (フェデレーション) とゲストの使用の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="ed788-125">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="ed788-126">いずれの場合も、組織外のユーザーは外部のユーザーとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="ed788-126">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="ed788-127">ユーザーが実行できる操作</span><span class="sxs-lookup"><span data-stu-id="ed788-127">Things your users can do</span></span>

| <span data-ttu-id="ed788-128">ユーザーは、次のことを実行できます</span><span class="sxs-lookup"><span data-stu-id="ed788-128">Users can</span></span> | <span data-ttu-id="ed788-129">外部アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="ed788-129">External access users</span></span> | <span data-ttu-id="ed788-130">ゲスト</span><span class="sxs-lookup"><span data-stu-id="ed788-130">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="ed788-131">別の組織のユーザーとチャットする</span><span class="sxs-lookup"><span data-stu-id="ed788-131">Chat with someone in another organization</span></span> | <span data-ttu-id="ed788-132">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-132">Yes</span></span> | <span data-ttu-id="ed788-133">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-133">Yes</span></span> |
| <span data-ttu-id="ed788-134">別の組織のユーザーに電話をかける</span><span class="sxs-lookup"><span data-stu-id="ed788-134">Call someone in another organization</span></span> | <span data-ttu-id="ed788-135">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-135">Yes</span></span> | <span data-ttu-id="ed788-136">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-136">Yes</span></span> |
| <span data-ttu-id="ed788-137">別の組織のユーザーが通話またはチャットできるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="ed788-137">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="ed788-138">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-138">Yes</span></span> | <span data-ttu-id="ed788-139">はい<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-139">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="ed788-140">別の組織内のユーザーを検索する</span><span class="sxs-lookup"><span data-stu-id="ed788-140">Search for people in other organizations</span></span> | <span data-ttu-id="ed788-141">はい<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-141">Yes<sup>2</sup></span></span> | <span data-ttu-id="ed788-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="ed788-142">No</span></span> |
| <span data-ttu-id="ed788-143">ファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="ed788-143">Share files</span></span> | <span data-ttu-id="ed788-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="ed788-144">No</span></span> | <span data-ttu-id="ed788-145">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-145">Yes</span></span> |
| <span data-ttu-id="ed788-146">別の組織のユーザーの不在メッセージを見る</span><span class="sxs-lookup"><span data-stu-id="ed788-146">See the out-of-office message of someone in another organization</span></span> | <span data-ttu-id="ed788-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="ed788-147">No</span></span> | <span data-ttu-id="ed788-148">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-148">Yes</span></span> |
| <span data-ttu-id="ed788-149">別の組織のユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="ed788-149">Block someone in another organization</span></span>  | <span data-ttu-id="ed788-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="ed788-150">No</span></span> | <span data-ttu-id="ed788-151">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-151">Yes</span></span> |
| <span data-ttu-id="ed788-152">@メンションを使用する</span><span class="sxs-lookup"><span data-stu-id="ed788-152">Use @mentions</span></span> | <span data-ttu-id="ed788-153">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-153">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-154">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-154">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="ed788-155">組織外のユーザーが実行できる操作</span><span class="sxs-lookup"><span data-stu-id="ed788-155">Things people outside your organization can do</span></span>

| <span data-ttu-id="ed788-156">組織外のユーザーは、次のことを実行できます</span><span class="sxs-lookup"><span data-stu-id="ed788-156">People outside your organization can</span></span> | <span data-ttu-id="ed788-157">外部アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="ed788-157">External access users</span></span> | <span data-ttu-id="ed788-158">ゲスト</span><span class="sxs-lookup"><span data-stu-id="ed788-158">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="ed788-159">Teams のリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="ed788-159">Access Teams resources</span></span> | <span data-ttu-id="ed788-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="ed788-160">No</span></span> | <span data-ttu-id="ed788-161">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-161">Yes</span></span> |
| <span data-ttu-id="ed788-162">グループ チャットに追加される</span><span class="sxs-lookup"><span data-stu-id="ed788-162">Be added to a group chat</span></span> | <span data-ttu-id="ed788-163">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-163">Yes</span></span> | <span data-ttu-id="ed788-164">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-164">Yes</span></span> |
| <span data-ttu-id="ed788-165">会議に招待される</span><span class="sxs-lookup"><span data-stu-id="ed788-165">Be invited to a meeting</span></span> | <span data-ttu-id="ed788-166">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-166">Yes</span></span> | <span data-ttu-id="ed788-167">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-167">Yes</span></span> |
| <span data-ttu-id="ed788-168">プライベート通話をする</span><span class="sxs-lookup"><span data-stu-id="ed788-168">Make private calls</span></span> | <span data-ttu-id="ed788-169">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-169">Yes</span></span> | <span data-ttu-id="ed788-170">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-170">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-171">ダイヤルイン会議の参加者の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="ed788-171">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="ed788-172">いいえ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-172">No<sup>4</sup></span></span> | <span data-ttu-id="ed788-173">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-173">Yes</span></span> |
| <span data-ttu-id="ed788-174">IP ビデオを使う</span><span class="sxs-lookup"><span data-stu-id="ed788-174">Use IP video</span></span> | <span data-ttu-id="ed788-175">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-175">Yes</span></span> | <span data-ttu-id="ed788-176">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-176">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-177">画面共有を使う</span><span class="sxs-lookup"><span data-stu-id="ed788-177">Use screen sharing</span></span> | <span data-ttu-id="ed788-178">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-178">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-179">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-179">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-180">今すぐ会議を使う</span><span class="sxs-lookup"><span data-stu-id="ed788-180">Use meet now</span></span> | <span data-ttu-id="ed788-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="ed788-181">No</span></span> | <span data-ttu-id="ed788-182">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-182">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-183">送信済みメッセージを編集する</span><span class="sxs-lookup"><span data-stu-id="ed788-183">Edit sent messages</span></span> | <span data-ttu-id="ed788-184">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-184">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-185">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-185">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-186">送信済みメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="ed788-186">Delete sent messages</span></span> | <span data-ttu-id="ed788-187">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-187">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-188">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-188">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-189">会話で Giphy を使用する</span><span class="sxs-lookup"><span data-stu-id="ed788-189">Use Giphy in conversation</span></span> | <span data-ttu-id="ed788-190">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-190">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-191">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-191">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-192">会話でミームを使用する</span><span class="sxs-lookup"><span data-stu-id="ed788-192">Use memes in conversation</span></span> | <span data-ttu-id="ed788-193">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-193">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-194">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-194">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-195">会話でステッカーを使用する</span><span class="sxs-lookup"><span data-stu-id="ed788-195">Use stickers in conversation</span></span> | <span data-ttu-id="ed788-196">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-196">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-197">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-197">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="ed788-198">プレゼンスが表示される</span><span class="sxs-lookup"><span data-stu-id="ed788-198">Presence is displayed</span></span> | <span data-ttu-id="ed788-199">Yes</span><span class="sxs-lookup"><span data-stu-id="ed788-199">Yes</span></span> | <span data-ttu-id="ed788-200">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-200">Yes</span></span> |
| <span data-ttu-id="ed788-201">@メンションを使用する</span><span class="sxs-lookup"><span data-stu-id="ed788-201">Use @mentions</span></span> | <span data-ttu-id="ed788-202">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ed788-202">Yes<sup>3</sup></span></span> | <span data-ttu-id="ed788-203">はい</span><span class="sxs-lookup"><span data-stu-id="ed788-203">Yes</span></span> |

<br>

<span data-ttu-id="ed788-204"><sup>1</sup> ユーザーがゲストとして追加され、ゲスト アカウントでサインインされている場合。</span><span class="sxs-lookup"><span data-stu-id="ed788-204"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="ed788-205"><sup>2</sup> メールまたはセッション開始プロトコル (SIP) アドレスのみ。</span><span class="sxs-lookup"><span data-stu-id="ed788-205"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="ed788-206"><sup>3</sup> 2 つの異なる組織の Teams のみユーザーの Teams のみの 1:1 チャットでサポートされる。</span><span class="sxs-lookup"><span data-stu-id="ed788-206"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="ed788-207"><sup>4</sup> 既定では、外部ユーザーはダイヤル インした参加者の電話番号は見ることができません。</span><span class="sxs-lookup"><span data-stu-id="ed788-207"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="ed788-208">これらの電話番号のプライバシーを維持したい場合は、**開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。</span><span class="sxs-lookup"><span data-stu-id="ed788-208">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="ed788-209">詳細については、「[Microsoft Teams で会議の入退室通知をオンまたはオフにする](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed788-209">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="ed788-210"><sup>5</sup> 既定で許可されていますが、Teams 管理者がオフにすることができます</span><span class="sxs-lookup"><span data-stu-id="ed788-210"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed788-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed788-211">Related topics</span></span>

[<span data-ttu-id="ed788-212">Teams での外部アクセス</span><span class="sxs-lookup"><span data-stu-id="ed788-212">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="ed788-213">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="ed788-213">Guest access in Teams</span></span>](guest-access.md)
