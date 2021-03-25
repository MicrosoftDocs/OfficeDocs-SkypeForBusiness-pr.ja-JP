---
title: Microsoft Teams 管理センターで Skype for Business の設定を管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 管理センターで Skype for Business 機能の設定を管理する方法について説明します。
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117005"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c4e6b-103">Microsoft Teams 管理センターで Skype for Business の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="c4e6b-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="c4e6b-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="c4e6b-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="c4e6b-105">管理者として、Microsoft Teams 管理センターでは、組織内の Skype for Business ユーザーの Skype for Business 機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="c4e6b-106">Skype **for Business** [ページで](#manage-skype-for-business-settings-for-your-organization)組織の設定を管理し、[](#manage-skype-for-business-settings-for-individual-users)ユーザー詳細ページの **[Skype for Business]** タブで個々のユーザーの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="c4e6b-107">Skype **for Business** ページは、組織の共存モードが Teams にのみ設定されていない場合にのみ **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="c4e6b-108">同様に、ユーザーの共存モードが Teams のみではない場合にのみ、ユーザーの **[Skype for Business]** タブが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="c4e6b-109">共存モードの詳細については [、「Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) と Skype for Business の共存と相互運用性について」および「共存とアップグレードの設定」を [参照してください](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c4e6b-110">Skype for Business の設定は、以前は Microsoft Teams **管理センター** のレガシ ポータルに保存されています。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c4e6b-111">従来のポータルがサポートされなき、Skype for Business 管理用の Teams 管理センターでこれらの新しい場所に設定を移行しました。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="c4e6b-112">Microsoft Teams 管理センターで Skype for Business [AD](/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="c4e6b-113">組織の Skype for Business 設定を管理する</span><span class="sxs-lookup"><span data-stu-id="c4e6b-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="c4e6b-114">Microsoft Teams 管理センターの左側のナビゲーションで、組織 **全体の** 設定  >  **Skype for Business に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="c4e6b-115">ここから、組織内のすべての Skype for Business ユーザーの Skype 会議ブロードキャスト、プレゼンス プライバシー、モバイル デバイス通知を構成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="c4e6b-116">Skype 会議メディア</span><span class="sxs-lookup"><span data-stu-id="c4e6b-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="c4e6b-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="c4e6b-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="c4e6b-118">組織で Skype 会議ブロードキャストを [管理するには、次の](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センターの Skype 会議ブロードキャストの設定のスクリーンショット":::

