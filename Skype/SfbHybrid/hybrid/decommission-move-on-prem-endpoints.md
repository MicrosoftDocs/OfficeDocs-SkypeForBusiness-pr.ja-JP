---
title: ハイブリッド アプリケーション エンドポイントをクラウドに移行する
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
description: hyrid アプリケーション エンドポイントを移行してから、オンプレミス環境Skype for Business使用を停止します。
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420802"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="16fc3-103">オンプレミス環境を使用停止する前にハイブリッド アプリケーション エンドポイントを移行する</span><span class="sxs-lookup"><span data-stu-id="16fc3-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="16fc3-104">この記事では、オンプレミスのアプリケーション 環境を使用停止する前に、必要なハイブリッド アプリケーション エンドポイントを Microsoft クラウドに移動するSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="16fc3-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="16fc3-105">これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。</span><span class="sxs-lookup"><span data-stu-id="16fc3-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="16fc3-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="16fc3-106">Step 1.</span></span> [<span data-ttu-id="16fc3-107">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="16fc3-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="16fc3-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="16fc3-108">Step 2.</span></span> <span data-ttu-id="16fc3-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="16fc3-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="16fc3-110">**手順 3.ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行します。**</span><span class="sxs-lookup"><span data-stu-id="16fc3-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="16fc3-111">(この記事)</span><span class="sxs-lookup"><span data-stu-id="16fc3-111">(This article)</span></span>

- <span data-ttu-id="16fc3-112">手順 4.</span><span class="sxs-lookup"><span data-stu-id="16fc3-112">Step 4.</span></span> <span data-ttu-id="16fc3-113">[オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="16fc3-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="16fc3-114">必要なすべてのハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行する</span><span class="sxs-lookup"><span data-stu-id="16fc3-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="16fc3-115">これらのエンドポイントをオンラインに移動する前に、エンドポイントで使用されるすべての sip ドメインの Microsoft 365 をポイントする DNS レコードを更新している必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fc3-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="16fc3-116">DNS を更新して Microsoft 365 をポイントすると、この手順を完了するまで、既存のハイブリッド アプリケーション エンドポイントは検出できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="16fc3-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="16fc3-117">DNS レコードがオンプレミスを指している場合、この手順 (オンライン リソース アカウントの作成) は実行できないので、同じメンテナンス ウィンドウで手順 2 と 3 の両方を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fc3-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="16fc3-118">詳細については、「ハイブリッド構成を [無効にする」を参照してください](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="16fc3-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="16fc3-119">PowerShell コマンドで次のオンプレミスアプリケーションを実行して、オンプレミスのハイブリッド アプリケーション エンドポイントSkype for Business Serverエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="16fc3-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="16fc3-120">既存の[オンプレミスハイブリッド](/microsoftteams/manage-resource-accounts)アプリケーション エンドポイントMicrosoft 365置き換える新しいリソース アカウントを作成し、ライセンスします。</span><span class="sxs-lookup"><span data-stu-id="16fc3-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="16fc3-121">新しいリソース アカウントを既存のハイブリッド アプリケーション エンドポイントに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="16fc3-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="16fc3-122">PowerShell コマンドを実行して、オンプレミスハイブリッド アプリケーション エンドポイントで定義されている電話番号Skype for Business Server削除します。</span><span class="sxs-lookup"><span data-stu-id="16fc3-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="16fc3-123">これらのアカウントの電話番号は、オンプレミスではなく Microsoft 365 で管理されている可能性があります。オンライン PowerShell で次のコマンドSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="16fc3-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="16fc3-124">手順 2 で作成した新しいリソース アカウントに電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="16fc3-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="16fc3-125">電話番号をリソース アカウントに割り当てる方法の詳細については、「サービス番号を割り当てる」 [を参照してください](/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="16fc3-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="16fc3-126">PowerShell コマンドで次のオンプレミス エンドポイントを実行して、オンプレミスSkype for Business Server削除します。</span><span class="sxs-lookup"><span data-stu-id="16fc3-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="16fc3-127">これで、オンプレミスの展開[を削除するSkype for Business準備ができました](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="16fc3-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16fc3-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="16fc3-128">See also</span></span>

- [<span data-ttu-id="16fc3-129">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="16fc3-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="16fc3-130">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="16fc3-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="16fc3-131">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="16fc3-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="16fc3-132">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="16fc3-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




