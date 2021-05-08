---
title: アップグレード のチェックリスト|SkypeBusiness to Teams Upgrade |基本的な手順
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この高速な 10 ステップのアクション プランに従って、基本的な設定Skype for BusinessセットアップからMicrosoft Teamsに移行します。
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
ms.openlocfilehash: d9453ad770b7ca21b5300b193cbafb932ea7645a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120528"
---
# <a name="upgrade-basic"></a><span data-ttu-id="b5ff1-103">Basic のアップグレード</span><span class="sxs-lookup"><span data-stu-id="b5ff1-103">Upgrade Basic</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="b5ff1-104">小規模な組織や、IM (チャット) および会議専用の Skype for Business Online を使用しているユーザー向けに設計された Upgrade Basic チェックリストは、Skype for Business から Teams への移行を成功に移す際のコア、推奨されるアクティビティ、関連リソースを含む高速アクション プランです。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-104">Designed for smaller organizations or those using Skype for Business Online for IM (chat) and meetings only, the Upgrade Basic checklist is an accelerated action plan that includes core, recommended activities and associated resources for implementing a successful move from Skype for Business to Teams.</span></span>

<span data-ttu-id="b5ff1-105">この 10 の簡単な手順は、アップグレードを成功するために必要なすべてを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-105">These ten easy steps provide everything you need for a successful upgrade.</span></span> <span data-ttu-id="b5ff1-106">これらは約 30 ~ 45 日で完了するように設計されています。ただし、組織のアップグレード スケジュールに基づいてタスクの完了日を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-106">They're designed to be completed in about 30 to 45 days, but you should adjust task completion dates based on your organization's upgrade schedule.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5ff1-107">Skype for Businessオンラインは 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-107">Skype for Business Online will be retired on July 31, 2021.</span></span> <span data-ttu-id="b5ff1-108">その後、Skype for Business Online サービスにアクセスしたりサポートしたりしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-108">After that time, the Skype for Business Online service will no longer be accessible or supported.</span></span> <span data-ttu-id="b5ff1-109">移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-109">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span>

<span data-ttu-id="b5ff1-110">アップグレード後Skype for Businessは何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="b5ff1-110">What happens to Skype for Business after the upgrade?</span></span> <span data-ttu-id="b5ff1-111">ユーザーが Teams にアップグレードされた後 (**Teams のみ** モード) は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="b5ff1-111">After your users are upgraded to Teams (**Teams Only** mode):</span></span>

- <span data-ttu-id="b5ff1-112">クライアントSkype for Businessが無効になり、すべてのチャットと通話がTeams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-112">Their Skype for Business client is disabled, and all chat and calls go to Teams.</span></span> <span data-ttu-id="b5ff1-113">これにより、デスクトップ上のクライアントはアンインストールされないので注意してください。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-113">Note that this will not uninstall the client on their desktops.</span></span>
- <span data-ttu-id="b5ff1-114">アップグレードSkype for Business前にスケジュールされていた会議は設計通り動作しますが、すべての新しい会議は、Teams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-114">Any Skype for Business meetings that were scheduled before the upgrade work as designed, but all new meetings are scheduled in Teams.</span></span> <span data-ttu-id="b5ff1-115">このSkype for Businessは、このプラグインでは使用Outlook。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-115">The Skype for Business plugin will no longer be available in Outlook.</span></span> 
- <span data-ttu-id="b5ff1-116">ユーザーが Skype for Business にサインインしようとして、クライアントからユーザーにアップグレードされたという通知をTeams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-116">If users try to sign in to Skype for Business, they get a notification from their client that they've been upgraded to Teams.</span></span>
- <span data-ttu-id="b5ff1-117">ユーザーは、モバイル デバイス上のSkype for Businessクライアントを手動でアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-117">Users need to manually uninstall the Skype for Business client on their mobile devices.</span></span>

<span data-ttu-id="b5ff1-118">アップグレードに関 [するその他](./faq-journey.yml) の質問については、FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-118">See our [FAQ](./faq-journey.yml) for additional questions about your upgrade.</span></span>

