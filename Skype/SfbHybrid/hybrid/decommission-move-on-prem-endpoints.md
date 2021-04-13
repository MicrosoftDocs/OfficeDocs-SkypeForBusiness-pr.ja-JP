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
description: Skype for Business オンプレミス環境を使用停止する前に、hyrid アプリケーション エンドポイントを移動します。
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656881"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="2f6e3-103">オンプレミス環境を使用停止する前に、hyrid アプリケーション エンドポイントを移動する</span><span class="sxs-lookup"><span data-stu-id="2f6e3-103">Move hyrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="2f6e3-104">この記事では、オンプレミスの Skype for Business 環境を使用停止する前に、必要なハイブリッド アプリケーション エンドポイントを Microsoft クラウドに移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="2f6e3-105">これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="2f6e3-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="2f6e3-106">Step 1.</span></span> [<span data-ttu-id="2f6e3-107">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="2f6e3-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="2f6e3-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="2f6e3-108">Step 2.</span></span> <span data-ttu-id="2f6e3-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="2f6e3-110">**手順 3.ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します。**</span><span class="sxs-lookup"><span data-stu-id="2f6e3-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="2f6e3-111">(この記事)</span><span class="sxs-lookup"><span data-stu-id="2f6e3-111">(This article)</span></span>

- <span data-ttu-id="2f6e3-112">手順 4.</span><span class="sxs-lookup"><span data-stu-id="2f6e3-112">Step 4.</span></span> <span data-ttu-id="2f6e3-113">[オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="2f6e3-114">必要なすべてのハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="2f6e3-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="2f6e3-115">これらのエンドポイントをオンラインに移動する前に、エンドポイントで使用されるすべての sip ドメインについて、Microsoft 365 をポイントする DNS レコードを更新している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="2f6e3-116">DNS レコードがオンプレミスを指している場合、オンライン リソース アカウントを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="2f6e3-117">詳細については、「ハイブリッド構成を [無効にする」を参照してください](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="2f6e3-118">次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスのハイブリッド アプリケーション エンドポイント設定を取得およびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="2f6e3-119">Microsoft 365 で新しい [リソース アカウント](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) を作成してライセンスを取得し、既存のオンプレミスハイブリッド アプリケーション エンドポイントを置き換える。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="2f6e3-120">新しいリソース アカウントを既存のハイブリッド アプリケーション エンドポイントに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="2f6e3-121">次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスハイブリッド アプリケーション エンドポイントで定義されている電話番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="2f6e3-122">これらのアカウントの電話番号は、オンプレミスではなく Microsoft 365 で管理されている可能性があります。Skype for Business Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="2f6e3-123">手順 2 で作成した新しいリソース アカウントに電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="2f6e3-124">電話番号をリソース アカウントに割り当てる方法の詳細については、「サービス番号を割り当てる」 [を参照してください](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="2f6e3-125">次のオンプレミス Skype for Business Server PowerShell コマンドを実行して、オンプレミスのエンドポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="2f6e3-126">これで、オンプレミスの [Skype for Business 展開を削除する準備ができました](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6e3-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f6e3-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f6e3-127">See also</span></span>

- [<span data-ttu-id="2f6e3-128">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="2f6e3-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="2f6e3-129">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="2f6e3-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="2f6e3-130">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="2f6e3-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="2f6e3-131">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="2f6e3-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




