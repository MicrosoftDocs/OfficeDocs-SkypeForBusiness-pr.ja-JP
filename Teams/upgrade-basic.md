---
title: アップグレード チェックリスト|Skype Business から Teams へのアップグレード |基本的な手順
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この加速された 10 段階のアクション プランに従って、基本的な Skype for Business セットアップから Microsoft Teams のセットアップに移行します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809087"
---
# <a name="upgrade-basic"></a><span data-ttu-id="b33c3-103">Upgrade Basic</span><span class="sxs-lookup"><span data-stu-id="b33c3-103">Upgrade Basic</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="b33c3-104">小規模な組織向け、または IM (チャット) と会議にのみ Skype for Business Online を使用する組織向けで設計された Upgrade Basic チェックリストは、Skype for Business から Teams への移行を成功に向け実装するためのコア、推奨アクティビティ、および関連リソースを含む、高速化されたアクション プランです。</span><span class="sxs-lookup"><span data-stu-id="b33c3-104">Designed for smaller organizations or those using Skype for Business Online for IM (chat) and meetings only, the Upgrade Basic checklist is an accelerated action plan that includes core, recommended activities and associated resources for implementing a successful move from Skype for Business to Teams.</span></span>

<span data-ttu-id="b33c3-105">この 10 の簡単な手順は、アップグレードを成功するために必要なすべてを提供します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-105">These ten easy steps provide everything you need for a successful upgrade.</span></span> <span data-ttu-id="b33c3-106">これらのタスクは、約 30 ~ 45 日後に完了するように設計されています。ただし、組織のアップグレード スケジュールに基づいてタスクの完了日を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-106">They're designed to be completed in about 30 to 45 days, but you should adjust task completion dates based on your organization's upgrade schedule.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b33c3-107">Skype for Business Online は 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-107">Skype for Business Online will be retired on July 31, 2021.</span></span> <span data-ttu-id="b33c3-108">その後、Skype for Business Online サービスへのアクセスやサポートは終了します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-108">After that time, the Skype for Business Online service will no longer be accessible or supported.</span></span> <span data-ttu-id="b33c3-109">移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b33c3-109">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span>

<span data-ttu-id="b33c3-110">アップグレード後の Skype for Business は何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="b33c3-110">What happens to Skype for Business after the upgrade?</span></span> <span data-ttu-id="b33c3-111">ユーザーが Teams にアップグレードされた後 (**Teams のみ** モード) は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="b33c3-111">After your users are upgraded to Teams (**Teams Only** mode):</span></span>

- <span data-ttu-id="b33c3-112">Skype for Business クライアントが無効になり、すべてのチャットと通話が Teams に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-112">Their Skype for Business client is disabled, and all chat and calls go to Teams.</span></span> <span data-ttu-id="b33c3-113">これにより、デスクトップ上のクライアントはアンインストールされないので注意してください。</span><span class="sxs-lookup"><span data-stu-id="b33c3-113">Note that this will not uninstall the client on their desktops.</span></span>
- <span data-ttu-id="b33c3-114">アップグレードの前にスケジュールされていた Skype for Business 会議は設計通り動作しますが、すべての新しい会議は Teams でスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-114">Any Skype for Business meetings that were scheduled before the upgrade work as designed, but all new meetings are scheduled in Teams.</span></span> <span data-ttu-id="b33c3-115">Skype for Business プラグインは Outlook では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b33c3-115">The Skype for Business plugin will no longer be available in Outlook.</span></span> 
- <span data-ttu-id="b33c3-116">ユーザーが Skype for Business にサインインしようとする場合、クライアントから Teams にアップグレードされたという通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-116">If users try to sign in to Skype for Business, they get a notification from their client that they've been upgraded to Teams.</span></span>
- <span data-ttu-id="b33c3-117">ユーザーは、モバイル デバイスで Skype for Business クライアントを手動でアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-117">Users need to manually uninstall the Skype for Business client on their mobile devices.</span></span>

