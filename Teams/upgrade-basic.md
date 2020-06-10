---
title: アップグレードのチェックリスト |Skype Business から Teams へのアップグレード |基本的な手順
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この高速な10段階のアクションプランに従って、基本的な Skype for Business のセットアップから Microsoft Teams のセットアップに切り替えます。
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
ms.openlocfilehash: ef27d9faac30003edbb4c21ee7d9060d41ea454b
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666229"
---
# <a name="upgrade-basic"></a><span data-ttu-id="5437e-103">アップグレードの基本</span><span class="sxs-lookup"><span data-stu-id="5437e-103">Upgrade Basic</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="5437e-104">小規模の組織または Skype for Business Online を使った IM (チャット) および会議のみを対象として設計されています。アップグレードの基本的なチェックリストは、Skype for Business から Teams への正常な移行を実現するためのコア、推奨アクティビティ、関連リソースを含む、加速されたアクションプランです。</span><span class="sxs-lookup"><span data-stu-id="5437e-104">Designed for smaller organizations or those using Skype for Business Online for IM (chat) and meetings only, the Upgrade Basic checklist is an accelerated action plan that includes core, recommended activities and associated resources for implementing a successful move from Skype for Business to Teams.</span></span>

<span data-ttu-id="5437e-105">この10個の簡単な手順で、アップグレードを成功させるために必要なすべての操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5437e-105">These ten easy steps provide everything you need for a successful upgrade.</span></span> <span data-ttu-id="5437e-106">30 ~ 45 日後に完了するように設計されていますが、組織のアップグレードスケジュールに基づいて、タスクの完了日を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5437e-106">They're designed to be completed in about 30 to 45 days, but you should adjust task completion dates based on your organization's upgrade schedule.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5437e-107">Skype for Business Online は、2021年7月31日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="5437e-107">Skype for Business Online will be retired on July 31, 2021.</span></span> <span data-ttu-id="5437e-108">その後、Skype for Business Online サービスは、アクセスまたはサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="5437e-108">After that time, the Skype for Business Online service will no longer be accessible or supported.</span></span> <span data-ttu-id="5437e-109">移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5437e-109">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span>

<span data-ttu-id="5437e-110">アップグレード後の Skype for Business はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="5437e-110">What happens to Skype for Business after the upgrade?</span></span> <span data-ttu-id="5437e-111">ユーザーが Teams (**Teams のみ**モード) にアップグレードされた後、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5437e-111">After your users are upgraded to Teams (**Teams Only** mode):</span></span>

- <span data-ttu-id="5437e-112">Skype for Business クライアントが無効になり、すべてのチャットと通話が Teams に移動します。</span><span class="sxs-lookup"><span data-stu-id="5437e-112">Their Skype for Business client is disabled, and all chat and calls go to Teams.</span></span> <span data-ttu-id="5437e-113">これにより、デスクトップ上のクライアントがアンインストールされることはありません。</span><span class="sxs-lookup"><span data-stu-id="5437e-113">Note that this will not uninstall the client on their desktops.</span></span>
- <span data-ttu-id="5437e-114">アップグレード前にスケジュールされていた Skype for Business 会議は、設計どおりに動作しますが、すべての新しい会議は Teams でスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="5437e-114">Any Skype for Business meetings that were scheduled before the upgrade work as designed, but all new meetings are scheduled in Teams.</span></span> <span data-ttu-id="5437e-115">Skype for Business プラグインは Outlook で利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5437e-115">The Skype for Business plugin will no longer be available in Outlook.</span></span> 
- <span data-ttu-id="5437e-116">ユーザーが Skype for Business にサインインしようとすると、そのユーザーはクライアントからチームにアップグレードされたという通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5437e-116">If users try to sign in to Skype for Business, they get a notification from their client that they've been upgraded to Teams.</span></span>
- <span data-ttu-id="5437e-117">ユーザーは、モバイルデバイスで Skype for Business クライアントを手動でアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5437e-117">Users need to manually uninstall the Skype for Business client on their mobile devices.</span></span>

