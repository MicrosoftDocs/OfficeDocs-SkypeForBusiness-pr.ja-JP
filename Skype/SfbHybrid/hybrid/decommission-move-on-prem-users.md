---
title: ユーザーとエンドポイントをクラウドに移動する
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
description: Skype for Business オンプレミス環境を使用停止する前に、ユーザーとエンドポイントを移動します。
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593910"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="e64d5-103">オンプレミス環境を使用停止する前に、必要なユーザーとエンドポイントを移動する</span><span class="sxs-lookup"><span data-stu-id="e64d5-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="e64d5-104">この記事では、オンプレミスの Skype for Business 環境を使用停止する前に、必要なユーザーとアプリケーション エンドポイントを Microsoft クラウドに移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="e64d5-105">これは、オンプレミス環境を使用停止にするための次の手順 1 です。</span><span class="sxs-lookup"><span data-stu-id="e64d5-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="e64d5-106">**手順 1.必要なすべてのユーザーとアプリケーション エンドポイントをオンプレミスからオンラインに移動します。**</span><span class="sxs-lookup"><span data-stu-id="e64d5-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="e64d5-107">(この記事)</span><span class="sxs-lookup"><span data-stu-id="e64d5-107">(This article.)</span></span>

- <span data-ttu-id="e64d5-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="e64d5-108">Step 2.</span></span> <span data-ttu-id="e64d5-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d5-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="e64d5-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="e64d5-110">Step 3.</span></span> <span data-ttu-id="e64d5-111">[オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d5-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="e64d5-112">必要なすべてのユーザーをオンプレミスからクラウドに移動する</span><span class="sxs-lookup"><span data-stu-id="e64d5-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="e64d5-113">移行が完了した後も引き続き使用するユーザーは、まずオンプレミスからクラウドに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e64d5-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="e64d5-114">オンプレミスの管理ツールを使用してユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="e64d5-115">詳細については、「オンプレミスと [クラウドの間でユーザーを移動する」を参照してください](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d5-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="e64d5-116">オンプレミスの Skype for Business Server アカウントを持つユーザーは Teams を使用することができますが、これらのユーザーには Teams の完全な機能はありません。</span><span class="sxs-lookup"><span data-stu-id="e64d5-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="e64d5-117">これらのユーザーは、Skype for Business を引き続き使用している他のユーザー (オンラインでもオンプレミスでも) を相互運用またはフェデレーションすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e64d5-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="e64d5-118">また、これらのユーザーは Teams クライアントで PSTN 通話を受け取る必要もありません。</span><span class="sxs-lookup"><span data-stu-id="e64d5-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="e64d5-119">したがって、これらのユーザーをオンラインに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e64d5-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="e64d5-120">この手順では、Skype for Business Server で作成された連絡先や会議が Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="e64d5-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="e64d5-121">オンプレミス展開にユーザーが残っている場合は、Skype for Business Server PowerShell ウィンドウで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="e64d5-122">ユーザーが返された場合は、出力を確認して、アカウントをクラウドに移動する必要があるかどうかを確認し、そのようなユーザーについては、次の手順に従 [います](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d5-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="e64d5-123">不要になったユーザー アカウントの場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="e64d5-124">このDisable-CsUserすると、フィルター条件を満たすすべてのユーザーのすべての Skype for Business 属性が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e64d5-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="e64d5-125">先に進む前に、これらのアカウントが今後必要でなくなったか確認してください。</span><span class="sxs-lookup"><span data-stu-id="e64d5-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="e64d5-126">オンプレミスのハイブリッド アプリケーション エンドポイントを Microsoft 365 に移動する</span><span class="sxs-lookup"><span data-stu-id="e64d5-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="e64d5-127">次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスのハイブリッド アプリケーション エンドポイント設定を取得およびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e64d5-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="e64d5-128">Microsoft 365 で新しい [リソース アカウント](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) を作成してライセンスを取得し、既存のオンプレミスハイブリッド アプリケーション エンドポイントを置き換える。</span><span class="sxs-lookup"><span data-stu-id="e64d5-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="e64d5-129">新しいリソース アカウントを既存のハイブリッド アプリケーション エンドポイントに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="e64d5-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="e64d5-130">次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスハイブリッド アプリケーション エンドポイントで定義されている電話番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="e64d5-131">これらのアカウントの電話番号は、オンプレミスではなく Microsoft 365 で管理されている可能性があります。Skype for Business Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="e64d5-132">手順 2 で作成した新しいリソース アカウントに電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e64d5-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="e64d5-133">電話番号をリソース アカウントに割り当てる方法の詳細については、「サービス番号を割り当てる」 [を参照してください](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="e64d5-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="e64d5-134">次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスのエンドポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="e64d5-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="e64d5-135">これで、ハイブリッド構成を [無効にする準備ができました](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d5-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e64d5-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e64d5-136">See also</span></span>

- [<span data-ttu-id="e64d5-137">オンプレミスの Skype for Business 環境を使用停止する</span><span class="sxs-lookup"><span data-stu-id="e64d5-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="e64d5-138">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="e64d5-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="e64d5-139">オンプレミスの Skype for Business 展開を削除する</span><span class="sxs-lookup"><span data-stu-id="e64d5-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




