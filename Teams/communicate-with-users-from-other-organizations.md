---
title: 別の組織のユーザーとの電話およびチャット
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 外部アクセス (フェデレーション) とゲスト アクセスを使用して、Microsoft Teams で組織外のユーザーと電話およびチャットし、ユーザーを検索および追加する方法を説明します。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031813"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a><span data-ttu-id="62148-103">Microsoft Teams の別の組織のユーザーとの電話およびチャット</span><span class="sxs-lookup"><span data-stu-id="62148-103">Call and chat with users from other organizations in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="62148-p101">組織外の人と通信して共同作業する必要がある場合、Microsoft Teams はそれを実現する 2 つの異なる方法を提供します。1 つ目は、 **外部 アクセス** (フェデレーション) であり、別のドメイン (contoso.com など) のユーザーを検索、呼び出し、チャットできます。2 つ目は **ゲスト アクセス** で、メール アドレスを使うことにより、個人をゲストとしてチームに追加することができます。組織内の別のユーザーと同じように、ゲストと共同作業できます。</span><span class="sxs-lookup"><span data-stu-id="62148-p101">When you need to communicate and collaborate with people outside your organization, Microsoft Teams gives you two different ways to make that happen. The first – **external access** (federation) – lets  you find, call, and chat with users in other domains (for example, contoso.com). The second – **guest access** – lets you add individuals to your teams, as guests, using their email address. You can collaborate with guests as you would with any other users in your organization.</span></span>

<span data-ttu-id="62148-108">必要に応じて、外部アクセスとゲストアクセスの両方を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="62148-108">You can use both external access and guest access if you want - one doesn't preclude the other.</span></span>

