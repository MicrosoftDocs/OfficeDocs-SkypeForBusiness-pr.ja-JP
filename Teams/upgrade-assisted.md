---
title: アップグレードの支援|Skype Business Online から Teams へのアップグレード
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business Online から Teams への支援されたアップグレードの概要
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995198"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="c56a7-103">Skype for Business Online から Microsoft Teams へのアップグレード支援</span><span class="sxs-lookup"><span data-stu-id="c56a7-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="c56a7-104">Microsoft では、2021 年 7 月 31 日にサービスが終了するに合わせ、組織が Skype for Business Online から正常に移行できるよう、Teams へのアップグレード支援を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c56a7-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="c56a7-105">アップグレード支援により、必要な技術的なタスクの数が減り、組織の準備、ユーザー認識、Teams トレーニングに集中できます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-105">Assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="c56a7-106">アップグレードの前に、アップグレードガイダンス [を確認](https://aka.ms/SkypeToTeams) することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c56a7-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="c56a7-107">アップグレード ガイダンスには、Skype for Business Online から Teams へのアップグレードを完了するための推奨アクティビティと役立つリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c56a7-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="c56a7-108">このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用するかに関して、Teams へのアップグレードを計画している組織に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="c56a7-109">Teams へのアップグレードを支援する予定の場合は、スケジュールされたアップグレード日の前に、Skype for Business Online から独自のアップグレードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="c56a7-110">Teams に手動でアップグレードする方法の詳細については、アップグレードのガイダンスを [参照してください](https://aka.ms/SkypeToTeams)。</span><span class="sxs-lookup"><span data-stu-id="c56a7-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="c56a7-111">Skype for Business Server のオンプレミスデプロイでは、アップグレードの支援は利用できません。</span><span class="sxs-lookup"><span data-stu-id="c56a7-111">Assisted upgrade is not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="c56a7-112">スケジュールされた顧客に関する通知</span><span class="sxs-lookup"><span data-stu-id="c56a7-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="c56a7-113">Teams へのアップグレード支援を予定している Skype for Business Online のお客様は、一連のアップグレード通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c56a7-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="c56a7-114">これらの通知は、スケジュールされたアップグレード日の 90 日前に開始されます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="c56a7-115">これらの通知は、Microsoft  365 メッセージ センターでの変更の計画の投稿、Teams 管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグとして配信されます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="c56a7-116">アップグレード通知には、アップグレード支援の予定日が含まれます。また、Teams の導入と使用を促進するためにリソースとトレーニングのアップグレードにリンクします。</span><span class="sxs-lookup"><span data-stu-id="c56a7-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="c56a7-117">アップグレードの支援を受け取るエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c56a7-117">The assisted upgrade experience</span></span>

<span data-ttu-id="c56a7-118">支援アップグレードは 2021 年 8 月に開始され、上記のスケジュール通知でテナント固有の日付が共有されます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="c56a7-119">アップグレードの期間は、ユーザーのボリュームとデプロイの特性によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c56a7-119">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="c56a7-120">ただし、ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-120">However, in most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="c56a7-121">この間、エンド ユーザーは引き続き Skype for Business Online 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-121">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="c56a7-122">アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話に Teams の使用が開始されます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-122">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="c56a7-123">アップグレード後のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c56a7-123">The post-upgrade experience</span></span>

<span data-ttu-id="c56a7-124">支援されたアップグレードが完了すると、アップグレードされたユーザーの共存モードは Teams Only に設定され、Microsoft によって異なる共存モードにのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-124">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only and can only be changed to a different coexistence mode by Microsoft.</span></span> <span data-ttu-id="c56a7-125">アップグレード前に [Teams Only モードの考慮事項を確認](teams-only-mode-considerations.md) することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c56a7-125">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="c56a7-126">次の表は、Teams Only ユーザー エクスペリエンスの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c56a7-126">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="c56a7-127">**チャットと通話**</span><span class="sxs-lookup"><span data-stu-id="c56a7-127">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="c56a7-128">Teams ですべての通話とチャットが開始および受信される</span><span class="sxs-lookup"><span data-stu-id="c56a7-128">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="c56a7-129">ユーザーは、Skype for Business ユーザーと通信 (チャット/通話) できます</span><span class="sxs-lookup"><span data-stu-id="c56a7-129">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="c56a7-130">組織は、外部アクセス許可を管理することで、Teams ユーザーが Skype コンシューマー サービスのユーザーと通信 [できます。](manage-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="c56a7-130">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="c56a7-131">Skype for Business Online へのサインインを試みる Teams ユーザーは、Teams にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c56a7-131">Teams users who attempt to sign in to Skype for Business Online will be redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="c56a7-132">**会議**</span><span class="sxs-lookup"><span data-stu-id="c56a7-132">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="c56a7-133">ユーザーが Teams ですべての新しい会議をスケジュールする (プラグインが置き換えられた)</span><span class="sxs-lookup"><span data-stu-id="c56a7-133">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="c56a7-134">**移行されたデータ**</span><span class="sxs-lookup"><span data-stu-id="c56a7-134">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="c56a7-135">フェデレーションを含む Skype for Business Online の既存の連絡先 (ただし、配布リストはありません)</span><span class="sxs-lookup"><span data-stu-id="c56a7-135">Existing contacts from Skype for Business Online including federated (but no distribution lists</span></span>
        - <span data-ttu-id="c56a7-136">既存の Skype for Business Online 会議が Teams 会議に変換される</span><span class="sxs-lookup"><span data-stu-id="c56a7-136">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
    :::column-end:::
:::row-end:::

## <a name="related-content"></a><span data-ttu-id="c56a7-137">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="c56a7-137">Related content</span></span>

- [<span data-ttu-id="c56a7-138">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="c56a7-138">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="c56a7-139">Skype for Business Online のサポート終了</span><span class="sxs-lookup"><span data-stu-id="c56a7-139">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="c56a7-140">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="c56a7-140">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="c56a7-141">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="c56a7-141">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