<span data-ttu-id="5437e-118">アップグレードに関するその他の質問については、 [FAQ](https://aka.ms/SkypeToTeams-FAQ)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5437e-118">See our [FAQ](https://aka.ms/SkypeToTeams-FAQ) for additional questions about your upgrade.</span></span>

<span data-ttu-id="5437e-119">Teams について理解していない場合</span><span class="sxs-lookup"><span data-stu-id="5437e-119">Not familiar with Teams?</span></span> <span data-ttu-id="5437e-120">ここでは、チームによる会話、会議、ファイル、Office アプリ、サードパーティの統合の[概要について説明](https://products.office.com/microsoft-teams/group-chat-software)します。これには、Microsoft 365 および Office 365 でのチームワーク用の単一のハブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5437e-120">[Read about how Teams](https://products.office.com/microsoft-teams/group-chat-software) brings together conversations, meetings, files, Office apps, and third-party integrations—providing a single hub for teamwork in Microsoft 365 and Office 365.</span></span>

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a><span data-ttu-id="5437e-121">手順1</span><span class="sxs-lookup"><span data-stu-id="5437e-121">Step 1.</span></span> <span data-ttu-id="5437e-122">主要な関係者に通知する</span><span class="sxs-lookup"><span data-stu-id="5437e-122">Notify your key stakeholders</span></span>

<span data-ttu-id="5437e-123">*(アップグレードの前に約 4 ~ 6 週間)*</span><span class="sxs-lookup"><span data-stu-id="5437e-123">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="5437e-124">シニアリーダーは、企業の成功の責任を持ちます。技術の変更については、必ず知っておいてください。</span><span class="sxs-lookup"><span data-stu-id="5437e-124">Senior leaders are accountable for company success; be sure to keep them in the know about technology changes.</span></span> <span data-ttu-id="5437e-125">アップグレードの計画を始める前に、参加者 (CEO、IT プロフェッショナル、マーケティング、ヘルプデスクの潜在顧客など) に通知する必要があるため、お客様の関係者に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5437e-125">Because it's possible that not everyone received or read the notification of upgrade eligibility, you need to inform your stakeholders (for example, CEO, IT pros, Marketing, and helpdesk leads) before you begin planning your upgrade.</span></span>

<span data-ttu-id="5437e-126">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-126">**Resources:**</span></span>

- [<span data-ttu-id="5437e-127">サンプルメール: 関係者とのコミュニケーション</span><span class="sxs-lookup"><span data-stu-id="5437e-127">Sample email: stakeholder communication</span></span>](upgrade-emails-surveys.md#step-1-email)

[<span data-ttu-id="5437e-128">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-128">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a><span data-ttu-id="5437e-129">手順2</span><span class="sxs-lookup"><span data-stu-id="5437e-129">Step 2.</span></span> <span data-ttu-id="5437e-130">Teams に向けて組織を準備する</span><span class="sxs-lookup"><span data-stu-id="5437e-130">Prepare your organization for Teams</span></span>

<span data-ttu-id="5437e-131">*(アップグレードの前に約 4 ~ 6 週間)*</span><span class="sxs-lookup"><span data-stu-id="5437e-131">*(About four to six weeks before the upgrade)*</span></span>

<span data-ttu-id="5437e-132">チームは、IM (チャット) や会議などの Skype for Business の互換性のある機能を提供していますが、その他にも多くのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5437e-132">Teams offers compatible Skype for Business functionality—such as IM (chat) and meetings—but it can also do so much more.</span></span> <span data-ttu-id="5437e-133">Teams では、チームワークグループの実際のハブとして、プロジェクト、ファイル、スレッド、アプリを1つの場所で管理できます。</span><span class="sxs-lookup"><span data-stu-id="5437e-133">As a true hub for teamwork, Teams enables workgroups to manage projects, files, conversations, and apps all in one location.</span></span> <span data-ttu-id="5437e-134">既定では、Teams はすべての組織でオンになります。</span><span class="sxs-lookup"><span data-stu-id="5437e-134">By default, Teams is turned on for all organizations.</span></span> <span data-ttu-id="5437e-135">組織でチームをどのように使用するかを決定し、成功のために環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="5437e-135">Decide how your organization will use Teams and configure your environment for success.</span></span> 

> [!Note]
> <span data-ttu-id="5437e-136">既存の Skype for Business のお客様としては、現在のネットワークインフラストラクチャが Teams 用に既に構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5437e-136">As an existing Skype for Business customer, your current network infrastructure is likely already configured for Teams.</span></span> <span data-ttu-id="5437e-137">これを確認するには、以下にリンクされている「完全な技術計画」のガイダンスに従う必要があります (これは省略可能です)。</span><span class="sxs-lookup"><span data-stu-id="5437e-137">To confirm this, you can follow the "Complete technical planning" guidance linked to below (this is optional).</span></span>

<span data-ttu-id="5437e-138">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-138">**Resources:**</span></span>

- [<span data-ttu-id="5437e-139">Teams の概要</span><span class="sxs-lookup"><span data-stu-id="5437e-139">Overview of Teams</span></span>](Teams-overview.md)
- [<span data-ttu-id="5437e-140">Microsoft Teams の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="5437e-140">Get started with Microsoft Teams</span></span>](get-started-with-teams-quick-start.md)

[<span data-ttu-id="5437e-141">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-141">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a><span data-ttu-id="5437e-142">手順3</span><span class="sxs-lookup"><span data-stu-id="5437e-142">Step 3.</span></span> <span data-ttu-id="5437e-143">Skype for Business ユーザーについて知る</span><span class="sxs-lookup"><span data-stu-id="5437e-143">Know your Skype for Business users</span></span>

<span data-ttu-id="5437e-144">*(アップグレードの4週間前)*</span><span class="sxs-lookup"><span data-stu-id="5437e-144">*(About four weeks before the upgrade)*</span></span>

<span data-ttu-id="5437e-145">Skype for Business に深く採用されているユーザーは、チームへの移行を行うために、さらに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5437e-145">Users who are deeply adopted on Skype for Business might need a little more time or assistance to make the transition to Teams.</span></span> <span data-ttu-id="5437e-146">現在の Skype for Business の使用状況を確認して、追加のサポートが必要な上位ユーザーを特定し、更新後の番号に対して追跡できる使用方法のベースラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="5437e-146">Take time to review your current Skype for Business usage to identify your top users in need of additional support and to establish a usage baseline you can track against your post-upgrade numbers.</span></span>

<span data-ttu-id="5437e-147">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-147">**Resources:**</span></span>

- [<span data-ttu-id="5437e-148">管理センターでの Microsoft 365 レポート</span><span class="sxs-lookup"><span data-stu-id="5437e-148">Microsoft 365 reports in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[<span data-ttu-id="5437e-149">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-149">Return to top</span></span>](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="5437e-150">手順4。</span><span class="sxs-lookup"><span data-stu-id="5437e-150">Step 4.</span></span> <span data-ttu-id="5437e-151">Skype for Business から Teams にアップグレードすることをユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="5437e-151">Notify your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="5437e-152">*(アップグレードの 1 ~ 3 週間前)*</span><span class="sxs-lookup"><span data-stu-id="5437e-152">*(About two to three weeks before the upgrade)*</span></span>

<span data-ttu-id="5437e-153">ユーザーに十分な通知を提供することで、チームの生産性に悪影響を与えずに、チームの理解を深めることができます。その結果、よりポジティブなユーザーエクスペリエンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="5437e-153">Providing ample notice to your users will give them time to get familiar with Teams without negatively affecting their productivity, resulting in a more positive user experience.</span></span> <span data-ttu-id="5437e-154">通信を送信して、何が変更されているか、変更される理由、準備を行う方法を伝えます。</span><span class="sxs-lookup"><span data-stu-id="5437e-154">Send a communication to tell them what's changing, why it's changing, and how they can prepare for it.</span></span>

> [!Note]
> <span data-ttu-id="5437e-155">この時点では、必要に応じて、Microsoft 365 管理センターを使用して、ユーザーのチームを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5437e-155">If needed, you can enable Teams for your users via the Microsoft 365 admin center at this time.</span></span>

<span data-ttu-id="5437e-156">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-156">**Resources:**</span></span>

- [<span data-ttu-id="5437e-157">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="5437e-157">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="5437e-158">サンプルメール: Skype for Business についてのユーザーへのお知らせ</span><span class="sxs-lookup"><span data-stu-id="5437e-158">Sample email: announcement to users about Skype for Business</span></span>](upgrade-emails-surveys.md#step-4-email)

[<span data-ttu-id="5437e-159">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-159">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a><span data-ttu-id="5437e-160">手順5</span><span class="sxs-lookup"><span data-stu-id="5437e-160">Step 5.</span></span> <span data-ttu-id="5437e-161">ユーザーアップグレード通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="5437e-161">Activate the user upgrade notification</span></span>

<span data-ttu-id="5437e-162">*(アップグレードの1週間前)*</span><span class="sxs-lookup"><span data-stu-id="5437e-162">*(About one week before the upgrade)*</span></span>

<span data-ttu-id="5437e-163">管理ポータルを使用してユーザーのアップグレード通知を有効にし、skype for business クライアントでユーザーが Skype for Business から Teams にアップグレードすることによって、アップグレードの勢いを維持します。</span><span class="sxs-lookup"><span data-stu-id="5437e-163">Maintain upgrade momentum by enabling the user upgrade notification via the admin portal, providing a visual alert in the Skype for Business client that users are being upgraded from Skype for Business to Teams.</span></span>

<span data-ttu-id="5437e-164">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-164">**Resources:**</span></span>

- [<span data-ttu-id="5437e-165">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="5437e-165">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="5437e-166">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-166">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a><span data-ttu-id="5437e-167">手順6</span><span class="sxs-lookup"><span data-stu-id="5437e-167">Step 6.</span></span> <span data-ttu-id="5437e-168">Skype for Business から Teams にアップグレードすることをユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="5437e-168">Remind your users that they'll be upgrading from Skype for Business to Teams</span></span>

<span data-ttu-id="5437e-169">*(アップグレードの5日後)*</span><span class="sxs-lookup"><span data-stu-id="5437e-169">*(About five days before the upgrade)*</span></span>

<span data-ttu-id="5437e-170">ユーザーは、毎日の責任の対象となります。</span><span class="sxs-lookup"><span data-stu-id="5437e-170">Users are busy with their daily responsibilities.</span></span> <span data-ttu-id="5437e-171">保留中のアップグレードについて通知すると、チームの準備に必要な手順を確実に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5437e-171">Reminding them of the pending upgrade will help ensure they remember to take the steps they need to prepare for Teams.</span></span> <span data-ttu-id="5437e-172">これは、利用可能なトレーニングや Teams の使用を開始する方法についてユーザーに通知するのに最適なタイミングです。</span><span class="sxs-lookup"><span data-stu-id="5437e-172">This is the perfect time to remind users about available training and how to get started with Teams.</span></span>

<span data-ttu-id="5437e-173">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-173">**Resources:**</span></span>

- [<span data-ttu-id="5437e-174">サンプルメール: Teams の使用を開始するようにユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="5437e-174">Sample email: remind users to get started with Teams</span></span>](upgrade-emails-surveys.md#step-6-email)

[<span data-ttu-id="5437e-175">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-175">Return to top</span></span>](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a><span data-ttu-id="5437e-176">手順7</span><span class="sxs-lookup"><span data-stu-id="5437e-176">Step 7.</span></span> <span data-ttu-id="5437e-177">ユーザーを Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="5437e-177">Upgrade users to Teams!</span></span>

<span data-ttu-id="5437e-178">*(アップグレード日)*</span><span class="sxs-lookup"><span data-stu-id="5437e-178">*(Upgrade Day)*</span></span>

<span data-ttu-id="5437e-179">本日は、お客様の組織がコミュニケーションとコラボレーションソリューションとしてチームに正式にアップグレードした日です。</span><span class="sxs-lookup"><span data-stu-id="5437e-179">Today is the day your organization officially upgrades to Teams as your communication and collaboration solution.</span></span> <span data-ttu-id="5437e-180">Microsoft Teams 管理センターで、[共存] モードを [**チームのみ**] に設定してアップグレードスイッチをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="5437e-180">In the Microsoft Teams admin center, activate the upgrade switch by setting the coexistence mode to **Teams Only**.</span></span> <span data-ttu-id="5437e-181">(管理センターで、[**組織全体の設定**  >  ] に移動します。**Teams のアップグレード**。)ユーザーは、Skype for Business クライアントで、チームにアップグレードされたという通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5437e-181">(In the admin center, go to **Org-wide Settings** > **Teams Upgrade**.) Users will receive a notification in their Skype for Business client that they've been upgraded to Teams.</span></span>

<span data-ttu-id="5437e-182">全員のアップグレードが完了したら、チームに歓迎するメールを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5437e-182">We recommend that after everyone has been upgraded, you send an email welcoming them to Teams.</span></span>

<span data-ttu-id="5437e-183">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-183">**Resources:**</span></span>

- [<span data-ttu-id="5437e-184">共存およびアップグレードの設定</span><span class="sxs-lookup"><span data-stu-id="5437e-184">Set your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)
- [<span data-ttu-id="5437e-185">サンプルメール: Teams へようこそ</span><span class="sxs-lookup"><span data-stu-id="5437e-185">Sample email: welcome users to Teams</span></span>](upgrade-emails-surveys.md#step-7-email)

[<span data-ttu-id="5437e-186">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-186">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a><span data-ttu-id="5437e-187">手順8</span><span class="sxs-lookup"><span data-stu-id="5437e-187">Step 8.</span></span> <span data-ttu-id="5437e-188">チームの使用状況をベースラインに対して監視する</span><span class="sxs-lookup"><span data-stu-id="5437e-188">Monitor Teams usage against your baseline</span></span>

<span data-ttu-id="5437e-189">*(アップグレード後の1週間または2週間後)*</span><span class="sxs-lookup"><span data-stu-id="5437e-189">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="5437e-190">新しいテクノロジに調整するには、時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5437e-190">Adjusting to a new technology can take some time.</span></span> <span data-ttu-id="5437e-191">使用状況を確認して、ユーザーが Skype for Business と同じレベルまたはそれ以上のレベルで Teams を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5437e-191">Check usage to verify that users are using Teams at the same—or greater—level as they did with Skype for Business.</span></span> <span data-ttu-id="5437e-192">チームを使用していないユーザーと期待されるレベルでチェックインします。</span><span class="sxs-lookup"><span data-stu-id="5437e-192">Check in with users who aren't using Teams at expected levels.</span></span>

<span data-ttu-id="5437e-193">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-193">**Resources:**</span></span>

- [<span data-ttu-id="5437e-194">利用状況データを表示する</span><span class="sxs-lookup"><span data-stu-id="5437e-194">See usage data</span></span>](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[<span data-ttu-id="5437e-195">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-195">Return to top</span></span>](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a><span data-ttu-id="5437e-196">手順9</span><span class="sxs-lookup"><span data-stu-id="5437e-196">Step 9.</span></span> <span data-ttu-id="5437e-197">ユーザー満足度の評価</span><span class="sxs-lookup"><span data-stu-id="5437e-197">Measure user satisfaction</span></span>

<span data-ttu-id="5437e-198">*(アップグレード後の1週間または2週間後)*</span><span class="sxs-lookup"><span data-stu-id="5437e-198">*(About one or two weeks after the upgrade)*</span></span>

<span data-ttu-id="5437e-199">従業員の満足度は生産性、保持度、および最終的なビジネスの結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5437e-199">Employee satisfaction can influence productivity, retention, and—ultimately—business outcomes.</span></span> <span data-ttu-id="5437e-200">ユーザーに連絡して、アップグレードについてのユーザー感情とチームとの満足度を評価する。</span><span class="sxs-lookup"><span data-stu-id="5437e-200">Reach out to your users to gauge user sentiment about the upgrade and their satisfaction with Teams.</span></span>

<span data-ttu-id="5437e-201">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-201">**Resources:**</span></span>

- <span data-ttu-id="5437e-202">[サンプルメール: ユーザーと](upgrade-emails-surveys.md#step-9-email)[ユーザーアンケート](upgrade-emails-surveys.md#step-9-surveys)をチェックインする</span><span class="sxs-lookup"><span data-stu-id="5437e-202">[Sample email: check in with users](upgrade-emails-surveys.md#step-9-email), plus [user surveys](upgrade-emails-surveys.md#step-9-surveys)</span></span>

[<span data-ttu-id="5437e-203">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-203">Return to top</span></span>](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a><span data-ttu-id="5437e-204">手順10</span><span class="sxs-lookup"><span data-stu-id="5437e-204">Step 10.</span></span> <span data-ttu-id="5437e-205">Teams で ROI を最大限に活用する</span><span class="sxs-lookup"><span data-stu-id="5437e-205">Maximize your ROI with Teams</span></span>

<span data-ttu-id="5437e-206">*現状*</span><span class="sxs-lookup"><span data-stu-id="5437e-206">*(Ongoing)*</span></span>

<span data-ttu-id="5437e-207">ユーザーがチームの IM (チャット) と会議に慣れたら、チームのグループ作業とアプリの統合を使用して、新しいソリューションの最適化と投資による収益の最大化を行うことで、ユースケースを延長することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5437e-207">After users are comfortable with IM (chat) and meetings in Teams, encourage them to extend their use case by using Teams collaboration and app integration, truly optimizing their new solution and maximizing a return on your investment.</span></span>

<span data-ttu-id="5437e-208">**参照**</span><span class="sxs-lookup"><span data-stu-id="5437e-208">**Resources:**</span></span>

- [<span data-ttu-id="5437e-209">サンプルメール: チームをより詳しく調査するようにユーザーに促します。</span><span class="sxs-lookup"><span data-stu-id="5437e-209">Sample email: encourage users to explore Teams further</span></span>](upgrade-emails-surveys.md#step-10-email)

[<span data-ttu-id="5437e-210">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="5437e-210">Return to top</span></span>](#about-upgrade-basic)