- <span data-ttu-id="c4e6b-120">**Skype 会議ブロードキャスト**: 組織で Skype 会議ブロードキャストを有効にするには、この機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="c4e6b-121">この機能を有効にした後は、Skype 会議ブロードキャスト用にネットワーク [をセットアップする必要があります](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="c4e6b-122">**プレビュー機能を参照** してください:この機能をオンにすると、新機能に早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="c4e6b-123">**開催者は匿名** の会議をスケジュールできます。組織外のユーザーがサインインせずに参加できるブロードキャスト イベントを開催者に許可する場合は、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="c4e6b-124">**Skype 会議ブロードキャスト会議を記録** する: この機能をオンにして、開催者と発表者が会議を記録できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="c4e6b-125">**出席者向けヘルプ** デスク サポート URL: 会議中にヘルプが必要な場合に会議出席者が使用できる組織のサポート URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="c4e6b-126">プレゼンスとモバイルの通知</span><span class="sxs-lookup"><span data-stu-id="c4e6b-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="c4e6b-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="c4e6b-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="c4e6b-128">組織の Skype for Business プレゼンス プライバシーとモバイル通知を管理するには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット":::

#### <a name="presence"></a><span data-ttu-id="c4e6b-130">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="c4e6b-130">Presence</span></span>

<span data-ttu-id="c4e6b-131">既定では、組織内の Skype for Business ユーザーは、他の Skype for Business ユーザーのプレゼンス状態 (利用可能、取り込み中、または離れた場所など) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="c4e6b-132">Skype for Business ユーザーのプレゼンスを表示できるユーザーを設定するには、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="c4e6b-133">**プレゼンス情報を** 自動的に表示する: ユーザーの外部リストまたはブロックリストに追加されていない組織内のすべての Skype for  Businessユーザーは、そのユーザーのプレゼンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="c4e6b-134">**ユーザー** の連絡先にのみプレゼンス情報を表示する: 外部リストまたはブロックリストに追加されていないユーザーの連絡先リスト内のすべての Skype for Businessユーザーは、そのユーザーのプレゼンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="c4e6b-135">ユーザーは、[設定ツール] オプションに移動して、Skype for Business のこの **設定を**  >  **上書き**  >  **できます**。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="c4e6b-136">モバイルの通知</span><span class="sxs-lookup"><span data-stu-id="c4e6b-136">Mobile notifications</span></span>

<span data-ttu-id="c4e6b-137">Skype for Business モバイル ユーザーが、プッシュ通知サービスを通じて、受信したインスタント メッセージ、見逃したインスタント メッセージ、ボイスメール メッセージ、および通話の着信に関する通知を受け取るかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="c4e6b-138">組織で使用されているモバイル デバイスに応じて **、Microsoft プッシュ通知サービス、Apple Push** **Notification Service、** または両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="c4e6b-139">以下の点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-139">Keep the following in mind:</span></span>

- <span data-ttu-id="c4e6b-140">プッシュ通知をオフにした場合、次回モバイル デバイスで Skype for Business を起動すると、すべての通知がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="c4e6b-141">既定では、プッシュ通知はオンになっています。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="c4e6b-142">個々のユーザーは、モバイル デバイスの Skype for Business でオフにできます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="c4e6b-143">管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c4e6b-144">マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="c4e6b-145">このプライバシーに [関する声明をご覧ください](https://go.microsoft.com/fwlink/p/?linkid=247732)。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="c4e6b-146">個々のユーザーの Skype for Business 設定を管理する</span><span class="sxs-lookup"><span data-stu-id="c4e6b-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="c4e6b-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="c4e6b-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="c4e6b-148">個々のユーザーの Skype for Business 設定を管理するには、Teams 管理センターの左側のナビゲーションで [ユーザー] に移動し、ユーザーの表示名をクリックしてユーザーの詳細ページを開き **、[Skype for Business** の設定] タブを選択します。ここから、ユーザーの外部アクセスと会議の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="ユーザーの詳細ページの Skype for Business タブのスクリーンショット":::

### <a name="external-access-settings"></a><span data-ttu-id="c4e6b-150">外部アクセス設定</span><span class="sxs-lookup"><span data-stu-id="c4e6b-150">External access settings</span></span>

<span data-ttu-id="c4e6b-151">ユーザーが組織外のユーザーと通信できるかどうかを選択して許可またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="c4e6b-152">**外部の Skype for Business** ユーザー: フェデレーション ドメインの Skype for Business ユーザーとの通信をユーザーに許可する場合は、この機能をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="c4e6b-153">**外部の Skype ユーザー**: Skype ユーザーとの通信を許可する場合は、この機能をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="c4e6b-154">会議の設定</span><span class="sxs-lookup"><span data-stu-id="c4e6b-154">Meeting settings</span></span>

<span data-ttu-id="c4e6b-155">ユーザーに対して次の会議設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="c4e6b-156">**オーディオ &ビデオ**: 次のいずれかのオーディオとビデオの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="c4e6b-157">**なし**: ユーザーはオーディオまたはビデオを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="c4e6b-158">**オーディオのみ**: ユーザーはオーディオを使用できますが、ビデオは使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="c4e6b-159">**オーディオとビデオ**: ユーザーはオーディオとビデオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="c4e6b-160">**オーディオとビデオ (HD):** ユーザーはオーディオと高解像度のビデオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="c4e6b-161">**会議中&会話** を記録する: この機能をオンにすることにより、ユーザーは会話や会議を記録できます。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="c4e6b-162">**コンプライアンス**: 電子的に保存された情報を保持するために法的に要求される場合は、この機能を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="c4e6b-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>