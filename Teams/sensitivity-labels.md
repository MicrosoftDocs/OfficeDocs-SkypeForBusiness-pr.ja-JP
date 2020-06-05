---
title: Microsoft Teams の機密ラベル
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams で機密ラベルを定義して使用する方法について説明します。
ms.openlocfilehash: 7f8eb7e0fa0d34ae21829a12011f094d8e9c9126
ms.sourcegitcommit: 2c23a8c5afc4a6b74c2c6d7487975a94fe99dc07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44562072"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="3a1e3-103">Microsoft Teams の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="3a1e3-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="3a1e3-104">機密[ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)を使用すると、チームの管理者はチーム内で共同作業を行って作成された機密組織のコンテンツへのアクセスを規制できます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="3a1e3-105">[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)では、機密ラベルと関連するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="3a1e3-106">このようなラベルとポリシーは、組織内の teams に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="3a1e3-107">秘密度ラベルとチーム分類ラベルの違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="3a1e3-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="3a1e3-108">機密ラベルは、PowerShell を使って作成する必要がある分類ラベルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="3a1e3-109">分類ラベルは、グループに関連付けることができるが、実際のポリシーは関連付けられていないテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="3a1e3-110">分類ラベルはメタデータとして使用し、内部のツールとスクリプトを使って手動でポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="3a1e3-111">一方、機密ラベルとそのポリシーは、グループプラットフォーム、セキュリティ & コンプライアンスセンター、および Teams サービスの組み合わせによって、自動的にエンドツーエンドで適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="3a1e3-112">機密ラベルを使用すると、組織の機密データをセキュリティで保護するための強力なインフラストラクチャサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="3a1e3-113">Teams の機密ラベルを作成、管理、および公開する</span><span class="sxs-lookup"><span data-stu-id="3a1e3-113">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="3a1e3-114">Teams の機密ラベルを有効にし、作成して発行する方法については、「 [Microsoft Teams、microsoft 365 グループ、SharePoint サイトで機密ラベルを使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="3a1e3-115">機密ラベルの作成、更新、削除には、ユーザーにラベルを発行するための順序を慎重に付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-115">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="3a1e3-116">順序を逸脱すると、すべてのユーザーに対して永続的なチーム作成エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-116">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="3a1e3-117">したがって、<a href="#createpublishlabels">ラベルの作成と発行</a>、発行された<a href="#modifydeletelabels">ラベルの変更と削除</a>、<a href="#manageerrors">チーム作成エラーの管理</a>を行う場合は、次の操作を実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-117">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="3a1e3-118"><a name="createpublishlabels"> </a> **ラベルを作成して発行する**</span><span class="sxs-lookup"><span data-stu-id="3a1e3-118">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="3a1e3-119">セキュリティ & コンプライアンスセンターでラベルを作成して公開するときに、ラベルが teams 作成インターフェイスに表示されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-119">When a label is created and published in the Security & Compliance Center, it can take up to 24 hours for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="3a1e3-120">テナントのすべてのユーザーのラベルを発行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-120">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="3a1e3-121">ラベルを作成して、テナント内のいくつかの選択されたユーザーアカウントに公開します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-121">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="3a1e3-122">ラベルが公開されたら、24時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-122">When the label is published, wait 24 hours.</span></span>
3. <span data-ttu-id="3a1e3-123">24時間後に、ラベルにアクセスできるいずれかのユーザーアカウントを使用して、ラベルを含むチームを作成してみてください。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-123">After 24 hours, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="3a1e3-124">手順3でチームが正常に作成された場合は、テナントに残りのユーザーのラベルを公開します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-124">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="3a1e3-125"><a name="modifydeletelabels"> </a> **公開したラベルを変更および削除**する</span><span class="sxs-lookup"><span data-stu-id="3a1e3-125">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="3a1e3-126">機密ポリシーに関連付けられているラベルを削除または変更すると、テナントでのチームの作成エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-126">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="3a1e3-127">したがって、ラベルを削除または変更する前に、最初にラベルと関連付けられているポリシーの関連付けを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-127">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="3a1e3-128">次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-128">Use the following steps</span></span>  
<span data-ttu-id="3a1e3-129">ラベルを削除または変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-129">to delete or modify a label:</span></span>
1. <span data-ttu-id="3a1e3-130">ラベルを使用するすべてのポリシーからラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-130">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="3a1e3-131">または、ポリシー自体を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-131">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="3a1e3-132">ラベルがポリシーから削除された場合やポリシー自体が削除された場合は、さらに作業を続ける前に、48時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-132">When the label is removed from the policies or the policies themselves are deleted, wait 48 hours before proceeding further.</span></span>
3. <span data-ttu-id="3a1e3-133">48時間経過したら、チーム作成インターフェイスを起動し、テナント内のユーザーのラベルが表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-133">After 48 hours, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="3a1e3-134">これで、ラベルを安全に削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-134">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="3a1e3-135">**チーム作成エラー** <a name="manageerrors"> </a>を管理する</span><span class="sxs-lookup"><span data-stu-id="3a1e3-135">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="3a1e3-136">パブリックプレビューの途中でチームの作成が失敗する場合は、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-136">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="3a1e3-137">チームを作成するときに、すべてのユーザーが秘密度のラベルを必須にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-137">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="3a1e3-138">「[このプレビューを有効にする](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)」のスクリプトを使用して、機密ラベルをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-138">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="3a1e3-139">EnableMIPLabels の設定は、次のように false に設定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-139">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="3a1e3-140">Teams で秘密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="3a1e3-140">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="3a1e3-141">組織内の Teams で機密ラベルを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-141">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="3a1e3-142">Teams のプライバシー設定</span><span class="sxs-lookup"><span data-stu-id="3a1e3-142">Privacy setting of teams</span></span>

