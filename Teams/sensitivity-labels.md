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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で機密ラベルを定義して使用する方法について説明します。
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653593"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="59910-103">Microsoft Teams の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="59910-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="59910-104">機密[ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)を使用すると、チームの管理者はチーム内で共同作業を行って作成された機密組織のコンテンツへのアクセスを規制できます。</span><span class="sxs-lookup"><span data-stu-id="59910-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="59910-105">[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)では、機密ラベルと関連するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="59910-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="59910-106">このようなラベルとポリシーは、組織内の teams に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="59910-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="59910-107">秘密度ラベルとチーム分類ラベルの違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="59910-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="59910-108">機密ラベルは、PowerShell を使って作成する必要がある分類ラベルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="59910-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="59910-109">分類ラベルは、グループに関連付けることができるが、実際のポリシーは関連付けられていないテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="59910-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="59910-110">分類ラベルはメタデータとして使用し、内部のツールとスクリプトを使って手動でポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="59910-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="59910-111">一方、機密ラベルとそのポリシーは、グループプラットフォーム、セキュリティ & コンプライアンスセンター、および Teams サービスの組み合わせによって、自動的にエンドツーエンドで適用されます。</span><span class="sxs-lookup"><span data-stu-id="59910-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="59910-112">機密ラベルを使用すると、組織の機密データをセキュリティで保護するための強力なインフラストラクチャサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="59910-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="59910-113">チームの機密ラベルを作成して公開する</span><span class="sxs-lookup"><span data-stu-id="59910-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="59910-114">Teams の機密ラベルを有効にし、作成して発行する方法については、「 [Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59910-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="59910-115">Teams で秘密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="59910-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="59910-116">組織内の Teams で機密ラベルを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="59910-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="59910-117">Teams のプライバシー設定</span><span class="sxs-lookup"><span data-stu-id="59910-117">Privacy setting of teams</span></span>

<span data-ttu-id="59910-118">チームの作成時に適用される機密ラベルを作成して、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を使用してチームを作成できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="59910-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="59910-119">たとえば、セキュリティ & コンプライアンスセンターで "社外秘" という名前のラベルを作成し、このラベルを使って作成されたチームがプライベートチームでなければならないようにチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="59910-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="59910-120">ユーザーが新しいチームを作成して、**機密**ラベルを選択した場合、ユーザーが使用できるプライバシーオプションのみが**非公開**になります。</span><span class="sxs-lookup"><span data-stu-id="59910-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="59910-121">パブリックや組織全体など、その他のプライバシーオプションは、ユーザーに対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="59910-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![秘密度のラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="59910-123">同様に、ユーザーが新しいチームを作成するときに **[一般**] を選択した場合、パブリックまたは組織全体のチームのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="59910-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![一般的な秘密度ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

<span data-ttu-id="59910-125">チームが作成されると、チーム内のチャネルの右上隅に [秘密度] ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59910-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![チームチャネルの秘密度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

<span data-ttu-id="59910-127">チーム所有者は、チームに移動し、[**チームの編集**] をクリックして、いつでもチームの機密ラベルとプライバシー設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="59910-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![チームチャネルの秘密度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="59910-129">Teams へのゲストアクセス</span><span class="sxs-lookup"><span data-stu-id="59910-129">Guest access to teams</span></span>

<span data-ttu-id="59910-130">特定のラベルを使用して作成されたチームがゲストアクセスを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="59910-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="59910-131">ゲストアクセスが許可されていないラベルで作成されたチームは、組織内のユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="59910-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="59910-132">組織外のユーザーをチームに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="59910-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="59910-133">既知の問題</span><span class="sxs-lookup"><span data-stu-id="59910-133">Known issues</span></span>

<span data-ttu-id="59910-134">**Microsoft Teams 管理センターでの機密ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="59910-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="59910-135">現時点では、Microsoft Teams 管理センターでは、機密ラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="59910-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="59910-136">機密ラベルを使用している場合、チームを作成または編集するときに、機密ラベルを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="59910-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="59910-137">機密ラベルは、チームプロパティにも表示されず、Microsoft Teams 管理センターの [**分類**] 列にも表示されません。</span><span class="sxs-lookup"><span data-stu-id="59910-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="59910-138">**Teams Graph Api、Powershell コマンドレット、テンプレートでの機密ラベルのサポート**</span><span class="sxs-lookup"><span data-stu-id="59910-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="59910-139">現時点では、ユーザーは、Graph Api、Powershell コマンドレット、およびテンプレートを使って直接作成されたチームに機密ラベルを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="59910-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="59910-140">**SharePoint サイトコレクションでプライベートチャネルの機密ラベルを直接編集する**</span><span class="sxs-lookup"><span data-stu-id="59910-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="59910-141">チーム内で作成されたプライベートチャネルは、チームに適用された機密ラベルを継承します。</span><span class="sxs-lookup"><span data-stu-id="59910-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="59910-142">さらに、同じラベルが、プライベートチャネルの SharePoint サイトコレクションに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="59910-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="59910-143">プライベートチャネルの SharePoint サイトコレクションの機密ラベルがユーザーによって直接更新された場合、そのラベルは Teams クライアントでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="59910-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="59910-144">このシナリオでは、ユーザーはプライベートチャネルヘッダーのチームに適用された機密ラベルを引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="59910-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="59910-145">**Teams アプリ外部の機密ラベルに適用された変更の伝達時間**</span><span class="sxs-lookup"><span data-stu-id="59910-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="59910-146">Teams アプリ以外の機密ラベルに対する変更は、Teams アプリで反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="59910-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="59910-147">これは、テナントのラベルの有効化または無効化、ラベル名、設定、ポリシーの変更に適用されます。</span><span class="sxs-lookup"><span data-stu-id="59910-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="59910-148">さらに、チームをバックアップするグループまたは SharePoint サイトコレクションに直接追加されたラベルに対する変更は、Teams アプリに反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="59910-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>