---
title: ユーザーをクラウドに移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Skype for Business オンプレミス環境を使用停止する前にユーザーを移動します。
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656673"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="3dd8f-103">オンプレミス環境を使用停止する前に必要なユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="3dd8f-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="3dd8f-104">この記事では、オンプレミスの Skype for Business 環境を使用停止する前に、必要なユーザーを Microsoft クラウドに移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3dd8f-105">これは、オンプレミス環境を使用停止にするための次の手順 1 です。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3dd8f-106">**手順 1.必要なすべてのユーザーをオンプレミスからオンラインに移動します。**</span><span class="sxs-lookup"><span data-stu-id="3dd8f-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="3dd8f-107">(この記事)</span><span class="sxs-lookup"><span data-stu-id="3dd8f-107">(This article)</span></span>

- <span data-ttu-id="3dd8f-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-108">Step 2.</span></span> <span data-ttu-id="3dd8f-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="3dd8f-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-110">Step 3.</span></span> <span data-ttu-id="3dd8f-111">[ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3dd8f-112">手順 4.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-112">Step 4.</span></span> <span data-ttu-id="3dd8f-113">[オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="3dd8f-114">必要なすべてのユーザーをオンプレミスからクラウドに移動する</span><span class="sxs-lookup"><span data-stu-id="3dd8f-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="3dd8f-115">移行が完了した後も引き続き使用するユーザーは、まずオンプレミスからクラウドに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="3dd8f-116">オンプレミスの管理ツールを使用してユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="3dd8f-117">詳細については、「オンプレミスと [クラウドの間でユーザーを移動する」を参照してください](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="3dd8f-118">オンプレミスの Skype for Business Server アカウントを持つユーザーは Teams を使用することができますが、これらのユーザーには Teams の完全な機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="3dd8f-119">これらのユーザーは、Skype for Business を引き続き使用している他のユーザー (オンラインでもオンプレミスでも) を相互運用またはフェデレーションすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="3dd8f-120">また、これらのユーザーは Teams クライアントで PSTN 通話を受け取る必要もありません。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="3dd8f-121">したがって、これらのユーザーをオンラインに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="3dd8f-122">この手順では、Skype for Business Server で作成された連絡先や会議が Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="3dd8f-123">オンプレミス展開にユーザーが残っている場合は、Skype for Business Server PowerShell ウィンドウで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="3dd8f-124">ユーザーが返された場合は、出力を確認して、アカウントをクラウドに移動する必要があるかどうかを確認し、そのようなユーザーについては、次の手順に従 [います](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="3dd8f-125">不要になったユーザー アカウントの場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="3dd8f-126">このDisable-CsUserすると、フィルター条件を満たすすべてのユーザーのすべての Skype for Business 属性が削除されます。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="3dd8f-127">先に進む前に、これらのアカウントが今後必要でなくなったか確認してください。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="3dd8f-128">これで、ハイブリッド構成を [無効にする準備ができました](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd8f-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3dd8f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3dd8f-129">See also</span></span>

- [<span data-ttu-id="3dd8f-130">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="3dd8f-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="3dd8f-131">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="3dd8f-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="3dd8f-132">ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="3dd8f-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="3dd8f-133">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="3dd8f-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




