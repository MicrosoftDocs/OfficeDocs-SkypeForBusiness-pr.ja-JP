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
description: Microsoft Teams でチームを保護するために、感度ラベルを使用する方法について説明します。
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875107"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="4fbb3-103">Microsoft Teams の感度ラベル</span><span class="sxs-lookup"><span data-stu-id="4fbb3-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="4fbb3-104">[機密ラベルを使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) すると、Teams 管理者は、チーム内での共同作業中に作成された機密性の高い組織コンテンツへのアクセスを保護し、規制することができます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="4fbb3-105">[Microsoft](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)コンプライアンス センターで、関連するポリシーを使用して感度ラベルを構成した後、これらのラベルを組織内のチームに適用できます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="4fbb3-106">現在、Teams Education SKU を使用しているお客様は、感度ラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="4fbb3-107">Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="4fbb3-108">感度ラベルと Teams の分類ラベルの違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="4fbb3-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="4fbb3-109">感度ラベルは、分類ラベルとは異なります (Azure ラベルと呼ばれるAD分類)。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="4fbb3-110">分類ラベルは、Microsoft 365 グループに関連付け可能なが、実際のポリシーが関連付けはないテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="4fbb3-111">分類ラベルをメタデータとして使用し、内部ツールやスクリプトなどの他の方法を使用してポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="4fbb3-112">感度ラベルを使用する利点は、ポリシーが Microsoft 365 グループ プラットフォーム、コンプライアンス センター、および Teams サービスの組み合わせを通じてエンドツーエンドで自動的に適用される点です。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="4fbb3-113">機密ラベルは、組織の機密データをセキュリティで保護し、内部のポリシーまたは規制に準拠するための強力なインフラストラクチャ サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="4fbb3-114">現在分類ラベルを使用している場合は、詳細およびそれらを感度ラベルに移行する方法については、次のドキュメントを参照してください。従来の [Azure AD グループの分類](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="4fbb3-115">感度ラベルのシナリオ例</span><span class="sxs-lookup"><span data-stu-id="4fbb3-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="4fbb3-116">組織内の Teams で感度ラベルを使用する方法のシナリオ例:</span><span class="sxs-lookup"><span data-stu-id="4fbb3-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="4fbb3-117">チームのプライバシー レベル (パブリックまたはプライベート) を設定する</span><span class="sxs-lookup"><span data-stu-id="4fbb3-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="4fbb3-118">チームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="4fbb3-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="4fbb3-119">チームのプライバシー レベルを設定する</span><span class="sxs-lookup"><span data-stu-id="4fbb3-119">Set the privacy level for teams</span></span>

<span data-ttu-id="4fbb3-120">チームの作成中に適用すると、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できる、感度ラベルを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="4fbb3-121">たとえば、"機密" という名前の機密ラベルを作成して発行し、ラベルのプライバシー オプションが [非公開] として構成 **されている場合などです**。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="4fbb3-122">その結果、このラベルで作成されたチームは、プライベート チームである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="4fbb3-123">ユーザーが新しいチームを作成し、機密ラベルを選択すると、ユーザーが使用できるプライバシー オプションは [プライベート]**のみです**。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="4fbb3-124">パブリックや組織全体などの他のプライバシー オプションは、ユーザーが次を選択できません。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![機密ラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="4fbb3-126">同様に、"全般" という名前の感度ラベルを作成して発行し、ラベルのプライバシー オプションを [パブリック] として構成 **します**。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="4fbb3-127">ユーザーが新しいチームを作成すると、次のラベルを選択した場合にのみ、パブリックまたは組織全体のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![[一般的な感度] ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

<span data-ttu-id="4fbb3-129">チームが作成されると、チームのチャネルの右上隅に感度ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> <span data-ttu-id="4fbb3-130">"Confidential\Finance" などの階層的な親の子ラベルを使用している場合は、親ラベルだけがチャネル ヘッダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-130">Note that if you are using hierarchical parent child labels such as "Confidential\Finance" then only the parent label will be showin the channel header.</span></span>


![チーム チャネルの感度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

<span data-ttu-id="4fbb3-132">チーム所有者は、チームにアクセスして [チームの編集] をクリックすると、いつでもチームの感度ラベルとプライバシー設定を **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![チームプロパティの感度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="4fbb3-134">チームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="4fbb3-134">Control guest access to teams</span></span>

<span data-ttu-id="4fbb3-135">チームへのゲスト アクセスを制御するには、感度ラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="4fbb3-136">ゲスト アクセスを許可しないラベルで作成された Teams は、組織内のユーザーだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="4fbb3-137">組織外のユーザーをチームに追加できない。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="4fbb3-138">Microsoft Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="4fbb3-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="4fbb3-139">Microsoft Teams 管理センターでチームを作成または編集するときに、感度ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="4fbb3-140">また、チームのプロパティおよび Microsoft Teams 管理センターの [チームの管理] ページの [分類] 列にも、感度ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="4fbb3-141">制限事項</span><span class="sxs-lookup"><span data-stu-id="4fbb3-141">Limitations</span></span>

<span data-ttu-id="4fbb3-142">Teams の感度ラベルを使用する前に、次の制限事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="4fbb3-143">**サブラベルに親ラベル名が表示されない**</span><span class="sxs-lookup"><span data-stu-id="4fbb3-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="4fbb3-144">Teams はサブラベルをサポートしますが、親ラベルの名前は表示されません。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="4fbb3-145">たとえば、機密のすべての **従業員** \\ **は、すべての従業員\*\*\*\*として表示されます**。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="4fbb3-146">**Teams Graph API、PowerShell コマンドレット、およびテンプレートでは、感度ラベルはサポートされません。**</span><span class="sxs-lookup"><span data-stu-id="4fbb3-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="4fbb3-147">ユーザーは、Teams Graph API、Teams PowerShell コマンドレット、および Teams テンプレートを使用して直接作成されたチームに、感度ラベルを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-147">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="4fbb3-148">**プライベート チャネルのサポート**</span><span class="sxs-lookup"><span data-stu-id="4fbb3-148">**Support for private channels**</span></span>
    
    <span data-ttu-id="4fbb3-149">チームで作成されたプライベート チャネルは、チームに適用された感度ラベルを継承します。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-149">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="4fbb3-150">プライベート チャネルの SharePoint サイト コレクションにも同じラベルが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-150">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="4fbb3-151">ただし、ユーザーがプライベート チャネルの SharePoint サイトの感度ラベルを直接変更した場合、そのラベルの変更は Teams クライアントには反映されません。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-151">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="4fbb3-152">このシナリオでは、ユーザーはプライベート チャネル ヘッダーにチームに適用された元の感度ラベルを引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-152">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="4fbb3-153">Teams の感度ラベルを作成および構成する方法</span><span class="sxs-lookup"><span data-stu-id="4fbb3-153">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="4fbb3-154">Microsoft 365 ドキュメントの手順を使用して、Teams の感度ラベルを作成および構成します。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-154">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="4fbb3-155">[Microsoft Teams、Microsoft 365 グループ、SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)サイトのコンテンツを保護するには、感度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fbb3-155">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
