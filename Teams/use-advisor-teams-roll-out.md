---
title: Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開を支援する
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開を計画および完了します。
ms.openlocfilehash: 63a3ae01dbe47323fd9227e65fa8c38a2d725ddf
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909473"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a><span data-ttu-id="c22b0-103">Teams のアドバイザーを使用して、Microsoft Teams の展開を支援する</span><span class="sxs-lookup"><span data-stu-id="c22b0-103">Use Advisor for Teams to help you roll out Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="c22b0-104">Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-104">Advisor for Teams (preview) walks you through your Microsoft Teams rollout.</span></span> <span data-ttu-id="c22b0-105">Office 365 テナント環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-105">It assesses your Office 365 tenant environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span> <span data-ttu-id="c22b0-106">次に、Teams のアドバイザーは、展開する各ワークロードのチャネルを備えた展開チーム (チーム内) を作成します。展開チームの各ワークロードには、各ワークロードのすべての展開タスクを含む包括的な Planner の計画が付属しています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-106">Then, Advisor for Teams creates a Deployment team (in Teams), with channels for each workload you want to roll out. Each workload in the Deployment team comes with a comprehensive Planner plan that includes all the rollout tasks for each workload.</span></span>  <span data-ttu-id="c22b0-107">この Planner プランを使用して、プロジェクト マネージャー、Teams および Office 365 の管理者、サポート担当者、導入およびユーザー準備チームなど、展開の各フェーズの責任者にタスクを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-107">Using this Planner plan, you'll assign tasks to the people responsible for each phase of the rollout - including the project manager, Teams and Office 365 admins, support people, and your adoption and user readiness team.</span></span> <span data-ttu-id="c22b0-108">各展開タスクには、タスクを正常に完了するために必要なすべてのガイダンスとリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-108">Each rollout task contains all the guidance and resources you need to successfully complete the task.</span></span>

