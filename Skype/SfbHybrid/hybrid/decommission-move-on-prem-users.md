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
description: ユーザーを移動してから、オンプレミスSkype for Business使用を停止します。
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420812"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="d9723-103">オンプレミス環境を使用停止する前に必要なユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="d9723-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="d9723-104">この記事では、オンプレミス環境を使用停止する前に、必要なユーザーを Microsoft クラウドに移動するSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="d9723-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="d9723-105">これは、オンプレミス環境を使用停止にするための次の手順 1 です。</span><span class="sxs-lookup"><span data-stu-id="d9723-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="d9723-106">**手順 1.必要なすべてのユーザーをオンプレミスからオンラインに移動します。**</span><span class="sxs-lookup"><span data-stu-id="d9723-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="d9723-107">(この記事)</span><span class="sxs-lookup"><span data-stu-id="d9723-107">(This article)</span></span>

- <span data-ttu-id="d9723-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="d9723-108">Step 2.</span></span> <span data-ttu-id="d9723-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="d9723-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="d9723-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="d9723-110">Step 3.</span></span> <span data-ttu-id="d9723-111">[ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行します](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="d9723-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="d9723-112">この手順を完了するまで、上記の手順 2 を実行するまで、既存のハイブリッド アプリケーション エンドポイントは検出できません。</span><span class="sxs-lookup"><span data-stu-id="d9723-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="d9723-113">同じメンテナンス ウィンドウで手順 2 と 3 の両方を実行する予定です。</span><span class="sxs-lookup"><span data-stu-id="d9723-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="d9723-114">手順 4.</span><span class="sxs-lookup"><span data-stu-id="d9723-114">Step 4.</span></span> <span data-ttu-id="d9723-115">[オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="d9723-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="d9723-116">必要なすべてのユーザーをオンプレミスからクラウドに移動する</span><span class="sxs-lookup"><span data-stu-id="d9723-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="d9723-117">移行が完了した後も引き続き使用するユーザーは、まずオンプレミスからクラウドに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9723-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="d9723-118">オンプレミスの管理ツールを使用してユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="d9723-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="d9723-119">詳細については、「オンプレミスと [クラウドの間でユーザーを移動する」を参照してください](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="d9723-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="d9723-120">オンプレミスのユーザーアカウントを持つユーザー Skype for Business Serverを使用Teams、これらのユーザーは、Teams の完全な機能を持Teams。</span><span class="sxs-lookup"><span data-stu-id="d9723-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="d9723-121">これらのユーザーは、オンラインまたはオンプレミスを問Skype for Businessを使用している他のユーザーと相互運用またはフェデレーションすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9723-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="d9723-122">また、これらのユーザーは、ユーザーのクライアントで PSTN 通話Teams受け取る必要もありません。</span><span class="sxs-lookup"><span data-stu-id="d9723-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="d9723-123">したがって、これらのユーザーをオンラインに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9723-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="d9723-124">また、この手順では、グループで作成された連絡先や会議Skype for Business Serverに移行Teams。</span><span class="sxs-lookup"><span data-stu-id="d9723-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="d9723-125">オンプレミス展開にユーザーが残っている場合は、PowerShell ウィンドウで次のコマンドレットSkype for Business Server実行します。</span><span class="sxs-lookup"><span data-stu-id="d9723-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="d9723-126">ユーザーが返された場合は、出力を確認して、アカウントをクラウドに移動する必要があるかどうかを確認し、そのようなユーザーについては、次の手順に従 [います](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="d9723-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="d9723-127">不要になったユーザー アカウントの場合は、PowerShell コマンドレットでSkype for Business Server実行します。</span><span class="sxs-lookup"><span data-stu-id="d9723-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="d9723-128">フィルターDisable-CsUserを実行すると、フィルター条件Skype for Businessを満たすすべてのユーザーのすべての属性が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d9723-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="d9723-129">先に進む前に、これらのアカウントが今後必要でなくなったか確認してください。</span><span class="sxs-lookup"><span data-stu-id="d9723-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="d9723-130">これで、ハイブリッド構成を [無効にする準備ができました](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="d9723-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9723-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9723-131">See also</span></span>

- [<span data-ttu-id="d9723-132">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="d9723-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="d9723-133">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="d9723-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="d9723-134">ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="d9723-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="d9723-135">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="d9723-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




