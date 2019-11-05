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
ms.openlocfilehash: 13c76c61a99869459c0dabcffedc45e06f6fd42e
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931815"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a><span data-ttu-id="3afc1-103">Teams のアドバイザーを使用して、Microsoft Teams の展開を支援する</span><span class="sxs-lookup"><span data-stu-id="3afc1-103">Use Advisor for Teams to help you roll out Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="3afc1-104">Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-104">Advisor for Teams (preview) walks you through your Microsoft Teams rollout.</span></span> <span data-ttu-id="3afc1-105">Office 365 テナント環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-105">It assesses your Office 365 tenant environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span> <span data-ttu-id="3afc1-106">次に、Teams のアドバイザーは、展開する各ワークロードのチャネルを備えたサービス管理チーム (チーム内) を作成します。サービス管理チームの各ワークロードには、各ワークロードのすべての展開タスクを含む包括的な Planner の計画が付属しています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-106">Then, Advisor for Teams creates a Service management team (in Teams), with channels for each workload you want to roll out. Each workload in the Service management team comes with a comprehensive Planner plan that includes all the rollout tasks for each workload.</span></span>  <span data-ttu-id="3afc1-107">この Planner プランを使用して、プロジェクト マネージャー、Teams および Office 365 の管理者、サポート担当者、導入およびユーザー準備チームなど、展開の各フェーズの責任者にタスクを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-107">Using this Planner plan, you'll assign tasks to the people responsible for each phase of the rollout - including the project manager, Teams and Office 365 admins, support people, and your adoption and user readiness team.</span></span> <span data-ttu-id="3afc1-108">各展開タスクには、タスクを正常に完了するために必要なすべてのガイダンスとリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-108">Each rollout task contains all the guidance and resources you need to successfully complete the task.</span></span>