<span data-ttu-id="b33c3-118">アップグレードに関 [するその他](https://aka.ms/SkypeToTeams-FAQ) の質問については、よく寄せられる質問を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33c3-118">See our [FAQ](https://aka.ms/SkypeToTeams-FAQ) for additional questions about your upgrade.</span></span>

<span data-ttu-id="b33c3-119">Teams に慣れ親しくない場合</span><span class="sxs-lookup"><span data-stu-id="b33c3-119">Not familiar with Teams?</span></span> <span data-ttu-id="b33c3-120">[](https://products.office.com/microsoft-teams/group-chat-software) Teams が会話、会議、ファイル、Office アプリ、サードパーティとの統合を一緒に行う方法について説明します。Microsoft 365 と Office 365 でチームワークのためのハブを 1 つ提供します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-120">[Read about how Teams](https://products.office.com/microsoft-teams/group-chat-software) brings together conversations, meetings, files, Office apps, and third-party integrations—providing a single hub for teamwork in Microsoft 365 and Office 365.</span></span>

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a><span data-ttu-id="b33c3-121">手順 1.</span><span class="sxs-lookup"><span data-stu-id="b33c3-121">Step 1.</span></span> <span data-ttu-id="b33c3-122">主要な関係者に通知する</span><span class="sxs-lookup"><span data-stu-id="b33c3-122">Notify your key stakeholders</span></span>

<span data-ttu-id="b33c3-123">*(アップグレードの約 4 から 6 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-123">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="b33c3-124">上級リーダーは会社の成功に対して責任を持つテクノロジの変更について常に知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-124">Senior leaders are accountable for company success; be sure to keep them in the know about technology changes.</span></span> <span data-ttu-id="b33c3-125">アップグレード資格の通知を受け取ったユーザーや読む人がいない可能性がある場合は、アップグレードの計画を開始する前に、関係者 (CEO、IT プロ、マーケティング、ヘルプデスク のリードなど) に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-125">Because it's possible that not everyone received or read the notification of upgrade eligibility, you need to inform your stakeholders (for example, CEO, IT pros, Marketing, and helpdesk leads) before you begin planning your upgrade.</span></span>

<span data-ttu-id="b33c3-126">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-126">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-127">メールの例: 関係者とのコミュニケーション</span><span class="sxs-lookup"><span data-stu-id="b33c3-127">Sample email: stakeholder communication</span></span>](upgrade-emails-surveys.md#step-1-email)

[<span data-ttu-id="b33c3-128">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-128">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a><span data-ttu-id="b33c3-129">手順 2.</span><span class="sxs-lookup"><span data-stu-id="b33c3-129">Step 2.</span></span> <span data-ttu-id="b33c3-130">Teams に向けて組織を準備する</span><span class="sxs-lookup"><span data-stu-id="b33c3-130">Prepare your organization for Teams</span></span>

<span data-ttu-id="b33c3-131">*(アップグレードの約 4 から 6 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-131">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="b33c3-132">Teams は、IM (チャット) や会議などの互換性のある Skype for Business 機能を提供しますが、さらに多くの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-132">Teams offers compatible Skype for Business functionality—such as IM (chat) and meetings—but it can also do so much more.</span></span> <span data-ttu-id="b33c3-133">Teams は、チームワークの真のハブとして、ワークグループがプロジェクト、ファイル、会話、アプリを 1 つの場所ですべて管理できます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-133">As a true hub for teamwork, Teams enables workgroups to manage projects, files, conversations, and apps all in one location.</span></span> <span data-ttu-id="b33c3-134">既定では、Teams はすべての組織でオンになります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-134">By default, Teams is turned on for all organizations.</span></span> <span data-ttu-id="b33c3-135">組織で Teams を使用する方法を決定し、成功のために環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-135">Decide how your organization will use Teams and configure your environment for success.</span></span> 

> [!Note]
> <span data-ttu-id="b33c3-136">既存の Skype for Business のお客様は、現在のネットワーク インフラストラクチャが Teams 用に既に構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-136">As an existing Skype for Business customer, your current network infrastructure is likely already configured for Teams.</span></span> <span data-ttu-id="b33c3-137">これを確認するには、以下にリンクされている「完全な技術計画」のガイダンスに従ってください (これはオプションです)。</span><span class="sxs-lookup"><span data-stu-id="b33c3-137">To confirm this, you can follow the "Complete technical planning" guidance linked to below (this is optional).</span></span>

<span data-ttu-id="b33c3-138">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-138">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-139">Teams の概要</span><span class="sxs-lookup"><span data-stu-id="b33c3-139">Overview of Teams</span></span>](Teams-overview.md)
- [<span data-ttu-id="b33c3-140">Microsoft Teams の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b33c3-140">Get started with Microsoft Teams</span></span>](get-started-with-teams-quick-start.md)

[<span data-ttu-id="b33c3-141">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-141">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a><span data-ttu-id="b33c3-142">手順 3.</span><span class="sxs-lookup"><span data-stu-id="b33c3-142">Step 3.</span></span> <span data-ttu-id="b33c3-143">Skype for Business ユーザーを知る</span><span class="sxs-lookup"><span data-stu-id="b33c3-143">Know your Skype for Business users</span></span>

<span data-ttu-id="b33c3-144">*(アップグレードの約 4 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-144">*(About four weeks before the upgrade)*</span></span>

<span data-ttu-id="b33c3-145">Skype for Business に深く採用されているユーザーは、Teams への移行に少し時間や支援が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-145">Users who are deeply adopted on Skype for Business might need a little more time or assistance to make the transition to Teams.</span></span> <span data-ttu-id="b33c3-146">追加のサポートが必要な上位ユーザーを特定し、アップグレード後の番号に対して追跡できる使用基準計画を確立するには、時間を取って現在の Skype for Business の使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-146">Take time to review your current Skype for Business usage to identify your top users in need of additional support and to establish a usage baseline you can track against your post-upgrade numbers.</span></span>

<span data-ttu-id="b33c3-147">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-147">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-148">管理センターの Microsoft 365 レポート</span><span class="sxs-lookup"><span data-stu-id="b33c3-148">Microsoft 365 reports in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[<span data-ttu-id="b33c3-149">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-149">Return to top</span></span>](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="b33c3-150">手順 4.</span><span class="sxs-lookup"><span data-stu-id="b33c3-150">Step 4.</span></span> <span data-ttu-id="b33c3-151">Skype for Business から Teams にアップグレードするユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="b33c3-151">Notify your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="b33c3-152">*(アップグレードの約 2 ~ 3 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-152">*(About two to three weeks before the upgrade)*</span></span>

<span data-ttu-id="b33c3-153">ユーザーに十分な通知を提供することで、生産性に悪影響を与えることなく Teams に慣れる時間が与え、ユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-153">Providing ample notice to your users will give them time to get familiar with Teams without negatively affecting their productivity, resulting in a more positive user experience.</span></span> <span data-ttu-id="b33c3-154">通信を送信して、何が変化し、なぜ変化し、どのように準備できるのかを伝えます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-154">Send a communication to tell them what's changing, why it's changing, and how they can prepare for it.</span></span>

> [!Note]
> <span data-ttu-id="b33c3-155">必要に応じて、現時点で Microsoft 365 管理センターを介してユーザーの Teams を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-155">If needed, you can enable Teams for your users via the Microsoft 365 admin center at this time.</span></span>

<span data-ttu-id="b33c3-156">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-156">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-157">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="b33c3-157">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="b33c3-158">サンプル メール: Skype for Business に関するユーザーへのお知らせ</span><span class="sxs-lookup"><span data-stu-id="b33c3-158">Sample email: announcement to users about Skype for Business</span></span>](upgrade-emails-surveys.md#step-4-email)

[<span data-ttu-id="b33c3-159">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-159">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a><span data-ttu-id="b33c3-160">手順 5.</span><span class="sxs-lookup"><span data-stu-id="b33c3-160">Step 5.</span></span> <span data-ttu-id="b33c3-161">ユーザー アップグレード通知をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="b33c3-161">Activate the user upgrade notification</span></span>

<span data-ttu-id="b33c3-162">*(アップグレードの約 1 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-162">*(About one week before the upgrade)*</span></span>

<span data-ttu-id="b33c3-163">管理ポータルを介してユーザーアップグレード通知を有効にし、Skype for Business クライアントでユーザーが Skype for Business から Teams にアップグレードされるという視覚的な通知を提供することで、アップグレードのモメンタムを維持します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-163">Maintain upgrade momentum by enabling the user upgrade notification via the admin portal, providing a visual alert in the Skype for Business client that users are being upgraded from Skype for Business to Teams.</span></span>

<span data-ttu-id="b33c3-164">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-164">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-165">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="b33c3-165">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="b33c3-166">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-166">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="b33c3-167">手順 6.</span><span class="sxs-lookup"><span data-stu-id="b33c3-167">Step 6.</span></span> <span data-ttu-id="b33c3-168">Skype for Business から Teams にアップグレードするユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="b33c3-168">Remind your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="b33c3-169">*(アップグレードの約 5 日前)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-169">*(About five days before the upgrade)*</span></span>

<span data-ttu-id="b33c3-170">ユーザーは毎日の仕事に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-170">Users are busy with their daily responsibilities.</span></span> <span data-ttu-id="b33c3-171">保留中のアップグレードをユーザーに通知すると、Teams の準備に必要な手順を忘れてはならないと思い出すのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-171">Reminding them of the pending upgrade will help ensure they remember to take the steps they need to prepare for Teams.</span></span> <span data-ttu-id="b33c3-172">これは、利用可能なトレーニングと Teams の使用を開始する方法をユーザーに通知する最適な時間です。</span><span class="sxs-lookup"><span data-stu-id="b33c3-172">This is the perfect time to remind users about available training and how to get started with Teams.</span></span>

<span data-ttu-id="b33c3-173">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-173">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-174">サンプル メール: Teams の使用を開始するユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="b33c3-174">Sample email: remind users to get started with Teams</span></span>](upgrade-emails-surveys.md#step-6-email)

[<span data-ttu-id="b33c3-175">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-175">Return to top</span></span>](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a><span data-ttu-id="b33c3-176">手順 7.</span><span class="sxs-lookup"><span data-stu-id="b33c3-176">Step 7.</span></span> <span data-ttu-id="b33c3-177">ユーザーを Teams にアップグレードしましょう。</span><span class="sxs-lookup"><span data-stu-id="b33c3-177">Upgrade users to Teams!</span></span>

<span data-ttu-id="b33c3-178">*(アップグレード日)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-178">*(Upgrade Day)*</span></span>

<span data-ttu-id="b33c3-179">今日は、組織がコミュニケーションとコラボレーションのソリューションとして Teams に正式にアップグレードする日です。</span><span class="sxs-lookup"><span data-stu-id="b33c3-179">Today is the day your organization officially upgrades to Teams as your communication and collaboration solution.</span></span> <span data-ttu-id="b33c3-180">Microsoft Teams 管理センターで、共存モードを Teams のみに設定して、アップグレード スイッチを **アクティブにします**。</span><span class="sxs-lookup"><span data-stu-id="b33c3-180">In the Microsoft Teams admin center, activate the upgrade switch by setting the coexistence mode to **Teams Only**.</span></span> <span data-ttu-id="b33c3-181">(管理センターで、組織全体の **設定に移動する**  > **Teams のアップグレード**.)ユーザーは、Skype for Business クライアントで、Teams にアップグレードされたという通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-181">(In the admin center, go to **Org-wide Settings** > **Teams Upgrade**.) Users will receive a notification in their Skype for Business client that they've been upgraded to Teams.</span></span>

<span data-ttu-id="b33c3-182">すべてのユーザーがアップグレードされた後で、歓迎するメールを Teams に送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b33c3-182">We recommend that after everyone has been upgraded, you send an email welcoming them to Teams.</span></span>

<span data-ttu-id="b33c3-183">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-183">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-184">共存およびアップグレードの設定</span><span class="sxs-lookup"><span data-stu-id="b33c3-184">Set your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)
- [<span data-ttu-id="b33c3-185">サンプル メール: Teams へのユーザーのようこそ</span><span class="sxs-lookup"><span data-stu-id="b33c3-185">Sample email: welcome users to Teams</span></span>](upgrade-emails-surveys.md#step-7-email)

[<span data-ttu-id="b33c3-186">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-186">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a><span data-ttu-id="b33c3-187">手順 8.</span><span class="sxs-lookup"><span data-stu-id="b33c3-187">Step 8.</span></span> <span data-ttu-id="b33c3-188">Teams の使用状況をベースラインに対して監視する</span><span class="sxs-lookup"><span data-stu-id="b33c3-188">Monitor Teams usage against your baseline</span></span>

<span data-ttu-id="b33c3-189">*(アップグレード後約 1 週間または 2 週間後)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-189">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="b33c3-190">新しいテクノロジに合わせて調整する場合、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b33c3-190">Adjusting to a new technology can take some time.</span></span> <span data-ttu-id="b33c3-191">使用状況を確認して、ユーザーが Skype for Business と同じレベル (またはより大きいレベル) で Teams を使用している確認を行います。</span><span class="sxs-lookup"><span data-stu-id="b33c3-191">Check usage to verify that users are using Teams at the same—or greater—level as they did with Skype for Business.</span></span> <span data-ttu-id="b33c3-192">期待されたレベルで Teams を使用していないユーザーにチェックインします。</span><span class="sxs-lookup"><span data-stu-id="b33c3-192">Check in with users who aren't using Teams at expected levels.</span></span>

<span data-ttu-id="b33c3-193">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-193">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-194">使用状況データを表示する</span><span class="sxs-lookup"><span data-stu-id="b33c3-194">See usage data</span></span>](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[<span data-ttu-id="b33c3-195">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-195">Return to top</span></span>](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a><span data-ttu-id="b33c3-196">手順 9.</span><span class="sxs-lookup"><span data-stu-id="b33c3-196">Step 9.</span></span> <span data-ttu-id="b33c3-197">ユーザーの満足度を測定する</span><span class="sxs-lookup"><span data-stu-id="b33c3-197">Measure user satisfaction</span></span>

<span data-ttu-id="b33c3-198">*(アップグレード後約 1 週間または 2 週間後)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-198">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="b33c3-199">従業員の満足度は、生産性、保持、最終的にはビジネス成果に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="b33c3-199">Employee satisfaction can influence productivity, retention, and—ultimately—business outcomes.</span></span> <span data-ttu-id="b33c3-200">アップグレードに関するユーザーの感情と Teams に対する満足度を評価するために、ユーザーに話し合います。</span><span class="sxs-lookup"><span data-stu-id="b33c3-200">Reach out to your users to gauge user sentiment about the upgrade and their satisfaction with Teams.</span></span>

<span data-ttu-id="b33c3-201">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-201">**Resources:**</span></span>

- <span data-ttu-id="b33c3-202">[サンプル メール: ユーザーに対するチェックインと](upgrade-emails-surveys.md#step-9-email)[ユーザーアンケート](upgrade-emails-surveys.md#step-9-surveys)</span><span class="sxs-lookup"><span data-stu-id="b33c3-202">[Sample email: check in with users](upgrade-emails-surveys.md#step-9-email), plus [user surveys](upgrade-emails-surveys.md#step-9-surveys)</span></span>

[<span data-ttu-id="b33c3-203">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-203">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a><span data-ttu-id="b33c3-204">手順 10.</span><span class="sxs-lookup"><span data-stu-id="b33c3-204">Step 10.</span></span> <span data-ttu-id="b33c3-205">Teams で ROI を最大化する</span><span class="sxs-lookup"><span data-stu-id="b33c3-205">Maximize your ROI with Teams</span></span>

<span data-ttu-id="b33c3-206">*(進行中)*</span><span class="sxs-lookup"><span data-stu-id="b33c3-206">*(Ongoing)*</span></span>

<span data-ttu-id="b33c3-207">ユーザーが Teams での IM (チャット) と会議に快適に取り組むには、Teams の共同作業とアプリの統合を使用して、使用事例を広げ、新しいソリューションを真に最適化し、投資収益を最大化します。</span><span class="sxs-lookup"><span data-stu-id="b33c3-207">After users are comfortable with IM (chat) and meetings in Teams, encourage them to extend their use case by using Teams collaboration and app integration, truly optimizing their new solution and maximizing a return on your investment.</span></span>

<span data-ttu-id="b33c3-208">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b33c3-208">**Resources:**</span></span>

- [<span data-ttu-id="b33c3-209">サンプル メール: ユーザーに Teams をさらに探索を促す</span><span class="sxs-lookup"><span data-stu-id="b33c3-209">Sample email: encourage users to explore Teams further</span></span>](upgrade-emails-surveys.md#step-10-email)

[<span data-ttu-id="b33c3-210">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b33c3-210">Return to top</span></span>](#about-upgrade-basic)