<span data-ttu-id="3a1e3-143">チームの作成時に適用される機密ラベルを作成して、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を使用してチームを作成できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-143">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="3a1e3-144">たとえば、セキュリティ & コンプライアンスセンターで "社外秘" という名前のラベルを作成し、このラベルを使って作成されたチームがプライベートチームでなければならないようにチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-144">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="3a1e3-145">ユーザーが新しいチームを作成して、**機密**ラベルを選択した場合、ユーザーが使用できるプライバシーオプションのみが**非公開**になります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-145">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="3a1e3-146">パブリックや組織全体など、その他のプライバシーオプションは、ユーザーに対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-146">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![秘密度のラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="3a1e3-148">同様に、ユーザーが新しいチームを作成するときに **[一般**] を選択した場合、パブリックまたは組織全体のチームのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-148">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![一般的な秘密度ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

<span data-ttu-id="3a1e3-150">チームが作成されると、チーム内のチャネルの右上隅に [秘密度] ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-150">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![チームチャネルの秘密度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

<span data-ttu-id="3a1e3-152">チーム所有者は、チームに移動し、[**チームの編集**] をクリックして、いつでもチームの機密ラベルとプライバシー設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-152">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![チームチャネルの秘密度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="3a1e3-154">Teams へのゲストアクセス</span><span class="sxs-lookup"><span data-stu-id="3a1e3-154">Guest access to teams</span></span>

<span data-ttu-id="3a1e3-155">特定のラベルを使用して作成されたチームがゲストアクセスを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-155">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="3a1e3-156">ゲストアクセスが許可されていないラベルで作成されたチームは、組織内のユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-156">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="3a1e3-157">組織外のユーザーをチームに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-157">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3a1e3-158">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3a1e3-158">Known issues</span></span>

<span data-ttu-id="3a1e3-159">**Microsoft Teams 管理センターでの機密ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="3a1e3-159">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="3a1e3-160">現時点では、Microsoft Teams 管理センターでは、機密ラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-160">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3a1e3-161">機密ラベルを使用している場合、チームを作成または編集するときに、機密ラベルを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-161">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="3a1e3-162">機密ラベルは、チームプロパティにも表示されず、Microsoft Teams 管理センターの [**分類**] 列にも表示されません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-162">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="3a1e3-163">**Teams Graph Api、Powershell コマンドレット、テンプレートでの機密ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="3a1e3-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="3a1e3-164">現時点では、ユーザーは、Graph Api、Powershell コマンドレット、およびテンプレートを使って直接作成されたチームに機密ラベルを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="3a1e3-165">**Teams EDU Sku での機密ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="3a1e3-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="3a1e3-166">機密ラベルは、現在、Teams の教育 Sku を使用しているお客様はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="3a1e3-167">**SharePoint サイトコレクションでプライベートチャネルの機密ラベルを直接編集する**</span><span class="sxs-lookup"><span data-stu-id="3a1e3-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="3a1e3-168">チーム内で作成されたプライベートチャネルは、チームに適用された機密ラベルを継承します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="3a1e3-169">さらに、同じラベルが、プライベートチャネルの SharePoint サイトコレクションに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="3a1e3-170">プライベートチャネルの SharePoint サイトコレクションの機密ラベルがユーザーによって直接更新された場合、そのラベルは Teams クライアントでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="3a1e3-171">このシナリオでは、ユーザーはプライベートチャネルヘッダーのチームに適用された機密ラベルを引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="3a1e3-172">**Teams アプリ外部の機密ラベルに適用された変更の伝達時間**</span><span class="sxs-lookup"><span data-stu-id="3a1e3-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="3a1e3-173">Teams アプリ以外の機密ラベルに対する変更は、Teams アプリで反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="3a1e3-174">これは、テナントのラベルの有効化または無効化、ラベル名、設定、ポリシーの変更に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="3a1e3-175">さらに、チームをバックアップするグループまたは SharePoint サイトコレクションに直接追加されたラベルに対する変更は、Teams アプリに反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3a1e3-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
