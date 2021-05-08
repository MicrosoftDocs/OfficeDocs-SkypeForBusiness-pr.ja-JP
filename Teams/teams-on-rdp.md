---
title: リモート Teamsサービスでアプリを使用する
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: リモート デスクトップ サービスで Microsoft Teamsを使用する方法について学習します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119096"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="37603-103">Teams デスクトップ サービスの設定</span><span class="sxs-lookup"><span data-stu-id="37603-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="37603-104">この記事では、リモート デスクトップ サービス (RDS) 環境でMicrosoft Teamsの要件と制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="37603-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="37603-105">RDS とは</span><span class="sxs-lookup"><span data-stu-id="37603-105">What is RDS?</span></span>

<span data-ttu-id="37603-106">リモート デスクトップ サービス (RDS) は、エンド ユーザーのニーズに応じて仮想化ソリューションを構築するためのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="37603-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="37603-107">RDS を使用すると、個々の仮想化アプリケーションを提供し、セキュリティで保護されたモバイル およびリモート デスクトップ アクセスを提供し、エンド ユーザーにクラウドからアプリケーションとデスクトップを実行する機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="37603-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="37603-108">RDS は、デプロイの柔軟性、コスト効率、拡張性を提供します。</span><span class="sxs-lookup"><span data-stu-id="37603-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="37603-109">RDS は、オンプレミスデプロイ用の Windows Server 2016、クラウド デプロイ用の Microsoft Azure、堅牢なパートナー ソリューションなど、さまざまなデプロイ オプションを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="37603-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="37603-110">環境と設定に応じて、セッション ベースの仮想化用の RDS ソリューションを仮想デスクトップ インフラストラクチャ (VDI) として設定できます。</span><span class="sxs-lookup"><span data-stu-id="37603-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="37603-111">現在、Teamsサービス環境内の共有機能は、コラボレーション機能とチャット機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="37603-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="37603-112">最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="37603-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-rds-with-chat-and-collaboration"></a><span data-ttu-id="37603-113">Teamsコラボレーションを使用して RDS を使用する</span><span class="sxs-lookup"><span data-stu-id="37603-113">Teams on RDS with chat and collaboration</span></span>

<span data-ttu-id="37603-114">組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="37603-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="37603-115">通話および会議機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="37603-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="37603-116">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="37603-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="37603-117">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="37603-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="37603-118">指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="37603-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="37603-119">[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="37603-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="37603-120">DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="37603-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="37603-121">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="37603-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="37603-122">AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="37603-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="37603-123">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="37603-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="37603-124">DisallowCalling 通話ポリシーと AllOff 会議ポリシーをユーザーに割り当てるには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="37603-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="37603-125">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="37603-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="37603-126">ユーザー名の左側にある を選択してユーザーを選択し、[設定の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37603-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="37603-127">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="37603-127">Do the following steps:</span></span>

    <span data-ttu-id="37603-128">a.</span><span class="sxs-lookup"><span data-stu-id="37603-128">a.</span></span>  <span data-ttu-id="37603-129">[通話 **ポリシー] で** **、[DisallowCalling] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37603-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="37603-130">b.</span><span class="sxs-lookup"><span data-stu-id="37603-130">b.</span></span>  <span data-ttu-id="37603-131">[会議 **ポリシー] で**、[ **すべてオフ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37603-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="37603-132">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37603-132">Select **Apply**.</span></span>

<span data-ttu-id="37603-133">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="37603-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="37603-134">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="37603-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="37603-135">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="37603-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="37603-136">すべてのユーザーを選択するには、表の&#x2713;にある [チェック マーク] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37603-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="37603-137">[設定 **の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="37603-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="37603-138">または、次の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="37603-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="37603-139">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="37603-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="37603-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37603-140">For example:</span></span>

    - <span data-ttu-id="37603-141">[音声通話 **ポリシー**  >  **] に移動し\*\*\*\*、[DisallowCalling] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37603-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="37603-142">[会議の **会議**  >  **ポリシー] に移動し、[** すべてオフ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37603-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="37603-143">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37603-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="37603-144">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="37603-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="37603-145">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="37603-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="37603-146">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37603-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="37603-147">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="37603-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="37603-148">次の例は、[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="37603-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="37603-149">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37603-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="37603-150">次の例は、[Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="37603-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="37603-151">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37603-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>