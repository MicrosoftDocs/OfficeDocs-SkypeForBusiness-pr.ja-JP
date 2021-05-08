---
title: Microsoft Teams の感度ラベル
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 感度ラベルを使用してチームを保護する方法についてMicrosoft Teams。
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593865"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="45e6a-103">Microsoft Teams の感度ラベル</span><span class="sxs-lookup"><span data-stu-id="45e6a-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="45e6a-104">[機密ラベルを使用](/microsoft-365/compliance/sensitivity-labels)するとTeamsチーム内の共同作業中に作成された機密性の高い組織のコンテンツへのアクセスを保護および規制できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-104">[Sensitivity labels](/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="45e6a-105">[Microsoft](/microsoft-365/compliance/go-to-the-securitycompliance-center)コンプライアンス センターで、関連付けられているポリシーで感度ラベルを構成した後、これらのラベルを組織内のチームに適用できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="45e6a-106">現在、Teams Education SKU を使用しているお客様のクラス チームでは、感度ラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="45e6a-106">Sensitivity labels are currently unsupported in class teams for customers using Teams Education SKUs.</span></span> <span data-ttu-id="45e6a-107">Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45e6a-107">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="45e6a-108">感度ラベルと分類ラベルの違Teamsは何ですか?</span><span class="sxs-lookup"><span data-stu-id="45e6a-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="45e6a-109">感度ラベルは、分類ラベルとは異なります。分類ラベルは、Azure AD分類とも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="45e6a-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="45e6a-110">分類ラベルは、特定のグループに関連付Microsoft 365、実際のポリシーが関連付けられているものはないテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="45e6a-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="45e6a-111">分類ラベルをメタデータとして使用し、内部ツールやスクリプトなどの他の方法を使用してポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45e6a-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="45e6a-112">感度ラベルを使用する利点は、ポリシーが Microsoft 365 Groups プラットフォーム、コンプライアンス センター、および Teams サービスの組み合わせによってエンド to エンドで自動的に適用されるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="45e6a-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="45e6a-113">機密ラベルは、組織の機密データをセキュリティで保護し、社内のポリシーまたは規制に準拠するための強力なインフラストラクチャ サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="45e6a-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="45e6a-114">現在分類ラベルを使用している場合は、感度ラベルに移行する方法の詳細と手順については、次のドキュメントを参照してください。クラシック Azure AD [グループ分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。</span><span class="sxs-lookup"><span data-stu-id="45e6a-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="45e6a-115">感度ラベルのシナリオ例</span><span class="sxs-lookup"><span data-stu-id="45e6a-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="45e6a-116">組織内のユーザーと一緒に感度ラベルを使用Teamsシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="45e6a-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="45e6a-117">チームのプライバシー レベル (パブリックまたはプライベート) を設定する</span><span class="sxs-lookup"><span data-stu-id="45e6a-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="45e6a-118">チームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="45e6a-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="45e6a-119">チームのプライバシー レベルを設定する</span><span class="sxs-lookup"><span data-stu-id="45e6a-119">Set the privacy level for teams</span></span>