<span data-ttu-id="3afc1-109">Teams のアドバイザーは、[Teams 管理センター](https://admin.teams.microsoft.com)の一部です。</span><span class="sxs-lookup"><span data-stu-id="3afc1-109">Advisor for Teams is part of the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="3afc1-110">Teams のアドバイザーを初めて使用するには、ダッシュボードの [**チームのワークロードの展開**] ウィジェットの [**開始**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afc1-110">To use Advisor for Teams the first time, click the **Start** button in the **Deploying Teams workload** widget on the Dashboard.</span></span> <span data-ttu-id="3afc1-111">または、[**計画**] > [**アドバイザー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-111">Or go to **Planning** > **Advisor**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3afc1-112">Teams のアドバイザーは、Microsoft 365 Government - GCC High または DoD 展開では使用できません。</span><span class="sxs-lookup"><span data-stu-id="3afc1-112">Advisor for Teams isn't available for Microsoft 365 Government - GCC High or DoD deployments.</span></span>

## <a name="using-advisor-for-teams-preview"></a><span data-ttu-id="3afc1-113">Teams のアドバイザーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3afc1-113">Using Advisor for Teams (preview)</span></span>

<span data-ttu-id="3afc1-114">Teams のアドバイザーを使用するために Teams 管理者である必要はありません。組織内の誰でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-114">You don't have to be a Teams admin to use Advisor for Teams - anybody in your organization can use it.</span></span> <span data-ttu-id="3afc1-115">Teams 管理センターにあるにもかかわらず、管理者以外のユーザーが Teams のアドバイザーにアクセスできるように、特別なアクセス許可を設定しました。</span><span class="sxs-lookup"><span data-stu-id="3afc1-115">We've set up special permissions so non-admin users can get to Advisor for Teams, even though it's in the Teams admin center.</span></span> <span data-ttu-id="3afc1-116">テナントの準備状況の評価を開くには、Teams 管理者、Teams サービス管理者、またはグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afc1-116">You DO have to be a Teams admin, Teams Service Administrator, or Global Administrator to open the tenant readiness assessments.</span></span>

<span data-ttu-id="3afc1-117">Teams のアドバイザーを初めて使用する場合、Teams でサービス管理チームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-117">The first time you use Advisor for Teams, it'll create a Service management team for you in Teams.</span></span> <span data-ttu-id="3afc1-118">展開するワークロードごとにチャネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-118">It adds channels for each workload you want to roll out.</span></span> 


## <a name="available-advisor-for-teams-plans"></a><span data-ttu-id="3afc1-119">Teams プランの利用可能なアドバイザー</span><span class="sxs-lookup"><span data-stu-id="3afc1-119">Available Advisor for Teams plans</span></span>

<span data-ttu-id="3afc1-120">Teams のアドバイザーはプレビュー段階ですが、次の 2 つの計画を提供しています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-120">While Advisor for Teams is in preview, we're providing these two plans:</span></span>

1. <span data-ttu-id="3afc1-121">チャット、チーム、チャネルおよびアプリ</span><span class="sxs-lookup"><span data-stu-id="3afc1-121">Chat, teams, channels, and apps</span></span>
    - <span data-ttu-id="3afc1-122">テナントの評価</span><span class="sxs-lookup"><span data-stu-id="3afc1-122">Tenant assessment</span></span>
    - <span data-ttu-id="3afc1-123">導入タスクを含む Planner プラン</span><span class="sxs-lookup"><span data-stu-id="3afc1-123">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="3afc1-124">Forms のユーザー アンケート</span><span class="sxs-lookup"><span data-stu-id="3afc1-124">Forms user survey</span></span>
1. <span data-ttu-id="3afc1-125">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="3afc1-125">Meetings and conferencing</span></span>
    - <span data-ttu-id="3afc1-126">テナントの評価</span><span class="sxs-lookup"><span data-stu-id="3afc1-126">Tenant assessment</span></span>
    - <span data-ttu-id="3afc1-127">導入タスクを含む Planner プラン</span><span class="sxs-lookup"><span data-stu-id="3afc1-127">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="3afc1-128">Forms のユーザー アンケート</span><span class="sxs-lookup"><span data-stu-id="3afc1-128">Forms user survey</span></span>

<span data-ttu-id="3afc1-129">チャット、チーム、チャネル、アプリ プランから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3afc1-129">We recommend that you start with the Chat, teams, channels, and apps plan.</span></span> <span data-ttu-id="3afc1-130">そのワークロードの展開が完了したら、アドバイザーに戻り、[**チャネルの追加**] をクリックして次のワークロードを開始します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-130">When you're done deploying that workload, go back to Advisor and click **Add channel** to start the next workload.</span></span> 

## <a name="tenant-assessment"></a><span data-ttu-id="3afc1-131">テナントの評価</span><span class="sxs-lookup"><span data-stu-id="3afc1-131">Tenant assessment</span></span>
<span data-ttu-id="3afc1-132">各プランには、Teams を展開する前に環境内の欠陥を特定して修復するために使用できるテナント準備状況の評価が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-132">Each plan includes a tenant readiness assessment that you can use to identify and remediate any deficiencies in your environment before you roll out Teams.</span></span> <span data-ttu-id="3afc1-133">各評価では次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-133">Here's what each assessment checks:</span></span>

### <a name="chat-teams-channels-and-apps"></a><span data-ttu-id="3afc1-134">チャット、チーム、チャネルおよびアプリ</span><span class="sxs-lookup"><span data-stu-id="3afc1-134">Chat, teams, channels, and apps</span></span>


|<span data-ttu-id="3afc1-135">評価</span><span class="sxs-lookup"><span data-stu-id="3afc1-135">Assessment</span></span>  |<span data-ttu-id="3afc1-136">確認できること</span><span class="sxs-lookup"><span data-stu-id="3afc1-136">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="3afc1-137">Teams のライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-137">Assign Teams licenses</span></span>     |<span data-ttu-id="3afc1-138">使用可能な Teams のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-138">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="3afc1-139">Exchange のライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-139">Exchange licenses</span></span>     |<span data-ttu-id="3afc1-140">使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-140">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="3afc1-141">基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3afc1-141">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span>         |
|<span data-ttu-id="3afc1-142">SharePoint Online のライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-142">SharePoint Online licenses</span></span>     | <span data-ttu-id="3afc1-143">使用可能な SharePoint Online のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-143">Whether you have an active subscription with available SharePoint Online licenses.</span></span> <span data-ttu-id="3afc1-144">ファイル記憶域、チャネル共同作業、チャット用に、ユーザーごとに 1 つの SharePoint Online のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3afc1-144">You need one SharePoint Online license per user for file storage, channel collaboration, and chat.</span></span> 
|<span data-ttu-id="3afc1-145">ゲスト アクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="3afc1-145">Guest access enabled</span></span>     |<span data-ttu-id="3afc1-146">Teams でゲスト アクセスが有効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="3afc1-146">If guest access is turned on in Teams.</span></span> <span data-ttu-id="3afc1-147">ゲスト アクセスの Azure Active Directory 設定は確認されません。</span><span class="sxs-lookup"><span data-stu-id="3afc1-147">Azure Active Directory settings for guest access are not reviewed.</span></span>   |
|<span data-ttu-id="3afc1-148">構成済みのバニティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="3afc1-148">Vanity domain configured</span></span>     |<span data-ttu-id="3afc1-149">テナント用に @onmicrosoft.com 以外のドメインが構成されているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-149">Whether there's a non-@onmicrosoft.com domain configured for your tenant</span></span>  |
|<span data-ttu-id="3afc1-150">構成済みの Office 365 グループの名前付け基準</span><span class="sxs-lookup"><span data-stu-id="3afc1-150">Office 365 Group naming standard configured</span></span>     | <span data-ttu-id="3afc1-151">名前付け基準が Office 365 グループ用に構成されているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-151">Whether naming standards have been configured for Office 365 Groups</span></span>        |
|<span data-ttu-id="3afc1-152">構成済みの Office 365 グループの有効期限</span><span class="sxs-lookup"><span data-stu-id="3afc1-152">Office 365 Group expiration configured</span></span>     |  <span data-ttu-id="3afc1-153">グループの有効期限ポリシーが Office 365 グループに対して定義されているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-153">Whether a Group expiration policy has been defined for Office 365 Groups.</span></span> <span data-ttu-id="3afc1-154">そうでない場合、値は [なし] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-154">If not, the value is set to never.</span></span>        |
|<span data-ttu-id="3afc1-155">構成済み外部アクセス</span><span class="sxs-lookup"><span data-stu-id="3afc1-155">External access configured</span></span>     |<span data-ttu-id="3afc1-156">外部アクセスがオンになっていて、Teams の外部組織と通信できる場合。</span><span class="sxs-lookup"><span data-stu-id="3afc1-156">If external access is turned on so you can communicate with external organizations in Teams.</span></span>          |

### <a name="meetings-and-conferencing"></a><span data-ttu-id="3afc1-157">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="3afc1-157">Meetings and conferencing</span></span>


|<span data-ttu-id="3afc1-158">評価</span><span class="sxs-lookup"><span data-stu-id="3afc1-158">Assessment</span></span>  |<span data-ttu-id="3afc1-159">確認できること</span><span class="sxs-lookup"><span data-stu-id="3afc1-159">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="3afc1-160">Teams のライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-160">Assign Teams licenses</span></span>     |<span data-ttu-id="3afc1-161">使用可能な Teams のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-161">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="3afc1-162">Exchange のライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-162">Exchange licenses</span></span>     |<span data-ttu-id="3afc1-163">使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-163">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="3afc1-164">基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3afc1-164">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span> |
|<span data-ttu-id="3afc1-165">電話会議のライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-165">Audio conferencing licenses</span></span>    |<span data-ttu-id="3afc1-166">電話会議のライセンスの有効なサブスクリプションを所有しているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-166">Whether you have an active subscription with Audio conferencing licenses</span></span> |
|<span data-ttu-id="3afc1-167">ストリームのライセンス</span><span class="sxs-lookup"><span data-stu-id="3afc1-167">Stream licenses</span></span>     |<span data-ttu-id="3afc1-168">会議の記録が必要な場合に使用できる、ストリームのライセンスの有効なサブスクリプションがあるかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-168">Whether you have an active subscription with Stream licenses, which can used should Meeting Recording be desired.</span></span> |
|<span data-ttu-id="3afc1-169">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="3afc1-169">Guest access</span></span>     |<span data-ttu-id="3afc1-170">Teams でゲスト アクセスが有効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="3afc1-170">If guest access is turned on in Teams.</span></span> <span data-ttu-id="3afc1-171">ゲスト アクセスの Azure Active Directory 設定は確認されません。</span><span class="sxs-lookup"><span data-stu-id="3afc1-171">Azure Active Directory settings for guest access are not reviewed.</span></span>|
|<span data-ttu-id="3afc1-172">バニティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="3afc1-172">Vanity domain</span></span>     |<span data-ttu-id="3afc1-173">テナント用に @onmicrosoft.com 以外のドメインが構成されているかどうか</span><span class="sxs-lookup"><span data-stu-id="3afc1-173">Whether there's a non-@onmicrosoft.com domain configured for your tenant.</span></span>  |
|<span data-ttu-id="3afc1-174">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="3afc1-174">External access</span></span>     |<span data-ttu-id="3afc1-175">外部アクセスがオンになっていて、Teams の外部組織と通信できる場合。</span><span class="sxs-lookup"><span data-stu-id="3afc1-175">If external access is turned on so you can communicate with external organizations in Teams.</span></span> |


### <a name="advisor-bot"></a><span data-ttu-id="3afc1-176">アドバイザー ボット</span><span class="sxs-lookup"><span data-stu-id="3afc1-176">Advisor bot</span></span>
<span data-ttu-id="3afc1-177">アドバイザーがサービス管理チームを作成すると、アドバイザー ボットは次のメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-177">Once Advisor creates your Service management team, the Advisor bot delivers the following message.</span></span>

><span data-ttu-id="3afc1-178">**Microsoft Teams のサービス管理チームへようこそ!**</span><span class="sxs-lookup"><span data-stu-id="3afc1-178">**Welcome to your Service management team for Microsoft Teams!**</span></span>
>  
><span data-ttu-id="3afc1-179">このチームの目的は、必要なすべてのリソースとプロジェクト チームに共同作業スペースを提供することにより、組織の Teams の展開について説明することです。</span><span class="sxs-lookup"><span data-stu-id="3afc1-179">The purpose of this team is to walk you through your organization's Teams rollout by giving you all the resources you need and providing a collaboration space for the project team.</span></span> <span data-ttu-id="3afc1-180">Teams のアドバイザーを使用して作成された各チャネルには、段階的な Planner プランと、展開全体で使用できる Forms のユーザー アンケートなどの他のリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-180">Each channel created using Advisor for Teams includes a step-by-step Planner plan and other resources such as a Forms users survey that can be used throughout your rollout.</span></span> <span data-ttu-id="3afc1-181">いつでも戻って、テナントの準備状況の評価を確認したり、Teams 管理センターを使用してワークロード計画を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-181">At any point, you can you go back and review the tenant readiness assessment or add additional workload plans using the Teams admin center.</span></span> 
> 
><span data-ttu-id="3afc1-182">**実施すべき内容**</span><span class="sxs-lookup"><span data-stu-id="3afc1-182">**Call to action:**</span></span> 
>- <span data-ttu-id="3afc1-183">Teams または Planner を初めて使用する場合は、「[Teams のチュートリアル](https://teamsdemo.office.com/)」を確認し、「[Planner クイックスタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3afc1-183">If you're new to Teams or Planner, check out our [Teams walkthrough](https://teamsdemo.office.com/) and watch the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 
>- <span data-ttu-id="3afc1-184">Teams のサービス管理チームを見てみます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-184">Head over to your Service management team in Teams.</span></span> <span data-ttu-id="3afc1-185">ワークロード チャネル (チャット、チーム、チャネル、アプリなど) を選択し、[**Planner**] タブを選択して開始します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-185">Select your workload channel (for example, Chat, teams, channels, and apps), and select the **Planner** tab to get started.</span></span>
> 
><span data-ttu-id="3afc1-186">Teams のアドバイザーの詳細については、「[Teams のアドバイザーを使用して Microsoft Teams を展開する](use-advisor-teams-roll-out.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3afc1-186">To learn more about Advisor for Teams, read [Use Advisor for Teams to roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="3afc1-187">Teams のアドバイザー ボットは、サービス管理チームにウェルカム メッセージを送信するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-187">The Advisor for Teams Bot is only used to send a welcome message to your service management team.</span></span> <span data-ttu-id="3afc1-188">追加のデータは収集されません。</span><span class="sxs-lookup"><span data-stu-id="3afc1-188">No additional data is collected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3afc1-189">Teams のアドバイザー ボットは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-189">The Advisor for Teams bot is enabled by default.</span></span> <span data-ttu-id="3afc1-190">Teams のアドバイザーを使用または使用する予定の場合は、無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="3afc1-190">Do not disable it if you use or plan on using Advisor for Teams.</span></span>


## <a name="frequently-asked-questions"></a><span data-ttu-id="3afc1-191">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3afc1-191">Frequently asked questions</span></span>
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a><span data-ttu-id="3afc1-192">Teams のアドバイザーのライセンス要件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-192">What are the licensing requirements for Advisor for Teams?</span></span>
<span data-ttu-id="3afc1-193">Teams 用のライセンスにされる以外に、追加のライセンス要件はありません。</span><span class="sxs-lookup"><span data-stu-id="3afc1-193">There are no additional licensing requirements other than being licensed for Teams.</span></span>

### <a name="can-i-delete-the-service-management-team"></a><span data-ttu-id="3afc1-194">サービス管理チームを削除できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-194">Can I delete the Service management team?</span></span>
<span data-ttu-id="3afc1-195">Teams のアドバイザーがサービス管理チームを作成した後、他のチームと同様にチームを管理できます。これには削除機能も含まれます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-195">After Advisor for Teams has created your Service management team, manage the team like any other team - including the ability to delete it.</span></span> <span data-ttu-id="3afc1-196">Teams 管理センターを使用してチームを削除しない場合、チームの存在が報告されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3afc1-196">Be aware that, if you don't delete the team by using the Teams admin center, it will be reported that the team exists.</span></span>

### <a name="can-i-add-or-remove-channels-in-the-service-management-team"></a><span data-ttu-id="3afc1-197">サービス管理チームでチャネルを追加または削除できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-197">Can I add or remove channels in the Service management team?</span></span>
<span data-ttu-id="3afc1-198">はい。サービス管理チームが作成されたら、他のチームと同じ方法でチャネルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-198">Yes, once the Service management team has been created, you'll manage the channels the same way as any other team.</span></span>

### <a name="can-i-add-or-remove-project-team-members-in-the-service-management-team"></a><span data-ttu-id="3afc1-199">サービス管理チームでプロジェクト チームのメンバーを追加または削除できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-199">Can I add or remove project team members in the Service management team?</span></span>
<span data-ttu-id="3afc1-200">はい。サービス管理チームが作成されたら、他のチームと同じ方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-200">Yes, once the Service management team has been created, you'll manage it the same way as any other team.</span></span>

### <a name="can-i-modify-the-planner-plans"></a><span data-ttu-id="3afc1-201">Planner プランを変更できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-201">Can I modify the Planner plans?</span></span>
<span data-ttu-id="3afc1-202">はい。Teams のアドバイザーがサービス管理チームを作成した後、Teams の展開を最適にサポートするために Planner プランを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afc1-202">Yes, after Advisor for Teams has created your Service management team, you should update the Planner plan so it best supports your Teams rollout.</span></span> <span data-ttu-id="3afc1-203">他の Planner プランと同様に、バケット、タスク、タスク詳細など、何でも変更できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-203">You can modify anything - buckets, tasks, task details - just like any other Planner plan.</span></span>


### <a name="can-i-modify-the-forms-survey"></a><span data-ttu-id="3afc1-204">Forms アンケートを変更できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-204">Can I modify the Forms survey?</span></span>
<span data-ttu-id="3afc1-205">はい。Teams のアドバイザーがサービス管理チームを作成した後、必要に応じて Forms アンケートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-205">Yes, after Advisor for Teams has created your Service management team, you can modify the Forms survey as needed.</span></span>

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a><span data-ttu-id="3afc1-206">Teams のアドバイザーは自分の組織についてどのような情報を収集しますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-206">What information is Advisor for Teams collecting about my organization?</span></span>
<span data-ttu-id="3afc1-207">Teams のアドバイザーは、非 EUII (エンド ユーザー識別情報) の収集に関する同意を要求します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-207">Advisor for Teams requests your agreement to collecting non-EUII (end user identifying information).</span></span> <span data-ttu-id="3afc1-208">収集される情報はテレメトリーの形式であり、Teams のアドバイザーがどの程度成果を上げているのか、改善すべきところはどこなのか​​について、Microsoft にフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-208">The information that is collected is in the form of telemetry that provides feedback to Microsoft on how well Advisor for Teams is driving successful outcomes and where it may need to be improved.</span></span> <span data-ttu-id="3afc1-209">このデータは、Microsoft が展開を支援するために組織と積極的に連携する機会を特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-209">This same data is used to identify opportunities for Microsoft to proactively engage with your organization in an effort to assist with your deployment.</span></span>

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a><span data-ttu-id="3afc1-210">FastTrack で Teams のアドバイザーを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-210">Can I use Advisor for Teams with FastTrack?</span></span>
<span data-ttu-id="3afc1-211">はい。FastTrack では、Teams の展開を検討しているすべての顧客に対して Teams のアドバイザーを活用しています。</span><span class="sxs-lookup"><span data-stu-id="3afc1-211">Yes, FastTrack leverages Advisor for Teams for all customers looking to deploy Teams.</span></span> <span data-ttu-id="3afc1-212">FastTrack は、Teams のアドバイザー (必要な場合) を使用してサービス管理チームの初期セットアップを支援し、Teams の展開中に特定のトピックに関する必要に応じたサポートも提供します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-212">They can assist with the initial setup of your Service management team using Advisor for Teams (if required) and also provide as-needed support on specific topics during your Teams rollout.</span></span>

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a><span data-ttu-id="3afc1-213">パートナーで Teams のアドバイザーを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-213">Can I use Advisor for Teams with a partner?</span></span>
<span data-ttu-id="3afc1-214">はい。Teams の展開に展開パートナーを使用しながら、Teams のアドバイザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-214">Yes, you can use Advisor for Teams while also using a deployment partner for your Teams deployment.</span></span> <span data-ttu-id="3afc1-215">パートナーが CSP であり、顧客の代わりにテナントを管理している場合、Teams のアドバイザーを使用してサービス管理チームを作成し、プロジェクト全体の実行を支援できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-215">If your partner is a CSP and manages your tenant on your behalf, they can use Advisor for Teams to create your Service management team and assist you with executing the overall project.</span></span> <span data-ttu-id="3afc1-216">さらに、サービス管理チームにゲストとしてそれらの個人を追加して、プロジェクト チーム全体のメンバーとして参加できるようにすることで、パートナーと連携できます。</span><span class="sxs-lookup"><span data-stu-id="3afc1-216">Additionally, you can work with any partner by adding those individuals as guests in your Service management team, to allow them to participate as a member of the overall project team.</span></span>

### <a name="how-do-i-use-planner"></a><span data-ttu-id="3afc1-217">Planner を使用するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-217">How do I use Planner?</span></span>
<span data-ttu-id="3afc1-218">「[Microsoft Planner のヘルプ](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)」と「[Planner のクイック スタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3afc1-218">Check out [Microsoft Planner help](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) and the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 

### <a name="how-do-i-use-forms"></a><span data-ttu-id="3afc1-219">Forms を使用するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3afc1-219">How do I use Forms?</span></span>
<span data-ttu-id="3afc1-220">「[Forms ヘルプ センター](https://support.office.com/forms)」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3afc1-220">Go to the [Forms help center](https://support.office.com/forms).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3afc1-221">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3afc1-221">Related topics</span></span>

[<span data-ttu-id="3afc1-222">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="3afc1-222">How to roll out Teams</span></span>](How-to-roll-out-teams.md)
