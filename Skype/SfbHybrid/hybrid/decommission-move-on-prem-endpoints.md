---
title: ハイブリッド アプリケーション エンドポイントをクラウドに移動する
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
description: hyrid アプリケーション エンドポイントを移動してから、オンプレミス環境Skype for Business使用を停止します。
ms.openlocfilehash: 959a3ed47993f431636fe3c99b8502cf9aa634fe
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684384"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="bb18d-103">オンプレミス環境を使用停止する前にハイブリッド アプリケーション エンドポイントを移動する</span><span class="sxs-lookup"><span data-stu-id="bb18d-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="bb18d-104">この記事では、オンプレミスのアプリケーション 環境を使用停止する前に、必要なハイブリッド アプリケーション エンドポイントを Microsoft クラウドに移動するSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="bb18d-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="bb18d-105">これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。</span><span class="sxs-lookup"><span data-stu-id="bb18d-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="bb18d-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="bb18d-106">Step 1.</span></span> [<span data-ttu-id="bb18d-107">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="bb18d-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="bb18d-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="bb18d-108">Step 2.</span></span> <span data-ttu-id="bb18d-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="bb18d-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="bb18d-110">**手順 3.ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します。**</span><span class="sxs-lookup"><span data-stu-id="bb18d-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="bb18d-111">(この記事)</span><span class="sxs-lookup"><span data-stu-id="bb18d-111">(This article)</span></span>

- <span data-ttu-id="bb18d-112">手順 4.</span><span class="sxs-lookup"><span data-stu-id="bb18d-112">Step 4.</span></span> <span data-ttu-id="bb18d-113">[オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="bb18d-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="bb18d-114">必要なすべてのハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="bb18d-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="bb18d-115">これらのエンドポイントをオンラインに移動する前に、エンドポイントで使用されるすべての sip ドメインの Microsoft 365 をポイントする DNS レコードを更新している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb18d-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="bb18d-116">DNS レコードがオンプレミスを指している場合、オンライン リソース アカウントを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb18d-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="bb18d-117">詳細については、「ハイブリッド構成を [無効にする」を参照してください](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="bb18d-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="bb18d-118">PowerShell コマンドで次のオンプレミスアプリケーションを実行して、オンプレミスのハイブリッド アプリケーション エンドポイントSkype for Business Serverエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bb18d-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="bb18d-119">既存の[オンプレミスハイブリッド](/microsoftteams/manage-resource-accounts)アプリケーション エンドポイントMicrosoft 365置き換える新しいリソース アカウントを作成し、ライセンスします。</span><span class="sxs-lookup"><span data-stu-id="bb18d-119">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="bb18d-120">新しいリソース アカウントを既存のハイブリッド アプリケーション エンドポイントに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="bb18d-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="bb18d-121">PowerShell コマンドを実行して、オンプレミスハイブリッド アプリケーション エンドポイントで定義されている電話番号Skype for Business Server削除します。</span><span class="sxs-lookup"><span data-stu-id="bb18d-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="bb18d-122">これらのアカウントの電話番号は、オンプレミスではなく Microsoft 365 で管理されている可能性があります。オンライン PowerShell で次のコマンドSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="bb18d-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="bb18d-123">手順 2 で作成した新しいリソース アカウントに電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="bb18d-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="bb18d-124">電話番号をリソース アカウントに割り当てる方法の詳細については、「サービス番号を割り当てる」 [を参照してください](/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="bb18d-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="bb18d-125">PowerShell コマンドで次のオンプレミス エンドポイントを実行して、オンプレミスSkype for Business Server削除します。</span><span class="sxs-lookup"><span data-stu-id="bb18d-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="bb18d-126">これで、オンプレミスの展開[を削除するSkype for Business準備ができました](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="bb18d-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb18d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb18d-127">See also</span></span>

- [<span data-ttu-id="bb18d-128">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="bb18d-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="bb18d-129">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="bb18d-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="bb18d-130">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="bb18d-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="bb18d-131">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="bb18d-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