<span data-ttu-id="45e6a-120">チームの作成時に適用すると、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できる、感度ラベルを作成して構成できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="45e6a-121">たとえば、"Confidential" という名前の機密ラベルを作成して発行します。このラベルには、ラベルのプライバシー オプションが Private として構成 **されています**。</span><span class="sxs-lookup"><span data-stu-id="45e6a-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="45e6a-122">その結果、このラベルで作成されたチームは、プライベート チームである必要があります。</span><span class="sxs-lookup"><span data-stu-id="45e6a-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="45e6a-123">ユーザーが新しいチームを作成し **、[Confidential]** ラベルを選択すると、ユーザーが使用できるプライバシー オプションは [プライベート] **のみです**。</span><span class="sxs-lookup"><span data-stu-id="45e6a-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="45e6a-124">[パブリック] や [組織全体] などの他のプライバシー オプションは、ユーザーが選択できません。</span><span class="sxs-lookup"><span data-stu-id="45e6a-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![機密ラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="45e6a-126">同様に、ラベル プライバシー オプションがパブリック として構成されている "General" という名前の感度ラベルを作成して発行 **します**。</span><span class="sxs-lookup"><span data-stu-id="45e6a-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="45e6a-127">ユーザーが新しいチームを作成すると、次のラベルを選択した場合にのみ、パブリックまたは組織全体のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![一般的な感度ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

<span data-ttu-id="45e6a-129">チームが作成されると、チーム内のチャネルの右上隅に感度ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> 

> [!NOTE]
> <span data-ttu-id="45e6a-130">"Confidential\Finance" などの階層的な親子ラベルを使用している場合は、親ラベルだけがチャネル ヘッダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-130">If you are using hierarchical parent-child labels such as "Confidential\Finance", then only the parent label will be shown in the channel header.</span></span>

![チーム チャネルの感度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

<span data-ttu-id="45e6a-132">チーム所有者は、チームにアクセスしてチームの感度ラベルとプライバシー設定をいつでも変更し、[チームの編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="45e6a-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![チームのプロパティの感度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="45e6a-134">チームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="45e6a-134">Control guest access to teams</span></span>

<span data-ttu-id="45e6a-135">感度ラベルを使用して、チームへのゲスト アクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="45e6a-136">Teamsアクセスを許可しないラベルで作成されたユーザーは、組織内のユーザーだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="45e6a-137">組織外のユーザーをチームに追加できない。</span><span class="sxs-lookup"><span data-stu-id="45e6a-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="45e6a-138">Microsoft Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="45e6a-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="45e6a-139">管理者センターでチームを作成または編集するときに、Microsoft Teams適用できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="45e6a-140">また、チームのプロパティや、管理センターの [チームの管理]ページの [分類] Microsoft Teams表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="45e6a-141">制限事項</span><span class="sxs-lookup"><span data-stu-id="45e6a-141">Limitations</span></span>

<span data-ttu-id="45e6a-142">感度ラベルを使用する前Teams、次の制限事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="45e6a-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="45e6a-143">**親ラベル名がサブラベルに対して表示されない**</span><span class="sxs-lookup"><span data-stu-id="45e6a-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="45e6a-144">Teamsはサブラベルをサポートしますが、親ラベルの名前は表示されません。</span><span class="sxs-lookup"><span data-stu-id="45e6a-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="45e6a-145">たとえば、Confidential  \\ **All Employees は [All Employees]** **と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="45e6a-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="45e6a-146">**感度ラベルは、TEAMS GRAPH Api、PowerShell コマンドレット、およびテンプレートではサポートされていません**</span><span class="sxs-lookup"><span data-stu-id="45e6a-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="45e6a-147">ユーザーは、Teams Graph API、powerShell コマンドレット、Teams テンプレートを使用してチームを直接作成する際に、Teamsできません。</span><span class="sxs-lookup"><span data-stu-id="45e6a-147">Users won't be able to specify sensitivity labels while creating teams directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span> <span data-ttu-id="45e6a-148">ただし、Modern Groups Graph API と PowerShell コマンドレットを使用すると、ラベル付きのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-148">However Modern Groups Graph APIs and PowerShell cmdlets do allow creation of groups with labels.</span></span> <span data-ttu-id="45e6a-149">そのため、ユーザーはまず Groups Graph API または PowerShell コマンドレットを使用してラベル付きグループを作成し、次にこれらのグループを Teams。</span><span class="sxs-lookup"><span data-stu-id="45e6a-149">So users can first create Groups with labels using Groups Graph APIs or PowerShell cmdlets and then convert these Groups in to Teams.</span></span>

- <span data-ttu-id="45e6a-150">**プライベート チャネルのサポート**</span><span class="sxs-lookup"><span data-stu-id="45e6a-150">**Support for private channels**</span></span>
    
    <span data-ttu-id="45e6a-151">チームで作成されたプライベート チャネルは、チームに適用された感度ラベルを継承します。</span><span class="sxs-lookup"><span data-stu-id="45e6a-151">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="45e6a-152">同じラベルが、プライベート チャネルの SharePointに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="45e6a-152">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="45e6a-153">ただし、ユーザーがプライベート チャネルの SharePoint サイトの感度ラベルを直接変更した場合、そのラベルの変更は Teams クライアントに反映されません。</span><span class="sxs-lookup"><span data-stu-id="45e6a-153">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="45e6a-154">このシナリオでは、ユーザーはプライベート チャネル ヘッダーでチームに適用された元の感度ラベルを引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="45e6a-154">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="45e6a-155">デバイスの感度ラベルを作成して構成するTeams</span><span class="sxs-lookup"><span data-stu-id="45e6a-155">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="45e6a-156">次のドキュメントの手順に従ってMicrosoft 365の感度ラベルを作成して構成Teams。</span><span class="sxs-lookup"><span data-stu-id="45e6a-156">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="45e6a-157">[感度ラベルを使用して、Microsoft Teams、Microsoft 365、](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)および SharePoint サイト内のコンテンツを保護します。</span><span class="sxs-lookup"><span data-stu-id="45e6a-157">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