<span data-ttu-id="c22b0-109">Teams のアドバイザーは、[Teams 管理センター](https://admin.teams.microsoft.com)の一部です。</span><span class="sxs-lookup"><span data-stu-id="c22b0-109">Advisor for Teams is part of the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="c22b0-110">Teams のアドバイザーを初めて使用するには、ダッシュボードの [**チームのワークロードの展開**] ウィジェットの [**開始**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c22b0-110">To use Advisor for Teams the first time, click the **Start** button in the **Deploying Teams workload** widget on the Dashboard.</span></span> <span data-ttu-id="c22b0-111">または、[**計画**] > [**アドバイザー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-111">Or go to **Planning** > **Advisor**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c22b0-112">Teams のアドバイザーは、Microsoft 365 Government - GCC High または DoD 展開では使用できません。</span><span class="sxs-lookup"><span data-stu-id="c22b0-112">Advisor for Teams isn't available for Microsoft 365 Government - GCC High or DoD deployments.</span></span>

<span data-ttu-id="c22b0-113">この「[Teams の展開と構成の概要](https://youtu.be/o2mlsUubIO4?t=44)」のビデオで  Teams  のアドバイザーを確認してください (Teams  のアドバイザーは 0:50-3:15 分)。</span><span class="sxs-lookup"><span data-stu-id="c22b0-113">Check out Advisor for Teams in this [Deploy & Configure Teams Intro](https://youtu.be/o2mlsUubIO4?t=44) video (Advisor for Teams is at 0:50-3:15 minutes).</span></span>

## <a name="using-advisor-for-teams-preview"></a><span data-ttu-id="c22b0-114">Teams のアドバイザーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c22b0-114">Using Advisor for Teams (preview)</span></span>

<span data-ttu-id="c22b0-115">Teams のアドバイザーを使用するために Teams 管理者である必要はありません。組織内の誰でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-115">You don't have to be a Teams admin to use Advisor for Teams - anybody in your organization can use it.</span></span> <span data-ttu-id="c22b0-116">Teams 管理センターにあるにもかかわらず、管理者以外のユーザーが Teams のアドバイザーにアクセスできるように、特別なアクセス許可を設定しました。</span><span class="sxs-lookup"><span data-stu-id="c22b0-116">We've set up special permissions so non-admin users can get to Advisor for Teams, even though it's in the Teams admin center.</span></span> <span data-ttu-id="c22b0-117">テナントの準備状況の評価を開くには、Teams 管理者、Teams サービス管理者、またはグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c22b0-117">You DO have to be a Teams admin, Teams Service Administrator, or Global Administrator to open the tenant readiness assessments.</span></span>

<span data-ttu-id="c22b0-118">Teams のアドバイザーを初めて使用する場合、Teams で展開チームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-118">The first time you use Advisor for Teams, it'll create a Deployment team for you in Teams.</span></span> <span data-ttu-id="c22b0-119">展開するワークロードごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-119">It adds channels for each workload you want to roll out.</span></span> 


## <a name="available-advisor-for-teams-plans"></a><span data-ttu-id="c22b0-120">Teams プランの利用可能なアドバイザー</span><span class="sxs-lookup"><span data-stu-id="c22b0-120">Available Advisor for Teams plans</span></span>

<span data-ttu-id="c22b0-121">Teams のアドバイザーはプレビュー段階ですが、次の 2 つの計画を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-121">While Advisor for Teams is in preview, we're providing these two plans:</span></span>

1. <span data-ttu-id="c22b0-122">チャット、チーム、チャネルおよびアプリ</span><span class="sxs-lookup"><span data-stu-id="c22b0-122">Chat, teams, channels, and apps</span></span>
    - <span data-ttu-id="c22b0-123">テナントの評価</span><span class="sxs-lookup"><span data-stu-id="c22b0-123">Tenant assessment</span></span>
    - <span data-ttu-id="c22b0-124">導入タスクを含む Planner プラン</span><span class="sxs-lookup"><span data-stu-id="c22b0-124">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="c22b0-125">Forms のユーザー アンケート</span><span class="sxs-lookup"><span data-stu-id="c22b0-125">Forms user survey</span></span>
1. <span data-ttu-id="c22b0-126">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="c22b0-126">Meetings and conferencing</span></span>
    - <span data-ttu-id="c22b0-127">テナントの評価</span><span class="sxs-lookup"><span data-stu-id="c22b0-127">Tenant assessment</span></span>
    - <span data-ttu-id="c22b0-128">導入タスクを含む Planner プラン</span><span class="sxs-lookup"><span data-stu-id="c22b0-128">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="c22b0-129">Forms のユーザー アンケート</span><span class="sxs-lookup"><span data-stu-id="c22b0-129">Forms user survey</span></span>

<span data-ttu-id="c22b0-130">チャット、チーム、チャネル、アプリ プランから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c22b0-130">We recommend that you start with the Chat, teams, channels, and apps plan.</span></span> <span data-ttu-id="c22b0-131">そのワークロードの展開が完了したら、アドバイザーに戻り、[**チャネルの追加**] をクリックして次のワークロードを開始します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-131">When you're done deploying that workload, go back to Advisor and click **Add channel** to start the next workload.</span></span> 

## <a name="tenant-assessment"></a><span data-ttu-id="c22b0-132">テナントの評価</span><span class="sxs-lookup"><span data-stu-id="c22b0-132">Tenant assessment</span></span>
<span data-ttu-id="c22b0-133">各プランには、Teams を展開する前に環境内の欠陥を特定して修復するために使用できるテナント準備状況の評価が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-133">Each plan includes a tenant readiness assessment that you can use to identify and remediate any deficiencies in your environment before you roll out Teams.</span></span> <span data-ttu-id="c22b0-134">各評価では次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-134">Here's what each assessment checks:</span></span>

### <a name="chat-teams-channels-and-apps"></a><span data-ttu-id="c22b0-135">チャット、チーム、チャネルおよびアプリ</span><span class="sxs-lookup"><span data-stu-id="c22b0-135">Chat, teams, channels, and apps</span></span>


|<span data-ttu-id="c22b0-136">評価</span><span class="sxs-lookup"><span data-stu-id="c22b0-136">Assessment</span></span>  |<span data-ttu-id="c22b0-137">確認できること</span><span class="sxs-lookup"><span data-stu-id="c22b0-137">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="c22b0-138">Teams のライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-138">Teams licenses</span></span>     |<span data-ttu-id="c22b0-139">使用可能な Teams のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-139">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="c22b0-140">Exchange のライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-140">Exchange licenses</span></span>     |<span data-ttu-id="c22b0-141">使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-141">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="c22b0-142">基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c22b0-142">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span>         |
|<span data-ttu-id="c22b0-143">SharePoint Online のライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-143">SharePoint Online licenses</span></span>     | <span data-ttu-id="c22b0-144">使用可能な SharePoint Online のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-144">Whether you have an active subscription with available SharePoint Online licenses.</span></span> <span data-ttu-id="c22b0-145">ファイル記憶域、チャネル共同作業、チャット用に、ユーザーごとに 1 つの SharePoint Online のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c22b0-145">You need one SharePoint Online license per user for file storage, channel collaboration, and chat.</span></span> 
|<span data-ttu-id="c22b0-146">ゲスト アクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="c22b0-146">Guest access enabled</span></span>     |<span data-ttu-id="c22b0-147">Teams でゲスト アクセスが有効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="c22b0-147">If guest access is turned on in Teams.</span></span> <span data-ttu-id="c22b0-148">ゲスト アクセスの Azure Active Directory 設定は確認されません。</span><span class="sxs-lookup"><span data-stu-id="c22b0-148">Azure Active Directory settings for guest access are not reviewed.</span></span>   |
|<span data-ttu-id="c22b0-149">構成済みのバニティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="c22b0-149">Vanity domain configured</span></span>     |<span data-ttu-id="c22b0-150">テナント用に @onmicrosoft.com 以外のドメインが構成されているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-150">Whether there's a non-@onmicrosoft.com domain configured for your tenant</span></span>  |
|<span data-ttu-id="c22b0-151">構成済みの Office 365 グループの名前付け基準</span><span class="sxs-lookup"><span data-stu-id="c22b0-151">Office 365 Group naming standard configured</span></span>     | <span data-ttu-id="c22b0-152">名前付け基準が Office 365 グループ用に構成されているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-152">Whether naming standards have been configured for Office 365 Groups</span></span>        |
|<span data-ttu-id="c22b0-153">構成済みの Office 365 グループの有効期限</span><span class="sxs-lookup"><span data-stu-id="c22b0-153">Office 365 Group expiration configured</span></span>     |  <span data-ttu-id="c22b0-154">グループの有効期限ポリシーが Office 365 グループに対して定義されているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-154">Whether a Group expiration policy has been defined for Office 365 Groups.</span></span> <span data-ttu-id="c22b0-155">そうでない場合、値は [なし] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-155">If not, the value is set to never.</span></span>        |
|<span data-ttu-id="c22b0-156">構成済み外部アクセス</span><span class="sxs-lookup"><span data-stu-id="c22b0-156">External access configured</span></span>     |<span data-ttu-id="c22b0-157">外部アクセスがオンになっていて、Teams の外部組織と通信できる場合。</span><span class="sxs-lookup"><span data-stu-id="c22b0-157">If external access is turned on so you can communicate with external organizations in Teams.</span></span>          |

### <a name="meetings-and-conferencing"></a><span data-ttu-id="c22b0-158">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="c22b0-158">Meetings and conferencing</span></span>


|<span data-ttu-id="c22b0-159">評価</span><span class="sxs-lookup"><span data-stu-id="c22b0-159">Assessment</span></span>  |<span data-ttu-id="c22b0-160">確認できること</span><span class="sxs-lookup"><span data-stu-id="c22b0-160">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="c22b0-161">Teams のライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-161">Teams licenses</span></span>     |<span data-ttu-id="c22b0-162">使用可能な Teams のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-162">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="c22b0-163">Exchange のライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-163">Exchange licenses</span></span>     |<span data-ttu-id="c22b0-164">使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-164">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="c22b0-165">基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c22b0-165">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span> |
|<span data-ttu-id="c22b0-166">電話会議のライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-166">Audio conferencing licenses</span></span>    |<span data-ttu-id="c22b0-167">電話会議のライセンスの有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-167">Whether you have an active subscription with Audio conferencing licenses</span></span> |
|<span data-ttu-id="c22b0-168">ストリームのライセンス</span><span class="sxs-lookup"><span data-stu-id="c22b0-168">Stream licenses</span></span>     |<span data-ttu-id="c22b0-169">会議の記録が必要な場合に使用できる、ストリームのライセンスの有効なサブスクリプションがあるかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-169">Whether you have an active subscription with Stream licenses, which can used should Meeting Recording be desired.</span></span> |
|<span data-ttu-id="c22b0-170">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="c22b0-170">Guest access</span></span>     |<span data-ttu-id="c22b0-171">Teams でゲスト アクセスが有効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="c22b0-171">If guest access is turned on in Teams.</span></span> <span data-ttu-id="c22b0-172">ゲスト アクセスの Azure Active Directory 設定は確認されません。</span><span class="sxs-lookup"><span data-stu-id="c22b0-172">Azure Active Directory settings for guest access are not reviewed.</span></span>|
|<span data-ttu-id="c22b0-173">バニティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="c22b0-173">Vanity domain</span></span>     |<span data-ttu-id="c22b0-174">テナント用に @onmicrosoft.com 以外のドメインが構成されているかどうか</span><span class="sxs-lookup"><span data-stu-id="c22b0-174">Whether there's a non-@onmicrosoft.com domain configured for your tenant.</span></span>  |
|<span data-ttu-id="c22b0-175">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="c22b0-175">External access</span></span>     |<span data-ttu-id="c22b0-176">外部アクセスがオンになっていて、Teams の外部組織と通信できる場合。</span><span class="sxs-lookup"><span data-stu-id="c22b0-176">If external access is turned on so you can communicate with external organizations in Teams.</span></span> |


### <a name="advisor-bot"></a><span data-ttu-id="c22b0-177">アドバイザー ボット</span><span class="sxs-lookup"><span data-stu-id="c22b0-177">Advisor bot</span></span>
<span data-ttu-id="c22b0-178">アドバイザーが展開チームを作成すると、アドバイザー ボットは次のメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-178">Once Advisor creates your Deployment team, the Advisor bot delivers the following message.</span></span>

><span data-ttu-id="c22b0-179">**Microsoft Teams の展開チームへようこそ!**</span><span class="sxs-lookup"><span data-stu-id="c22b0-179">**Welcome to your Deployment team for Microsoft Teams!**</span></span>
>  
><span data-ttu-id="c22b0-180">このチームの目的は、必要なすべてのリソースとプロジェクト チームに共同作業スペースを提供することにより、組織の Teams の展開について説明することです。</span><span class="sxs-lookup"><span data-stu-id="c22b0-180">The purpose of this team is to walk you through your organization's Teams rollout by giving you all the resources you need and providing a collaboration space for the project team.</span></span> <span data-ttu-id="c22b0-181">Teams のアドバイザーを使用して作成された各チャネルには、段階的な Planner プランと、展開全体で使用できる Forms のユーザー アンケートなどの他のリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-181">Each channel created using Advisor for Teams includes a step-by-step Planner plan and other resources such as a Forms users survey that can be used throughout your rollout.</span></span> <span data-ttu-id="c22b0-182">いつでも戻って、テナントの準備状況の評価を確認したり、Teams 管理センターを使用してワークロード計画を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-182">At any point, you can you go back and review the tenant readiness assessment or add additional workload plans using the Teams admin center.</span></span> 
> 
><span data-ttu-id="c22b0-183">**実施すべき内容**</span><span class="sxs-lookup"><span data-stu-id="c22b0-183">**Call to action**</span></span> 
>- <span data-ttu-id="c22b0-184">Teams または Planner を初めて使用する場合は、「[Teams のチュートリアル](https://teamsdemo.office.com/)」を確認し、「[Planner クイックスタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c22b0-184">If you're new to Teams or Planner, check out our [Teams walkthrough](https://teamsdemo.office.com/) and watch the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 
>- <span data-ttu-id="c22b0-185">Teams の展開チームを見てみます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-185">Head over to your Deployment team in Teams.</span></span> <span data-ttu-id="c22b0-186">ワークロード チャネル (チャット、チーム、チャネル、アプリなど) を選択し、[**Planner**] タブを選択して開始します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-186">Select your workload channel (for example, Chat, teams, channels, and apps), and select the **Planner** tab to get started.</span></span>
> 
><span data-ttu-id="c22b0-187">Teams のアドバイザーの詳細については、「[Teams のアドバイザーを使用して Microsoft Teams を展開する](use-advisor-teams-roll-out.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c22b0-187">To learn more about Advisor for Teams, read [Use Advisor for Teams to roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="c22b0-188">Teams のアドバイザー ボットは、展開チームにウェルカム メッセージを送信するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-188">The Advisor for Teams Bot is only used to send a welcome message to your Deployment team.</span></span> <span data-ttu-id="c22b0-189">追加のデータは収集されません。</span><span class="sxs-lookup"><span data-stu-id="c22b0-189">No additional data is collected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c22b0-190">Teams のアドバイザー ボットは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-190">The Advisor for Teams bot is enabled by default.</span></span> <span data-ttu-id="c22b0-191">Teams のアドバイザーを使用または使用する予定の場合は、無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="c22b0-191">Do not disable it if you use or plan on using Advisor for Teams.</span></span>


## <a name="frequently-asked-questions"></a><span data-ttu-id="c22b0-192">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c22b0-192">Frequently asked questions</span></span>
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a><span data-ttu-id="c22b0-193">Teams のアドバイザーのライセンス要件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-193">What are the licensing requirements for Advisor for Teams?</span></span>
<span data-ttu-id="c22b0-194">Teams 用のライセンスにされる以外に、追加のライセンス要件はありません。</span><span class="sxs-lookup"><span data-stu-id="c22b0-194">There are no additional licensing requirements other than being licensed for Teams.</span></span>

### <a name="can-i-delete-the-deployment-team"></a><span data-ttu-id="c22b0-195">展開チームを削除できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-195">Can I delete the Deployment team?</span></span>
<span data-ttu-id="c22b0-196">Teams のアドバイザーが展開チームを作成した後、他のチームと同様にチームを管理できます。これには削除機能も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-196">After Advisor for Teams has created your Deployment team, manage the team like any other team - including the ability to delete it.</span></span> <span data-ttu-id="c22b0-197">Teams 管理センターを使用してチームを削除しない場合、チームの存在が報告されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c22b0-197">Be aware that, if you don't delete the team by using the Teams admin center, it will be reported that the team exists.</span></span>

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a><span data-ttu-id="c22b0-198">展開チームでチャネルを追加または削除できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-198">Can I add or remove channels in the Deployment team?</span></span>
<span data-ttu-id="c22b0-199">はい。展開チームが作成されたら、他のチームと同じ方法でチャネルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-199">Yes, once the Deployment team has been created, you'll manage the channels the same way as any other team.</span></span>

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a><span data-ttu-id="c22b0-200">展開チームでプロジェクト チームのメンバーを追加または削除できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-200">Can I add or remove project team members in the Deployment team?</span></span>
<span data-ttu-id="c22b0-201">はい。展開チームが作成されたら、他のチームと同じ方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-201">Yes, once the Deployment team has been created, you'll manage it the same way as any other team.</span></span>

### <a name="can-i-modify-the-planner-plans"></a><span data-ttu-id="c22b0-202">Planner プランを変更できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-202">Can I modify the Planner plans?</span></span>
<span data-ttu-id="c22b0-203">はい。Teams のアドバイザーが展開チームを作成した後、Teams の展開を最適にサポートするために Planner プランを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c22b0-203">Yes, after Advisor for Teams has created your Deployment team, you should update the Planner plan so it best supports your Teams rollout.</span></span> <span data-ttu-id="c22b0-204">他の Planner プランと同様に、バケット、タスク、タスク詳細など、何でも変更できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-204">You can modify anything - buckets, tasks, task details - just like any other Planner plan.</span></span>


### <a name="can-i-modify-the-forms-survey"></a><span data-ttu-id="c22b0-205">Forms アンケートを変更できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-205">Can I modify the Forms survey?</span></span>
<span data-ttu-id="c22b0-206">はい。Teams のアドバイザーが展開チームを作成した後、必要に応じて Forms アンケートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-206">Yes, after Advisor for Teams has created your Deployment team, you can modify the Forms survey as needed.</span></span>

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a><span data-ttu-id="c22b0-207">Teams のアドバイザーは自分の組織についてどのような情報を収集しますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-207">What information is Advisor for Teams collecting about my organization?</span></span>
<span data-ttu-id="c22b0-208">Teams のアドバイザーは、非 EUII (エンド ユーザー識別情報) の収集に関する同意を要求します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-208">Advisor for Teams requests your agreement to collecting non-EUII (end user identifying information).</span></span> <span data-ttu-id="c22b0-209">収集される情報はテレメトリーの形式であり、Teams のアドバイザーがどの程度成果を上げているのか、改善すべきところはどこなのか​​について、Microsoft にフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-209">The information that is collected is in the form of telemetry that provides feedback to Microsoft on how well Advisor for Teams is driving successful outcomes and where it may need to be improved.</span></span> <span data-ttu-id="c22b0-210">このデータは、Microsoft が展開を支援するために組織と積極的に連携する機会を特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-210">This same data is used to identify opportunities for Microsoft to proactively engage with your organization in an effort to assist with your deployment.</span></span>

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a><span data-ttu-id="c22b0-211">FastTrack で Teams のアドバイザーを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-211">Can I use Advisor for Teams with FastTrack?</span></span>
<span data-ttu-id="c22b0-212">はい。FastTrack では、Teams の展開を検討しているすべての顧客に対して Teams のアドバイザーを活用しています。</span><span class="sxs-lookup"><span data-stu-id="c22b0-212">Yes, FastTrack leverages Advisor for Teams for all customers looking to deploy Teams.</span></span> <span data-ttu-id="c22b0-213">FastTrack は、Teams のアドバイザー (必要な場合) を使用して展開チームの初期セットアップを支援し、Teams の展開中に特定のトピックに関する必要に応じたサポートも提供します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-213">They can assist with the initial setup of your Deployment team using Advisor for Teams (if required) and also provide as-needed support on specific topics during your Teams rollout.</span></span>

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a><span data-ttu-id="c22b0-214">パートナーで Teams のアドバイザーを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-214">Can I use Advisor for Teams with a partner?</span></span>
<span data-ttu-id="c22b0-215">はい。Teams の展開に展開パートナーを使用しながら、Teams のアドバイザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-215">Yes, you can use Advisor for Teams while also using a deployment partner for your Teams deployment.</span></span> <span data-ttu-id="c22b0-216">パートナーが CSP であり、顧客の代わりにテナントを管理している場合、Teams のアドバイザーを使用して展開チームを作成し、プロジェクト全体の実行を支援できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-216">If your partner is a CSP and manages your tenant on your behalf, they can use Advisor for Teams to create your Deployment team and assist you with executing the overall project.</span></span> <span data-ttu-id="c22b0-217">さらに、展開チームにゲストとしてそれらの個人を追加して、プロジェクト チーム全体のメンバーとして参加できるようにすることで、パートナーと連携できます。</span><span class="sxs-lookup"><span data-stu-id="c22b0-217">Additionally, you can work with any partner by adding those individuals as guests in your Deployment team, to allow them to participate as a member of the overall project team.</span></span>

### <a name="how-do-i-use-planner"></a><span data-ttu-id="c22b0-218">Planner を使用するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-218">How do I use Planner?</span></span>
<span data-ttu-id="c22b0-219">「[Microsoft Planner のヘルプ](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)」と「[Planner のクイック スタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c22b0-219">Check out [Microsoft Planner help](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) and the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 

### <a name="how-do-i-use-forms"></a><span data-ttu-id="c22b0-220">Forms を使用するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="c22b0-220">How do I use Forms?</span></span>
<span data-ttu-id="c22b0-221">「[Forms ヘルプ センター](https://support.office.com/forms)」に移動します。</span><span class="sxs-lookup"><span data-stu-id="c22b0-221">Go to the [Forms help center](https://support.office.com/forms).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c22b0-222">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c22b0-222">Related topics</span></span>

[<span data-ttu-id="c22b0-223">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="c22b0-223">How to roll out Teams</span></span>](How-to-roll-out-teams.md)