<span data-ttu-id="b5ff1-119">使い慣れたTeams?</span><span class="sxs-lookup"><span data-stu-id="b5ff1-119">Not familiar with Teams?</span></span> <span data-ttu-id="b5ff1-120">[Teams](https://products.office.com/microsoft-teams/group-chat-software)が会話、会議、ファイル、Office アプリ、サード パーティの統合を結び付ける方法について説明します。Microsoft 365 と Office 365 でチームワークのための単一のハブを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-120">[Read about how Teams](https://products.office.com/microsoft-teams/group-chat-software) brings together conversations, meetings, files, Office apps, and third-party integrations—providing a single hub for teamwork in Microsoft 365 and Office 365.</span></span>

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a><span data-ttu-id="b5ff1-121">手順 1.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-121">Step 1.</span></span> <span data-ttu-id="b5ff1-122">主要な関係者に通知する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-122">Notify your key stakeholders</span></span>

<span data-ttu-id="b5ff1-123">*(アップグレードの約 4 ~ 6 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-123">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="b5ff1-124">上級リーダーは、会社の成功に対して責任を持っています。テクノロジの変更について常に知り続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-124">Senior leaders are accountable for company success; be sure to keep them in the know about technology changes.</span></span> <span data-ttu-id="b5ff1-125">すべてのユーザーがアップグレードの適格性の通知を受信または読んだ可能性はないので、アップグレードの計画を開始する前に、関係者 (CEO、IT プロ、マーケティング、ヘルプデスク リードなど) に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-125">Because it's possible that not everyone received or read the notification of upgrade eligibility, you need to inform your stakeholders (for example, CEO, IT pros, Marketing, and helpdesk leads) before you begin planning your upgrade.</span></span>

<span data-ttu-id="b5ff1-126">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-126">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-127">電子メールの例: 関係者のコミュニケーション</span><span class="sxs-lookup"><span data-stu-id="b5ff1-127">Sample email: stakeholder communication</span></span>](upgrade-emails-surveys.md#step-1-email)

[<span data-ttu-id="b5ff1-128">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-128">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a><span data-ttu-id="b5ff1-129">手順 2.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-129">Step 2.</span></span> <span data-ttu-id="b5ff1-130">Teams に向けて組織を準備する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-130">Prepare your organization for Teams</span></span>

<span data-ttu-id="b5ff1-131">*(アップグレードの約 4 ~ 6 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-131">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="b5ff1-132">Teams IM (チャットSkype for Businessなど)、互換性のある機能を提供しますが、さらに多くの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-132">Teams offers compatible Skype for Business functionality—such as IM (chat) and meetings—but it can also do so much more.</span></span> <span data-ttu-id="b5ff1-133">チームワークの真のハブとして、Teamsワークグループがプロジェクト、ファイル、会話、アプリを 1 つの場所ですべて管理できます。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-133">As a true hub for teamwork, Teams enables workgroups to manage projects, files, conversations, and apps all in one location.</span></span> <span data-ttu-id="b5ff1-134">既定では、Teams はすべての組織でオンになります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-134">By default, Teams is turned on for all organizations.</span></span> <span data-ttu-id="b5ff1-135">組織でアプリケーションを使用する方法を決定Teams環境を成功に向け構成します。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-135">Decide how your organization will use Teams and configure your environment for success.</span></span> 

> [!Note]
> <span data-ttu-id="b5ff1-136">既存の顧客Skype for Business、現在のネットワーク インフラストラクチャが既に構成されている可能性Teams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-136">As an existing Skype for Business customer, your current network infrastructure is likely already configured for Teams.</span></span> <span data-ttu-id="b5ff1-137">これを確認するには、以下にリンクされている「完全な技術計画」ガイダンスに従ってください (これは省略可能です)。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-137">To confirm this, you can follow the "Complete technical planning" guidance linked to below (this is optional).</span></span>

<span data-ttu-id="b5ff1-138">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-138">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-139">Teams の概要</span><span class="sxs-lookup"><span data-stu-id="b5ff1-139">Overview of Teams</span></span>](Teams-overview.md)
- [<span data-ttu-id="b5ff1-140">Microsoft Teams の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-140">Get started with Microsoft Teams</span></span>](get-started-with-teams-quick-start.md)

[<span data-ttu-id="b5ff1-141">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-141">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a><span data-ttu-id="b5ff1-142">手順 3.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-142">Step 3.</span></span> <span data-ttu-id="b5ff1-143">自分のユーザーをSkype for Businessする</span><span class="sxs-lookup"><span data-stu-id="b5ff1-143">Know your Skype for Business users</span></span>

<span data-ttu-id="b5ff1-144">*(アップグレードの約 4 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-144">*(About four weeks before the upgrade)*</span></span>

<span data-ttu-id="b5ff1-145">アプリケーションに深く採用されているSkype for Businessユーザーは、アプリケーションへの移行にもう少し時間や支援が必要Teams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-145">Users who are deeply adopted on Skype for Business might need a little more time or assistance to make the transition to Teams.</span></span> <span data-ttu-id="b5ff1-146">追加のサポートを必要とするSkype for Businessユーザーを特定し、アップグレード後の番号に対して追跡できる使用基準を確立するために、現在の使用状況を確認する時間を取る。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-146">Take time to review your current Skype for Business usage to identify your top users in need of additional support and to establish a usage baseline you can track against your post-upgrade numbers.</span></span>

<span data-ttu-id="b5ff1-147">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-147">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-148">Microsoft 365センターでレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-148">Microsoft 365 reports in the admin center</span></span>](/microsoft-365/admin/activity-reports/activity-reports)

[<span data-ttu-id="b5ff1-149">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-149">Return to top</span></span>](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="b5ff1-150">手順 4.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-150">Step 4.</span></span> <span data-ttu-id="b5ff1-151">ユーザーが新しいバージョンから新しいバージョンにアップグレードSkype for Business通知Teams</span><span class="sxs-lookup"><span data-stu-id="b5ff1-151">Notify your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="b5ff1-152">*(アップグレードの約 2 ~ 3 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-152">*(About two to three weeks before the upgrade)*</span></span>

<span data-ttu-id="b5ff1-153">ユーザーに十分な通知を提供することで、生産性に悪影響を与えることなく Teams に慣れる時間が与え、ユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-153">Providing ample notice to your users will give them time to get familiar with Teams without negatively affecting their productivity, resulting in a more positive user experience.</span></span> <span data-ttu-id="b5ff1-154">通信を送信して、何が変化し、なぜ変化し、どのように準備できるのかを伝えます。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-154">Send a communication to tell them what's changing, why it's changing, and how they can prepare for it.</span></span>

> [!Note]
> <span data-ttu-id="b5ff1-155">必要に応じて、この時点Teams管理センターからユーザーのMicrosoft 365を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-155">If needed, you can enable Teams for your users via the Microsoft 365 admin center at this time.</span></span>

<span data-ttu-id="b5ff1-156">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-156">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-157">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-157">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="b5ff1-158">サンプルメール: ユーザーに関する通知Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b5ff1-158">Sample email: announcement to users about Skype for Business</span></span>](upgrade-emails-surveys.md#step-4-email)

[<span data-ttu-id="b5ff1-159">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-159">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a><span data-ttu-id="b5ff1-160">手順 5.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-160">Step 5.</span></span> <span data-ttu-id="b5ff1-161">ユーザー アップグレード通知をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-161">Activate the user upgrade notification</span></span>

<span data-ttu-id="b5ff1-162">*(アップグレードの約 1 週間前)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-162">*(About one week before the upgrade)*</span></span>

<span data-ttu-id="b5ff1-163">管理ポータルでユーザーのアップグレード通知を有効にすることでアップグレードの勢いを維持し、Skype for Business クライアントでユーザーが Skype for Business から Teams にアップグレードされるという視覚的なアラートを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-163">Maintain upgrade momentum by enabling the user upgrade notification via the admin portal, providing a visual alert in the Skype for Business client that users are being upgraded from Skype for Business to Teams.</span></span>

<span data-ttu-id="b5ff1-164">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-164">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-165">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-165">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="b5ff1-166">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-166">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="b5ff1-167">手順 6.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-167">Step 6.</span></span> <span data-ttu-id="b5ff1-168">ユーザーが新しいバージョンから新しいバージョンにアップグレードSkype for Business通知Teams</span><span class="sxs-lookup"><span data-stu-id="b5ff1-168">Remind your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="b5ff1-169">*(アップグレードの約 5 日前)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-169">*(About five days before the upgrade)*</span></span>

<span data-ttu-id="b5ff1-170">ユーザーは毎日の責任に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-170">Users are busy with their daily responsibilities.</span></span> <span data-ttu-id="b5ff1-171">保留中のアップグレードを通知すると、アップグレードの準備に必要な手順を忘れTeams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-171">Reminding them of the pending upgrade will help ensure they remember to take the steps they need to prepare for Teams.</span></span> <span data-ttu-id="b5ff1-172">これは、利用可能なトレーニングと、トレーニングの開始方法をユーザーに通知する最適なTeams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-172">This is the perfect time to remind users about available training and how to get started with Teams.</span></span>

<span data-ttu-id="b5ff1-173">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-173">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-174">サンプル メール: ユーザーにメールの使用を開始Teams</span><span class="sxs-lookup"><span data-stu-id="b5ff1-174">Sample email: remind users to get started with Teams</span></span>](upgrade-emails-surveys.md#step-6-email)

[<span data-ttu-id="b5ff1-175">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-175">Return to top</span></span>](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a><span data-ttu-id="b5ff1-176">手順 7.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-176">Step 7.</span></span> <span data-ttu-id="b5ff1-177">ユーザーをアップグレードしてTeams!</span><span class="sxs-lookup"><span data-stu-id="b5ff1-177">Upgrade users to Teams!</span></span>

<span data-ttu-id="b5ff1-178">*(アップグレード日)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-178">*(Upgrade Day)*</span></span>

<span data-ttu-id="b5ff1-179">今日は、組織が通信およびコラボレーション ソリューションとしてTeamsにアップグレードする日です。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-179">Today is the day your organization officially upgrades to Teams as your communication and collaboration solution.</span></span> <span data-ttu-id="b5ff1-180">管理センター Microsoft Teams、共存モードを [のみ] に設定して、アップグレード **スイッチTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-180">In the Microsoft Teams admin center, activate the upgrade switch by setting the coexistence mode to **Teams Only**.</span></span> <span data-ttu-id="b5ff1-181">(管理センターで、[組織全体]**ページに移動設定**  > **Teams アップグレード .)** ユーザーは、自分のクライアントSkype for Businessにアップグレードされたという通知を受け取Teams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-181">(In the admin center, go to **Org-wide Settings** > **Teams Upgrade**.) Users will receive a notification in their Skype for Business client that they've been upgraded to Teams.</span></span>

<span data-ttu-id="b5ff1-182">すべてのユーザーがアップグレードされた後、すべてのユーザーを歓迎する電子メールを送信Teams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-182">We recommend that after everyone has been upgraded, you send an email welcoming them to Teams.</span></span>

<span data-ttu-id="b5ff1-183">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-183">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-184">共存およびアップグレードの設定</span><span class="sxs-lookup"><span data-stu-id="b5ff1-184">Set your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)
- [<span data-ttu-id="b5ff1-185">サンプル メール: ユーザーをメールにTeams</span><span class="sxs-lookup"><span data-stu-id="b5ff1-185">Sample email: welcome users to Teams</span></span>](upgrade-emails-surveys.md#step-7-email)

[<span data-ttu-id="b5ff1-186">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-186">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a><span data-ttu-id="b5ff1-187">手順 8.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-187">Step 8.</span></span> <span data-ttu-id="b5ff1-188">ベースラインTeams使用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-188">Monitor Teams usage against your baseline</span></span>

<span data-ttu-id="b5ff1-189">*(アップグレード後約 1 ~ 2 週間)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-189">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="b5ff1-190">新しいテクノロジに合わせて調整する場合、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-190">Adjusting to a new technology can take some time.</span></span> <span data-ttu-id="b5ff1-191">使用状況を確認して、ユーザーが Teamsと同じレベル以上のレベルで使用Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-191">Check usage to verify that users are using Teams at the same—or greater—level as they did with Skype for Business.</span></span> <span data-ttu-id="b5ff1-192">期待されるレベルでユーザーを使用していないTeamsにチェックインします。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-192">Check in with users who aren't using Teams at expected levels.</span></span>

<span data-ttu-id="b5ff1-193">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-193">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-194">使用状況データを確認する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-194">See usage data</span></span>](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[<span data-ttu-id="b5ff1-195">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-195">Return to top</span></span>](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a><span data-ttu-id="b5ff1-196">手順 9.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-196">Step 9.</span></span> <span data-ttu-id="b5ff1-197">ユーザーの満足度を測定する</span><span class="sxs-lookup"><span data-stu-id="b5ff1-197">Measure user satisfaction</span></span>

<span data-ttu-id="b5ff1-198">*(アップグレード後約 1 ~ 2 週間)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-198">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="b5ff1-199">従業員の満足度は、生産性、リテンション期間、最終的にはビジネス成果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-199">Employee satisfaction can influence productivity, retention, and—ultimately—business outcomes.</span></span> <span data-ttu-id="b5ff1-200">アップグレードに関するユーザーのセンチメントと、アップグレードに対する満足度を評価するには、ユーザーにTeams。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-200">Reach out to your users to gauge user sentiment about the upgrade and their satisfaction with Teams.</span></span>

<span data-ttu-id="b5ff1-201">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-201">**Resources:**</span></span>

- <span data-ttu-id="b5ff1-202">[サンプルメール: ユーザーにチェックインし、](upgrade-emails-surveys.md#step-9-email)ユーザーアンケート [を追加する](upgrade-emails-surveys.md#step-9-surveys)</span><span class="sxs-lookup"><span data-stu-id="b5ff1-202">[Sample email: check in with users](upgrade-emails-surveys.md#step-9-email), plus [user surveys](upgrade-emails-surveys.md#step-9-surveys)</span></span>

[<span data-ttu-id="b5ff1-203">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-203">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a><span data-ttu-id="b5ff1-204">手順 10.</span><span class="sxs-lookup"><span data-stu-id="b5ff1-204">Step 10.</span></span> <span data-ttu-id="b5ff1-205">データを使用して ROI を最大化Teams</span><span class="sxs-lookup"><span data-stu-id="b5ff1-205">Maximize your ROI with Teams</span></span>

<span data-ttu-id="b5ff1-206">*(進行中)*</span><span class="sxs-lookup"><span data-stu-id="b5ff1-206">*(Ongoing)*</span></span>

<span data-ttu-id="b5ff1-207">ユーザーが Teams での IM (チャット) と会議に快適に取り組む場合は、Teams コラボレーションとアプリ統合を使用して使用事例を拡張し、新しいソリューションを真に最適化し、投資収益を最大化します。</span><span class="sxs-lookup"><span data-stu-id="b5ff1-207">After users are comfortable with IM (chat) and meetings in Teams, encourage them to extend their use case by using Teams collaboration and app integration, truly optimizing their new solution and maximizing a return on your investment.</span></span>

<span data-ttu-id="b5ff1-208">**リソース:**</span><span class="sxs-lookup"><span data-stu-id="b5ff1-208">**Resources:**</span></span>

- [<span data-ttu-id="b5ff1-209">電子メールのサンプル: ユーザーにさらに詳しいTeams勧め</span><span class="sxs-lookup"><span data-stu-id="b5ff1-209">Sample email: encourage users to explore Teams further</span></span>](upgrade-emails-surveys.md#step-10-email)

[<span data-ttu-id="b5ff1-210">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="b5ff1-210">Return to top</span></span>](#about-upgrade-basic)