---
title: Microsoft Teams 管理センターで Skype for Business の設定を管理する
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753562"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e9fc6-103">Microsoft Teams 管理センターで Skype for Business の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="e9fc6-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e9fc6-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="e9fc6-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="e9fc6-105">管理者として、Microsoft Teams 管理センターでは、組織の Skype for business ユーザーの Skype for Business の機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="e9fc6-106">ユーザー詳細ページの [ **skype For business** ] タブで、[組織の](#manage-skype-for-business-settings-for-your-organization)設定を**skype for business**ページと[個々のユーザーの](#manage-skype-for-business-settings-for-individual-users)設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="e9fc6-107">組織の [共存] モードが [**チームのみ**] に設定されていない場合は、[ **Skype for business** ] ページのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="e9fc6-108">同様に、ユーザーの [共存] モードが [**チームのみ**] ではない場合は、[ **Skype for business** ] タブのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="e9fc6-109">共存モードの詳細については、「 [Teams と Skype For business の共存と相互運用性を理解](teams-and-skypeforbusiness-coexistence-and-interoperability.md) する」および「 [共存とアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e9fc6-110">Skype for Business の設定は、以前は Microsoft Teams 管理センターの **従来のポータル** にありました。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e9fc6-111">従来のポータルが廃止されたため、Skype for Business 管理のために Teams 管理センターの新しい場所に設定が移行されました。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="e9fc6-112">Microsoft Teams 管理センターで Skype for Business の機能を管理するには、グローバル管理者または Skype for Business 管理者の [AZURE AD 管理者の役割](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="e9fc6-113">組織の Skype for Business の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="e9fc6-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="e9fc6-114">Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定**] の [  >  **Skype for business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="e9fc6-115">ここでは、組織内のすべての Skype for Business ユーザーに対して、Skype 会議ブロードキャスト、プレゼンスプライバシー、モバイルデバイス通知を構成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="e9fc6-116">Skype 会議ブロードキャスト</span><span class="sxs-lookup"><span data-stu-id="e9fc6-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e9fc6-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="e9fc6-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="e9fc6-118">組織の [Skype 会議ブロードキャスト](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) を管理するには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センターでの Skype 会議ブロードキャストの設定のスクリーンショット":::

- <span data-ttu-id="e9fc6-120">**Skype 会議ブロードキャスト**: これをオンにして、組織の Skype 会議ブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="e9fc6-121">この機能を有効にすると、 [Skype 会議ブロードキャスト用にネットワーク](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="e9fc6-122">**「プレビュー機能」をご覧**ください。新機能をいち早く利用するには、このオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="e9fc6-123">**開催者は、匿名の会議をスケジュールでき**ます。開催者に、組織外のユーザーがサインインしなくても参加できるようにするブロードキャストイベントを作成できるようにするには、このオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="e9fc6-124">**Skype 会議ブロードキャスト会議を記録**する: これをオンにして、開催者と発表者が会議を記録できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="e9fc6-125">**出席者のヘルプデスクサポート url**: 会議中にヘルプが必要な場合に、会議出席者が使用できる組織のサポート url を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="e9fc6-126">プレゼンスとモバイル通知</span><span class="sxs-lookup"><span data-stu-id="e9fc6-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e9fc6-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="e9fc6-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="e9fc6-128">次の設定を使用して、組織内の Skype for Business プレゼンスプライバシーとモバイル通知を管理します。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット":::

#### <a name="presence"></a><span data-ttu-id="e9fc6-130">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="e9fc6-130">Presence</span></span>

<span data-ttu-id="e9fc6-131">既定では、組織内の Skype for Business ユーザーは、他の Skype for Business ユーザーのプレゼンス状態 (連絡可能、取り込み中、退席中など) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="e9fc6-132">Skype for Business ユーザーのプレゼンスを表示できるユーザーを設定するには、次のいずれかを選びます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="e9fc6-133">**プレゼンス情報を自動的に表示**する: ユーザーの **外部** または **ブロック** されたリストに追加されていない組織内のすべての Skype for business ユーザーは、そのユーザーのプレゼンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="e9fc6-134">**ユーザーの連絡先にのみプレゼンス情報を表示**する: **外部** または **ブロック** されたリストに追加されていないユーザーの連絡先リストに含まれるすべての Skype for business ユーザーは、そのユーザーのプレゼンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="e9fc6-135">ユーザーは、[**設定**  >  **ツール**  >  **] のオプション**に移動して、Skype for business でこの設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="e9fc6-136">モバイル通知</span><span class="sxs-lookup"><span data-stu-id="e9fc6-136">Mobile notifications</span></span>

<span data-ttu-id="e9fc6-137">Skype for Business モバイルユーザーが、送受信されたインスタントメッセージ、ボイスメールメッセージ、不在着信について、プッシュ通知サービスを使って通知を受け取るかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="e9fc6-138">組織で使用されているモバイルデバイスに応じて、 **Microsoft プッシュ通知サービス**、 **Apple プッシュ通知サービス**、またはその両方を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="e9fc6-139">以下の点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-139">Keep the following in mind:</span></span>

- <span data-ttu-id="e9fc6-140">プッシュ通知をオフにすると、ユーザーは、モバイルデバイスで Skype for Business を次に起動したときにすべての通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="e9fc6-141">既定では、プッシュ通知はオンになっています。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="e9fc6-142">各ユーザーは、モバイルデバイスの Skype for Business でそれらをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="e9fc6-143">管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e9fc6-144">マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="e9fc6-145">このプライバシーに関する [声明](https://go.microsoft.com/fwlink/p/?linkid=247732)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="e9fc6-146">個々のユーザー向けに Skype for Business の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="e9fc6-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e9fc6-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="e9fc6-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="e9fc6-148">個々のユーザーの Skype for Business の設定を管理するには、Teams 管理センターの左側のナビゲーションで [ **ユーザー**] に移動し、ユーザーの表示名をクリックして [ユーザーの詳細] ページを開き、[ **Skype for business の設定** ] タブを選択します。ここでは、ユーザーの外部アクセスと会議の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="[ユーザーの詳細] ページの [Skype for Business] タブのスクリーンショット":::

### <a name="external-access-settings"></a><span data-ttu-id="e9fc6-150">外部アクセス設定</span><span class="sxs-lookup"><span data-stu-id="e9fc6-150">External access settings</span></span>

<span data-ttu-id="e9fc6-151">ユーザーが組織外のユーザーと通信できるかどうかを、選択的に許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="e9fc6-152">**外部の skype For business ユーザー**: フェデレーションドメインの Skype for business ユーザーとの通信を許可する場合は、このオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="e9fc6-153">**外部の skype ユーザー**: ユーザーが skype ユーザーと通信できるようにする場合は、このオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="e9fc6-154">会議の設定</span><span class="sxs-lookup"><span data-stu-id="e9fc6-154">Meeting settings</span></span>

<span data-ttu-id="e9fc6-155">ユーザーに対して次の会議の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="e9fc6-156">**オーディオ & ビデオ**: 次のいずれかのオーディオとビデオの設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-156">**Audio & video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="e9fc6-157">**なし**: ユーザーはオーディオまたはビデオを使用できません。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="e9fc6-158">**オーディオのみ**: ユーザーはオーディオは使用できますが、ビデオは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="e9fc6-159">**オーディオとビデオ**: ユーザーは音声とビデオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="e9fc6-160">**オーディオとビデオ (HD)**: ユーザーはオーディオと hd のビデオを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="e9fc6-161">**会議 & の会話を記録**する: このオプションをオンにすると、ユーザーは会話と会議の記録を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="e9fc6-162">**コンプライアンス**: 電子的に保存された情報を保持する必要がある場合は、このオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9fc6-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