<span data-ttu-id="62148-109">高レベルでの選択方法は次のとおりです (詳細な比較については、「[外部アクセスとゲスト アクセスの比較](#compare-external-and-guest-access)」に移動してください)。</span><span class="sxs-lookup"><span data-stu-id="62148-109">At a high level, here’s how to choose (for a detailed comparison, jump down to [Compare external and guest access](#compare-external-and-guest-access)):</span></span>

## <a name="external-access"></a><span data-ttu-id="62148-110">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="62148-110">External access</span></span>

<span data-ttu-id="62148-p102">別のドメインの外部ユーザが会議を検索、呼び出し、チャット、およびセットアップできるソリューションが必要な場合は、 **外部アクセス** (フェデレーション) を使用します。外部ユーザーは、組織のチームまたはチーム リソースにアクセスできません。Skype for Business (オンラインまたはオンプレミス) または Skype (2020 年初頭に予定) を使用している外部ユーザーと通信する場合は、外部アクセスを選択します。</span><span class="sxs-lookup"><span data-stu-id="62148-p102">Use **external access** (federation) when you need a solution that lets external users in other domains find, call, chat, and set up meetings with you. External users have no access to your organization's teams or team resources. Choose external access when you want to communicate with users outside your organization who are still on Skype for Business (online or on premises) or Skype (coming in early 2020).</span></span> 

<span data-ttu-id="62148-p103">Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。Teams 管理者はこれをオフにするか、含める (または除外する) ドメインを指定できます。詳細については、「[外部アクセスを管理する](manage-external-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62148-p103">External access is turned on by default in Teams, which means your org can communicate with all external domains. The Teams admin can turn it off or specify which domains to include (or exclude). To learn more, read [Manage external access](manage-external-access.md).</span></span> 

<span data-ttu-id="62148-117">外部ユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、[ゲスト アクセス](#guest-access)です。</span><span class="sxs-lookup"><span data-stu-id="62148-117">If you want external users to have access to teams and channels, [guest access](#guest-access) might be a better way to go.</span></span> 


## <a name="guest-access"></a><span data-ttu-id="62148-118">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="62148-118">Guest access</span></span>

<span data-ttu-id="62148-p104">**ゲスト アクセス** を使用して (ドメインに関係なく) 個々のユーザーをチームに追加し、Word、Excel または PowerPoint などの Microsoft 365 アプリまたは Office 365 アプリを使用して、チャット、通話、会議、組織ファイル (SharePoint または OneDrive for Business に保存されている) での共同作業を行うことができます。ゲスト ユーザーには、ネイティブ チーム メンバーとほぼ同じ Teams 機能を付与できます。詳しくは、 [Teams でのゲスト アクセス](guest-access.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62148-p104">Use **guest access** to add an individual user (regardless of domain) to a team, where they can chat, call, meet, and collaborate on organization files (stored in SharePoint or OneDrive for Business), using Microsoft 365 or Office 365 apps such as Word, Excel, or PowerPoint. A guest user can be given nearly all the same Teams capabilities as a native team member. To learn more, read [Guest access in Teams](guest-access.md).</span></span>

- <span data-ttu-id="62148-122">ゲストは組織の Active Directory に追加されます。</span><span class="sxs-lookup"><span data-stu-id="62148-122">Guests are added to your organization’s Active Directory.</span></span>
- <span data-ttu-id="62148-p105">ゲストと通信するには、ゲストはゲスト アカウントを使用して Teams にサインインする必要があります。つまり、Teams アカウントにサインインするか、同じアカウントではない場合組織を変更するために、自分の Teams アカウントからサイン アウトしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="62148-p105">To communicate with a guest, the guest has to be signed in to Teams using their guest account. This means that a guest may have to sign out of their own Teams account to sign in to your Teams account, or switch organizations if it's the same account.</span></span>
- <span data-ttu-id="62148-125">ゲスト ユーザーは、外部アクセス (フェデレーション) ユーザーよりも多くの Teams (ファイル、チーム、チャネルなど) のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62148-125">Guest users have access to more resources in Teams - such as files, teams, and channels - than external-access (federated) users.</span></span>
- <span data-ttu-id="62148-p106">Teams 管理者は、ゲストが Teams 管理センターでできること (またはできないこと) をすべて制御します。詳細については、「[ゲスト アクセスを管理する](manage-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62148-p106">The Teams admin controls everything that a guest can (or can’t) do in the Teams admin center. To learn more, read [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="62148-128">組織でゲスト アクセスをオンにする準備ができたら、「[チームでゲストと共同で作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」から始めます。</span><span class="sxs-lookup"><span data-stu-id="62148-128">If you're ready to turn on guest access in your organization, start with the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>


## <a name="compare-external-and-guest-access"></a><span data-ttu-id="62148-129">外部アクセスとゲスト アクセスの比較</span><span class="sxs-lookup"><span data-stu-id="62148-129">Compare external and guest access</span></span>

| <span data-ttu-id="62148-130">機能</span><span class="sxs-lookup"><span data-stu-id="62148-130">Feature</span></span> | <span data-ttu-id="62148-131">外部アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="62148-131">External access users</span></span> | <span data-ttu-id="62148-132">ゲスト アクセス ユーザー</span><span class="sxs-lookup"><span data-stu-id="62148-132">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="62148-133">ユーザーは別の会社の誰かとチャットできる</span><span class="sxs-lookup"><span data-stu-id="62148-133">User can chat with someone in another company</span></span> | <span data-ttu-id="62148-134">はい</span><span class="sxs-lookup"><span data-stu-id="62148-134">Yes</span></span> |<span data-ttu-id="62148-135">はい</span><span class="sxs-lookup"><span data-stu-id="62148-135">Yes</span></span> |
| <span data-ttu-id="62148-136">ユーザーは別の会社の誰かと通話できる</span><span class="sxs-lookup"><span data-stu-id="62148-136">User can call someone in another company</span></span> | <span data-ttu-id="62148-137">はい</span><span class="sxs-lookup"><span data-stu-id="62148-137">Yes</span></span> | <span data-ttu-id="62148-138">はい</span><span class="sxs-lookup"><span data-stu-id="62148-138">Yes</span></span> |
| <span data-ttu-id="62148-139">ユーザーは別の会社の誰かが通話またはチャットできるかどうかを確認できる</span><span class="sxs-lookup"><span data-stu-id="62148-139">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="62148-140">はい</span><span class="sxs-lookup"><span data-stu-id="62148-140">Yes</span></span> | <span data-ttu-id="62148-141">はい<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="62148-141">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="62148-142">ユーザーは外部テナント全体でユーザーを検索できます</span><span class="sxs-lookup"><span data-stu-id="62148-142">User can search for users across external tenants</span></span> | <span data-ttu-id="62148-143">はい<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="62148-143">Yes<sup>2</sup></span></span> | <span data-ttu-id="62148-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-144">No</span></span> |
| <span data-ttu-id="62148-145">ユーザーはファイルを共有できる</span><span class="sxs-lookup"><span data-stu-id="62148-145">User can share files</span></span> | <span data-ttu-id="62148-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-146">No</span></span> | <span data-ttu-id="62148-147">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-147">Yes</span></span> |
| <span data-ttu-id="62148-148">ユーザーは Teams のリソースにアクセスできる</span><span class="sxs-lookup"><span data-stu-id="62148-148">User can access Teams resources</span></span> | <span data-ttu-id="62148-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-149">No</span></span> | <span data-ttu-id="62148-150">はい</span><span class="sxs-lookup"><span data-stu-id="62148-150">Yes</span></span> |
| <span data-ttu-id="62148-151">ユーザーをグループ チャットに追加できる</span><span class="sxs-lookup"><span data-stu-id="62148-151">User can be added to a group chat</span></span> | <span data-ttu-id="62148-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-152">No</span></span> | <span data-ttu-id="62148-153">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-153">Yes</span></span> |
| <span data-ttu-id="62148-154">ユーザーを会議に招待できる</span><span class="sxs-lookup"><span data-stu-id="62148-154">User can be invited to a meeting</span></span> | <span data-ttu-id="62148-155">はい</span><span class="sxs-lookup"><span data-stu-id="62148-155">Yes</span></span> | <span data-ttu-id="62148-156">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-156">Yes</span></span> |
| <span data-ttu-id="62148-157">追加のユーザーを外部ユーザーとのチャットに追加できる</span><span class="sxs-lookup"><span data-stu-id="62148-157">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="62148-158">いいえ<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="62148-158">No<sup>3</sup></span></span> | <span data-ttu-id="62148-159">該当なし</span><span class="sxs-lookup"><span data-stu-id="62148-159">N/A</span></span> |
| <span data-ttu-id="62148-160">ユーザーは外部関係者として識別される</span><span class="sxs-lookup"><span data-stu-id="62148-160">User is identified as an external party</span></span> | <span data-ttu-id="62148-161">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-161">Yes</span></span> | <span data-ttu-id="62148-162">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-162">Yes</span></span> |
| <span data-ttu-id="62148-163">プレゼンスが表示される</span><span class="sxs-lookup"><span data-stu-id="62148-163">Presence is displayed</span></span> | <span data-ttu-id="62148-164">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-164">Yes</span></span> | <span data-ttu-id="62148-165">はい</span><span class="sxs-lookup"><span data-stu-id="62148-165">Yes</span></span> |
| <span data-ttu-id="62148-166">不在時のメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="62148-166">Out of office message is shown</span></span> | <span data-ttu-id="62148-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-167">No</span></span> | <span data-ttu-id="62148-168">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-168">Yes</span></span> |
| <span data-ttu-id="62148-169">個々のユーザーをブロックできる</span><span class="sxs-lookup"><span data-stu-id="62148-169">Individual user can be blocked</span></span> | <span data-ttu-id="62148-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-170">No</span></span> | <span data-ttu-id="62148-171">はい</span><span class="sxs-lookup"><span data-stu-id="62148-171">Yes</span></span> |
| <span data-ttu-id="62148-172">@メンションがサポートされている</span><span class="sxs-lookup"><span data-stu-id="62148-172">@mentions are supported</span></span> | <span data-ttu-id="62148-173">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-173">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-174">はい</span><span class="sxs-lookup"><span data-stu-id="62148-174">Yes</span></span> |
| <span data-ttu-id="62148-175">プライベート通話をする</span><span class="sxs-lookup"><span data-stu-id="62148-175">Make private calls</span></span> | <span data-ttu-id="62148-176">はい</span><span class="sxs-lookup"><span data-stu-id="62148-176">Yes</span></span> | <span data-ttu-id="62148-177">はい</span><span class="sxs-lookup"><span data-stu-id="62148-177">Yes</span></span> |
| <span data-ttu-id="62148-178">ダイヤルイン会議の参加者の電話番号を表示する</span><span class="sxs-lookup"><span data-stu-id="62148-178">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="62148-179">No<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="62148-179">No<sup>5</sup></span></span> | <span data-ttu-id="62148-180">はい</span><span class="sxs-lookup"><span data-stu-id="62148-180">Yes</span></span> |
| <span data-ttu-id="62148-181">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="62148-181">Allow IP video</span></span> | <span data-ttu-id="62148-182">Yes</span><span class="sxs-lookup"><span data-stu-id="62148-182">Yes</span></span> | <span data-ttu-id="62148-183">はい</span><span class="sxs-lookup"><span data-stu-id="62148-183">Yes</span></span> |
| <span data-ttu-id="62148-184">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="62148-184">Screen sharing mode</span></span> | <span data-ttu-id="62148-185">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-185">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-186">はい</span><span class="sxs-lookup"><span data-stu-id="62148-186">Yes</span></span> |
| <span data-ttu-id="62148-187">今すぐ会議を許可する</span><span class="sxs-lookup"><span data-stu-id="62148-187">Allow meet now</span></span> | <span data-ttu-id="62148-188">いいえ</span><span class="sxs-lookup"><span data-stu-id="62148-188">No</span></span> | <span data-ttu-id="62148-189">はい</span><span class="sxs-lookup"><span data-stu-id="62148-189">Yes</span></span> |
| <span data-ttu-id="62148-190">送信済みメッセージを編集する</span><span class="sxs-lookup"><span data-stu-id="62148-190">Edit sent messages</span></span> | <span data-ttu-id="62148-191">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-191">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-192">はい</span><span class="sxs-lookup"><span data-stu-id="62148-192">Yes</span></span> |
| <span data-ttu-id="62148-193">送信済みメッセージを削除できる</span><span class="sxs-lookup"><span data-stu-id="62148-193">Can delete sent messages</span></span> | <span data-ttu-id="62148-194">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-194">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-195">はい</span><span class="sxs-lookup"><span data-stu-id="62148-195">Yes</span></span> |
| <span data-ttu-id="62148-196">会話で Giphy を使用する</span><span class="sxs-lookup"><span data-stu-id="62148-196">Use Giphy in conversation</span></span> | <span data-ttu-id="62148-197">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-197">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-198">はい</span><span class="sxs-lookup"><span data-stu-id="62148-198">Yes</span></span> |
| <span data-ttu-id="62148-199">会話でミームを使用する</span><span class="sxs-lookup"><span data-stu-id="62148-199">Use memes in conversation</span></span> | <span data-ttu-id="62148-200">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-200">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-201">はい</span><span class="sxs-lookup"><span data-stu-id="62148-201">Yes</span></span> |
| <span data-ttu-id="62148-202">会話でステッカーを使用する</span><span class="sxs-lookup"><span data-stu-id="62148-202">Use stickers in conversation</span></span> | <span data-ttu-id="62148-203">はい<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="62148-203">Yes<sup>4</sup></span></span> | <span data-ttu-id="62148-204">はい</span><span class="sxs-lookup"><span data-stu-id="62148-204">Yes</span></span> |
||||

<span data-ttu-id="62148-205"><sup>1</sup> ユーザーがゲストとして追加され、ゲスト テナントにゲストとしてサインインしている場合。</span><span class="sxs-lookup"><span data-stu-id="62148-205"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="62148-206"><sup>2</sup> 電子メールまたはセッション開始プロトコル (SIP) アドレスのみ。</span><span class="sxs-lookup"><span data-stu-id="62148-206"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="62148-207"><sup>3</sup> 外部 (フェデレーション) チャットは 1:1 のみ。</span><span class="sxs-lookup"><span data-stu-id="62148-207"><sup>3</sup> External (federated) chat is 1:1 only.</span></span><br>
<span data-ttu-id="62148-208"><sup>4</sup> 2 つの異なる組織の Teams のみユーザーの Teams のみの 1:1 チャットでサポートされる。</span><span class="sxs-lookup"><span data-stu-id="62148-208"><sup>4</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="62148-p107"><sup>5</sup> 既定では、外部ユーザーはダイヤル インした参加者の電話番号は見ることができません。これらの電話番号のプライバシーを維持したい場合は、 **「入場/退出のお知らせの種類の **トーン** 」** (これにより、番号がチームによって読み取られません) を選択 します。詳細については、 [「Microsoft Teams で、入退出のお知らせをオン/オフにする」](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62148-p107"><sup>5</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="62148-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="62148-212">Related topics</span></span>

[<span data-ttu-id="62148-213">Teams での外部アクセス</span><span class="sxs-lookup"><span data-stu-id="62148-213">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="62148-214">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="62148-214">Guest access in Teams</span></span>](guest-access.md)

