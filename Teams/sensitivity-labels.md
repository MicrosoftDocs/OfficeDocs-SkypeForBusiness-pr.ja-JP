---
title: Microsoft Teams の感度ラベル
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Microsoft Teams で感度ラベルを定義して使用する方法について説明します。
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795778"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="feb61-103">Microsoft Teams の感度ラベル</span><span class="sxs-lookup"><span data-stu-id="feb61-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="feb61-104">[機密ラベルを使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) すると、Teams 管理者は、チーム内での共同作業中に作成された機密性の高い組織コンテンツへのアクセスを規制できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="feb61-105">コンプライアンス センターで、感度ラベルと関連するポリシーを [定義できます](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="feb61-105">You can define sensitivity labels and their associated policies in the [Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="feb61-106">これらのラベルとポリシーは、組織内のチームに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="feb61-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="feb61-107">区別ラベルと Teams の分類ラベルの違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="feb61-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="feb61-108">区別ラベルは、分類ラベルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="feb61-108">Sensitivity labels are different from classification labels.</span></span> <span data-ttu-id="feb61-109">分類ラベルは、Microsoft 365 グループに関連付け可能なが、実際のポリシーが関連付けられているものはないテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="feb61-109">Classification labels are text strings that can be associated with a Microsoft 365 Group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="feb61-110">分類ラベルをメタデータとして使用して、内部ツールとスクリプトを使用してポリシーを手動で適用します。</span><span class="sxs-lookup"><span data-stu-id="feb61-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="feb61-111">一方、感度ラベルとそのポリシーは、グループ プラットフォーム、セキュリティ & コンプライアンス センター、および Teams サービスの組み合わせを通じて、エンドツーエンドで自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="feb61-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="feb61-112">機密ラベルは、組織の機密データをセキュリティで保護するための強力なインフラストラクチャ サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="feb61-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="feb61-113">既存のグループを分類ラベルの使用から感度ラベルの使用に移行するには [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)グループの Azure Active Directory の分類と感度ラベルの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="feb61-113">To migrate your existing groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="feb61-114">Teams の感度ラベルを作成、管理、発行する</span><span class="sxs-lookup"><span data-stu-id="feb61-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="feb61-115">Teams の感度ラベルを有効にし、作成し、発行する方法については [、「Microsoft Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb61-115">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="feb61-116">感度ラベルを作成、更新、削除するには、ユーザーにラベルを発行する際に注意深く注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="feb61-117">シーケンスにずれが生じ、すべてのユーザーに永続的なチーム作成エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="feb61-118">したがって、ラベルの作成と発行、発行済みラベル<a href="#createpublishlabels"></a>の変更と削除、<a href="#modifydeletelabels"></a>チームの作成エラーの管理を行う場合は、次の操作<a href="#manageerrors">を行う必要があります</a>。</span><span class="sxs-lookup"><span data-stu-id="feb61-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="feb61-119">**ラベルを作成して発行する**<a name="createpublishlabels"></a></span><span class="sxs-lookup"><span data-stu-id="feb61-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="feb61-120">コンプライアンス センターでラベルを作成して公開すると、ラベルがチームの作成インターフェイスに表示されるのに最大 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-120">When a label is created and published in the Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="feb61-121">次の手順に従って、テナント内のすべてのユーザーにラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="feb61-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="feb61-122">ラベルを作成し、テナント内のいくつかの選択したユーザー アカウントに対して発行します。</span><span class="sxs-lookup"><span data-stu-id="feb61-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="feb61-123">ラベルが公開された場合は、10 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="feb61-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="feb61-124">10 分後に、ラベルにアクセスできるユーザー アカウントのいずれかを使用して、ラベル付きチームを作成してみてください。</span><span class="sxs-lookup"><span data-stu-id="feb61-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="feb61-125">手順 3 でチームが正常に作成された場合は、先に進み、テナント内の残りのユーザーのラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="feb61-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="feb61-126">**発行済みラベルを変更および削除する**<a name="modifydeletelabels"></a></span><span class="sxs-lookup"><span data-stu-id="feb61-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="feb61-127">ラベルが感度ポリシーに関連付けられている間にラベルを削除または変更すると、テナント全体でチームの作成に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="feb61-128">そのため、ラベルを削除または変更する前に、最初にラベルと関連付けられているポリシーの関連付けを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="feb61-129">次の手順を使用する</span><span class="sxs-lookup"><span data-stu-id="feb61-129">Use the following steps</span></span>  
<span data-ttu-id="feb61-130">を選択してラベルを削除または変更します。</span><span class="sxs-lookup"><span data-stu-id="feb61-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="feb61-131">ラベルを使用しているすべてのポリシーからラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="feb61-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="feb61-132">または、ポリシー自体を削除できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="feb61-133">ラベルがポリシーから削除された場合、またはポリシー自体が削除された場合は、さらに進むまで 10 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="feb61-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="feb61-134">10 分後に、チーム作成インターフェイスを起動し、テナント内のユーザーにラベルが表示されなくなったら確認します。</span><span class="sxs-lookup"><span data-stu-id="feb61-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="feb61-135">これで、ラベルを安全に削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="feb61-136">**チームの作成エラーを管理する**<a name="manageerrors"></a></span><span class="sxs-lookup"><span data-stu-id="feb61-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="feb61-137">パブリック プレビュー中にチームの作成が失敗し始める場合は、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="feb61-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="feb61-138">チームの作成中に、どのユーザーにも、感度ラベルが必須でなからず確認します。</span><span class="sxs-lookup"><span data-stu-id="feb61-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="feb61-139">[このプレビューを有効にする] のスクリプトを使用して、 [感度ラベルをオフにします](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)。</span><span class="sxs-lookup"><span data-stu-id="feb61-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="feb61-140">EnableMIPLabels の設定は、次のように false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="feb61-141">Teams で感度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="feb61-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="feb61-142">組織内の Teams で感度ラベルを使用する方法のシナリオ例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="feb61-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="feb61-143">チームのプライバシー設定</span><span class="sxs-lookup"><span data-stu-id="feb61-143">Privacy setting of teams</span></span>

<span data-ttu-id="feb61-144">チームの作成中に適用した場合、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できる、感度ラベルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="feb61-145">たとえば、セキュリティ & コンプライアンス センターで "Confidential" というラベルを作成し、このラベルで作成されたチームをプライベート チームに設定します。</span><span class="sxs-lookup"><span data-stu-id="feb61-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="feb61-146">ユーザーが新しいチームを作成し、機密ラベルを選択すると、ユーザーが使用できるプライバシー オプションは [プライベート]**のみです**。</span><span class="sxs-lookup"><span data-stu-id="feb61-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="feb61-147">パブリックや組織全体などの他のプライバシー オプションは、ユーザーに対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="feb61-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![機密ラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="feb61-149">同様に、ユーザーが新しいチームを作成するときに [全般] を選択した場合、パブリックチームまたは組織全体のチームのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![[一般的な感度] ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

<span data-ttu-id="feb61-151">チームが作成されると、チームのチャネルの右上隅に感度ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="feb61-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![チーム チャネルの感度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

<span data-ttu-id="feb61-153">チーム所有者は、チームにアクセスし、[チームの編集] をクリックすると、いつでもチームの感度ラベルとプライバシー設定を **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="feb61-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![チームプロパティの感度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="feb61-155">チームへのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="feb61-155">Guest access to teams</span></span>

<span data-ttu-id="feb61-156">特定のラベルで作成されたチームでゲスト アクセスを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="feb61-157">ゲスト アクセスを許可しないラベルで作成された Teams は、組織内のユーザーだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="feb61-158">組織外のユーザーをチームに追加できない。</span><span class="sxs-lookup"><span data-stu-id="feb61-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="feb61-159">Microsoft Teams 管理センターの感度ラベル</span><span class="sxs-lookup"><span data-stu-id="feb61-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="feb61-160">Microsoft Teams 管理センターでチームを作成または編集するときに、感度ラベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="feb61-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="feb61-161">また、チームのプロパティおよび Microsoft Teams 管理センターの [チームの管理] ページの [分類] 列にも、感度ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="feb61-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="feb61-162">既知の問題</span><span class="sxs-lookup"><span data-stu-id="feb61-162">Known issues</span></span>

<span data-ttu-id="feb61-163">**Teams Graph API、PowerShell コマンドレット、テンプレートでの感度ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="feb61-163">**Support for sensitivity labels in Teams Graph APIs, PowerShell cmdlets and templates**</span></span>

<span data-ttu-id="feb61-164">現在、ユーザーは、Graph API、PowerShell コマンドレット、およびテンプレートを使用して直接作成されたチームに、感度ラベルを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="feb61-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, PowerShell cmdlets, and templates.</span></span>

<span data-ttu-id="feb61-165">**Teams EDU SKU での感度ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="feb61-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="feb61-166">現在、Teams Education SKU を使用しているお客様は、感度ラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="feb61-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="feb61-167">**プライベート チャネル用に SharePoint サイト コレクションで直接感度ラベルを編集する**</span><span class="sxs-lookup"><span data-stu-id="feb61-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="feb61-168">チームで作成されたプライベート チャネルは、チームに適用された感度ラベルを継承します。</span><span class="sxs-lookup"><span data-stu-id="feb61-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="feb61-169">さらに、プライベート チャネルの SharePoint サイト コレクションにも同じラベルが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="feb61-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="feb61-170">ユーザーがプライベート チャネルの SharePoint サイト コレクションの感度ラベルを直接更新した場合、そのラベルは Teams クライアントでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="feb61-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="feb61-171">このシナリオでは、ユーザーはプライベート チャネル ヘッダーにチームに適用された感度ラベルを引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="feb61-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="feb61-172">**Teams アプリ以外の感度ラベルに適用された変更の反映時間**</span><span class="sxs-lookup"><span data-stu-id="feb61-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="feb61-173">Teams アプリ以外の感度ラベルに加えた変更は、Teams アプリに反映するために最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="feb61-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="feb61-174">これは、テナントのラベルを有効または無効にする変更、ラベル名、設定、ポリシーの変更に適用されます。</span><span class="sxs-lookup"><span data-stu-id="feb61-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="feb61-175">さらに、チームをバックアップするグループまたは SharePoint サイト コレクションに直接行われたラベルに対する変更は、Teams アプリに反映されるのに最大 24 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="feb61-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
