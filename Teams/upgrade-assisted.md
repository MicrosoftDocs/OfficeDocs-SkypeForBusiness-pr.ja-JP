---
title: 支援付きアップグレード|SkypeBusiness Online からアップグレードTeamsする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business Online から Skype for Business への支援付きアップグレードの概要Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e445fd6c5d26a64005ff1c285d8e9d843ca0211
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656060"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="65299-103">Skype for Business Online から Microsoft Teams への支援付きMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="65299-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="65299-104">Microsoft では、サービスが 2021 年 7 月 31 日に終了するSkype for Business Online から組織が移行を成功させるのに役立つ、Teams への支援付きアップグレードを提供しています。</span><span class="sxs-lookup"><span data-stu-id="65299-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="65299-105">組織がハイブリッド (Skype for Business Online と Skype for Business Server の両方のユーザー) 環境で *Skype for Business Online* または *Skype for Business* Onlineからアップグレードする場合でも、支援付きアップグレードでは、必要な技術タスクの数を減らし、組織の準備、ユーザー認識、Teams トレーニングに集中できます。</span><span class="sxs-lookup"><span data-stu-id="65299-105">Whether your organization is upgrading from a *Skype for Business Online* or *Skype for Business Online with hybrid* (users in both Skype for Business Online **and** Skype for Business Server) environment, assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="65299-106">アップグレードの前に、アップグレードガイダンス [を確認](https://aka.ms/SkypeToTeams) することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65299-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="65299-107">アップグレード ガイダンスには、Skype for Business Online から Teams へのアップグレードを完了するための推奨アクティビティと役に立つリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65299-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="65299-108">このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用Teams、Teams へのアップグレードを計画しているすべての組織に適用されます。</span><span class="sxs-lookup"><span data-stu-id="65299-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="65299-109">Teams への支援付きアップグレードをスケジュールしている場合は、スケジュールされたアップグレード日の前に Skype for Business Online から独自のアップグレードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="65299-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="65299-110">アプリケーションに手動でアップグレードする方法の詳細については、Teams ガイダンスを[参照してください](https://aka.ms/SkypeToTeams)。</span><span class="sxs-lookup"><span data-stu-id="65299-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="65299-111">サポートされているアップグレードは、オンプレミスのデプロイで使用Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="65299-111">Assisted upgrades are not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="65299-112">スケジュールされた顧客に関する通知</span><span class="sxs-lookup"><span data-stu-id="65299-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="65299-113">Skype for Businessオンライン のお客様は、サービスへのアップグレードの支援をTeams、一連のアップグレード通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="65299-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="65299-114">これらの通知は、スケジュールされたアップグレード日の 90 日前に開始されます。</span><span class="sxs-lookup"><span data-stu-id="65299-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="65299-115">これらの通知は、Microsoft 365メッセージ センターでの変更の投稿の計画、Teams 管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグとして配信されます。</span><span class="sxs-lookup"><span data-stu-id="65299-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="65299-116">アップグレード通知には、支援されたアップグレードのスケジュールされた日付が含まれます。アップグレードリソースとトレーニングにリンクして、アップグレードリソースの導入と使用を促進Teams。</span><span class="sxs-lookup"><span data-stu-id="65299-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="65299-117">支援付きアップグレード エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="65299-117">The assisted upgrade experience</span></span>

<span data-ttu-id="65299-118">支援付きアップグレードは 2021 年 8 月に開始され、上記のスケジュール通知でテナント固有の日付が共有されます。</span><span class="sxs-lookup"><span data-stu-id="65299-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="65299-119">アップグレードの支援は、ハイブリッド環境を使用する Skype for Business Online と Skype for Business Online のどちらの環境を使用しているかによって少し異なります。</span><span class="sxs-lookup"><span data-stu-id="65299-119">Your assisted upgrade experience will differ slightly depending on whether you have a Skype for Business Online-only or a Skype for Business Online with hybrid environment:</span></span>

- <span data-ttu-id="65299-120">**Skype for Businessオンラインのみ** 支援されたアップグレード プロセスによって、組織 `TeamsUpgradeOverridePolicy` にポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="65299-120">**Skype for Business Online-only** The assisted upgrade process will apply the `TeamsUpgradeOverridePolicy` policy to your organization.</span></span> <span data-ttu-id="65299-121">このポリシーを適用すると、すべての Skype for Business Online ユーザーが [のみ] Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="65299-121">When this policy is applied, all your Skype for Business Online users will be placed in Teams Only mode.</span></span>
- <span data-ttu-id="65299-122">**Skype for Business Online とハイブリッド** ハイブリッド環境には、次のいずれかのカテゴリに分類されるユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="65299-122">**Skype for Business Online with hybrid** Hybrid environments may have users that fall into one of the following categories:</span></span>

  - <span data-ttu-id="65299-123">オンプレミスのユーザーがクラウドにSkype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65299-123">On-premises users homed on Skype for Business Server</span></span>
  - <span data-ttu-id="65299-124">Skype for Businessオンライン ユーザー (Teamsのみ)</span><span class="sxs-lookup"><span data-stu-id="65299-124">Skype for Business Online users that are in Teams Only mode</span></span>
  - <span data-ttu-id="65299-125">Skype for Businessオンライン モードではない **オンライン** ユーザー Teamsのみ</span><span class="sxs-lookup"><span data-stu-id="65299-125">Skype for Business Online users that are **not** in Teams Only mode</span></span>

  <span data-ttu-id="65299-126">上記の各カテゴリにユーザーが複数存在する場合、サポートされるアップグレード プロセスでは、そのモードにまだユーザーが存在しない場合にのみ、Skype for Business Online ユーザーが Teams のみモードに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="65299-126">If you have a mixture of users in each of the categories listed above, the assisted upgrade process will only switch Skype for Business Online users to Teams Only mode if they're not already in that mode.</span></span> <span data-ttu-id="65299-127">オンプレミスのSkype for Businessは、支援されたアップグレード プロセスの影響を受け取る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65299-127">On-premises Skype for Business users won't be impacted by the assisted upgrade process.</span></span>

> [!NOTE]
> <span data-ttu-id="65299-128">2021 年 7 月 31 日より後の日付にアップグレードの支援が予定されている場合でも心配はいりません。</span><span class="sxs-lookup"><span data-stu-id="65299-128">Don't worry if your assisted upgrade is scheduled for a date after July 31, 2021.</span></span> <span data-ttu-id="65299-129">アップグレードが完了するまで、組織は Skype for Business Online を使用できます。</span><span class="sxs-lookup"><span data-stu-id="65299-129">Your organization will be able to use Skype for Business Online until your upgrade is complete.</span></span>

<span data-ttu-id="65299-130">アップグレードの期間は、ユーザーの量とデプロイの特性によって異なります。</span><span class="sxs-lookup"><span data-stu-id="65299-130">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="65299-131">ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="65299-131">In most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="65299-132">この期間中、エンド ユーザーは引き続きオンライン機能Skype for Businessアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="65299-132">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="65299-133">アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話に Teams の使用が開始されます。</span><span class="sxs-lookup"><span data-stu-id="65299-133">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="65299-134">アップグレード後のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="65299-134">The post-upgrade experience</span></span>

<span data-ttu-id="65299-135">支援付きアップグレードが完了すると、アップグレードされたユーザーの **共存** モードが [共存モード] Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="65299-135">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only.</span></span> <span data-ttu-id="65299-136">アップグレードの前に、Teams[モードに関する考慮事項を確認](teams-only-mode-considerations.md)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65299-136">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="65299-137">次の表は、「ユーザー エクスペリエンスのみ」の概要Teamsを示しています。</span><span class="sxs-lookup"><span data-stu-id="65299-137">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="65299-138">**チャットと通話**</span><span class="sxs-lookup"><span data-stu-id="65299-138">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="65299-139">すべての通話とチャットが開始され、受信Teams</span><span class="sxs-lookup"><span data-stu-id="65299-139">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="65299-140">ユーザーは、任意のユーザーと通信 (チャット/通話) Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="65299-140">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="65299-141">組織は、外部Teamsアクセス許可を管理することで、Skype コンシューマー サービスのユーザーと通信できます[。](manage-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="65299-141">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="65299-142">Teams Online にサインインしようとしたユーザーは、Skype for BusinessにリダイレクトTeams</span><span class="sxs-lookup"><span data-stu-id="65299-142">Teams users who attempt to sign in to Skype for Business Online are redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="65299-143">**会議**</span><span class="sxs-lookup"><span data-stu-id="65299-143">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="65299-144">ユーザーは、すべての新しい会議を Teamsスケジュールします (プラグインは置き換え)</span><span class="sxs-lookup"><span data-stu-id="65299-144">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="65299-145">**移行されたデータ**</span><span class="sxs-lookup"><span data-stu-id="65299-145">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="65299-146">フェデレーションを含む Skype for Business Online の既存の連絡先 (ただし、配布リストは含め)</span><span class="sxs-lookup"><span data-stu-id="65299-146">Existing contacts from Skype for Business Online including federated (but no distribution lists)</span></span>
        - <span data-ttu-id="65299-147">連絡先は、ユーザーが初めてログインTeamsに移行されます。</span><span class="sxs-lookup"><span data-stu-id="65299-147">Contacts are migrated when users log into Teams for the first time.</span></span>
            > [!IMPORTANT]
            ><span data-ttu-id="65299-148">連絡先は、アップグレードが完了した後 90 日以内に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65299-148">Contacts must be migrated within 90 days of the completion of your upgrade.</span></span>
        - <span data-ttu-id="65299-149">既存の Skype for Business Online 会議は、オンライン会議にTeamsされます</span><span class="sxs-lookup"><span data-stu-id="65299-149">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
            > [!IMPORTANT]
            > <span data-ttu-id="65299-150">純粋な Skype for Business Online 構成をお持ちのお客様は、Meeting Migration Service (MMS) を使用して、既存の Skype for Business Online 会議を他の会議Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="65299-150">Customers with pure Skype for Business Online configurations need to use the Meeting Migration Service (MMS) to migrate existing Skype for Business Online meetings to Teams meetings.</span></span> <span data-ttu-id="65299-151">アップグレードの支援日より前に MMS を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65299-151">We recommend using MMS prior to the assisted upgrade date.</span></span> <span data-ttu-id="65299-152">MMS の詳細については [、「Meeting Migration Service (MMS) の使用」を参照してください。](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="65299-152">For more information about MMS, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span></span>
    :::column-end:::
:::row-end:::

<span data-ttu-id="65299-153">アップグレードが完了すると、ハイブリッド 展開を使用している組織は、ユーザーをオンプレミスから Teams に移動したり、Teamsからオンプレミスに移動したりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="65299-153">After your upgrade is complete, organizations with hybrid deployments may move users from on-premises to Teams or moved from Teams to on-premises.</span></span>  

## <a name="related-content"></a><span data-ttu-id="65299-154">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="65299-154">Related content</span></span>

- [<span data-ttu-id="65299-155">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="65299-155">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="65299-156">Skype for Business Online のサポート終了</span><span class="sxs-lookup"><span data-stu-id="65299-156">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="65299-157">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="65299-157">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="65299-158">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="65299-158">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
