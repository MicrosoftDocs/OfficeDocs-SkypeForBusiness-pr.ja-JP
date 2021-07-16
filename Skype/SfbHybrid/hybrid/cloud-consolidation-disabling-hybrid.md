---
title: ハイブリッドを無効にして移行を完了Teamsのみ
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この記事では、クラウド統合の一環としてハイブリッドを無効にするための詳細な手順について説明TeamsおよびSkype for Business。
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453646"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="1da50-103">ハイブリッド構成を無効にして、ハイブリッド構成への移行Teamsのみ</span><span class="sxs-lookup"><span data-stu-id="1da50-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="1da50-104">この記事では、オンプレミス環境を使用停止する前にハイブリッド構成を無効にするSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="1da50-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="1da50-105">これは、オンプレミス環境を使用停止するための次の手順の手順 2 です。</span><span class="sxs-lookup"><span data-stu-id="1da50-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="1da50-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="1da50-106">Step 1.</span></span> <span data-ttu-id="1da50-107">[必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="1da50-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="1da50-108">**手順 2.ハイブリッド構成を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="1da50-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="1da50-109">(この記事)</span><span class="sxs-lookup"><span data-stu-id="1da50-109">(This article)</span></span>

- <span data-ttu-id="1da50-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="1da50-110">Step 3.</span></span> <span data-ttu-id="1da50-111">[ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行します](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="1da50-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="1da50-112">手順 4.</span><span class="sxs-lookup"><span data-stu-id="1da50-112">Step 4.</span></span> <span data-ttu-id="1da50-113">[オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="1da50-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1da50-114">手順 2 と手順 3 は、手順 2 と手順 3 の完了の間に既存のハイブリッド アプリケーション エンドポイントを検出できないので、同じメンテナンス ウィンドウで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1da50-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="1da50-115">概要</span><span class="sxs-lookup"><span data-stu-id="1da50-115">Summary</span></span>

<span data-ttu-id="1da50-116">すべてのユーザーを Skype for Business オンプレミスから Teams のみ Microsoft 365 にアップグレードした後、オンプレミスの展開をSkype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="1da50-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="1da50-117">オンプレミスの Skype for Business 展開を使用停止し、ハードウェアを削除する前に、ハイブリッドを無効にして、オンプレミス展開と Microsoft 365を論理的に分離する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1da50-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="1da50-118">ハイブリッドの無効化は、次の 4 つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1da50-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="1da50-119">[DNS レコードを更新して、DNS レコードを参照Microsoft 365。](#update-dns-to-point-to-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="1da50-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="1da50-120">[組織の共存モードを [のみ] にTeamsします](#change-the-coexistence-mode-for-your-organization-to-teams-only)。</span><span class="sxs-lookup"><span data-stu-id="1da50-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="1da50-121">[組織で共有 SIP アドレス空間 ("分割ドメイン" とも呼ばれる) をMicrosoft 365します](#disable-shared-sip-address-space-in-microsoft-365-organization)。</span><span class="sxs-lookup"><span data-stu-id="1da50-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="1da50-122">オンプレミスとユーザー間の通信を無効Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1da50-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="1da50-123">次の手順では、オンプレミスの展開と Skype for Business Serverを論理的にMicrosoft 365、組織が完全にTeamsします。</span><span class="sxs-lookup"><span data-stu-id="1da50-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="1da50-124">これらの手順を完了したら、「使用停止後に属性を管理する方法を決定する」で参照されている 2 つの方法のいずれかを使用して、オンプレミスの Skype for Business 展開を使用停止[できます](cloud-consolidation-managing-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="1da50-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="1da50-125">この論理的な分離が完了すると、オンプレミスの Active Directory の msRTCSIP 属性には値が残り、Azure AD Connect を介して Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="1da50-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="1da50-126">オンプレミス環境を使用停止する方法は、これらの属性をそのままにするか、最初にオンプレミスの Active Directory から削除するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1da50-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="1da50-127">オンプレミスから移行した後にオンプレミスの msRTCSIP 属性をクリアすると、ユーザーのサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1da50-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="1da50-128">2 つの使用停止アプローチの詳細とトレードオフについては、「使用停止後に属性を管理する方法を決定する」 [を参照してください](cloud-consolidation-managing-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="1da50-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="1da50-129">DNS を更新して、ユーザーをポイントMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="1da50-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="1da50-130">オンプレミス組織の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミス展開ではなく Microsoft 365 を指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1da50-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="1da50-131">さらに、会議またはダイヤルインの CNAME レコード (存在する場合) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="1da50-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="1da50-132">最後に、内部ネットワーク内Skype for Business DNS レコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1da50-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="1da50-133">DNS レコードの更新の詳細については、「UPDATE DNS エントリを使用して組織をすべてのユーザーのみTeams[してください](decommission-manage-dns-entries.md)。</span><span class="sxs-lookup"><span data-stu-id="1da50-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="1da50-134">組織の共存モードを [共有のみ] にTeamsする</span><span class="sxs-lookup"><span data-stu-id="1da50-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="1da50-135">この手順では、組織内のすべての新しいユーザーが常に [ユーザーのみ] Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="1da50-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="1da50-136">テナント モードを Teams のみに変更しようとすると、手順 1 で見つからない可能性のあるオンプレミス DNS レコードが自動的に存在することを確認し、出力でこれらのレコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="1da50-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="1da50-137">テナント モードを [Teamsのみ] に変更すると、組織のすべての DNS レコードが更新されるまで成功しません。</span><span class="sxs-lookup"><span data-stu-id="1da50-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="1da50-138">テナント モードを [テナント モード] にTeams PowerShell ウィンドウから次のコマンドTeams実行します。</span><span class="sxs-lookup"><span data-stu-id="1da50-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="1da50-139">または、Teams 管理センターを使用して、[組織全体の設定] -> "Teams アップグレード" の下で、テナント共存モードを TeamsOnly に変更できます。</span><span class="sxs-lookup"><span data-stu-id="1da50-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="1da50-140">組織で共有 SIP アドレス空間をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="1da50-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="1da50-141">共有 SIP アドレス空間を無効にするには、PowerShell ウィンドウから次Teams実行します。</span><span class="sxs-lookup"><span data-stu-id="1da50-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="1da50-142">オンプレミスとユーザー間の通信を無効Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1da50-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="1da50-143">オンプレミス環境とサーバー間の通信を無効にするにはMicrosoft 365、オンプレミスの PowerShell ウィンドウから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1da50-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="1da50-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1da50-144">See also</span></span>

- [<span data-ttu-id="1da50-145">クラウドの統合 :TeamsとSkype for Business</span><span class="sxs-lookup"><span data-stu-id="1da50-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="1da50-146">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="1da50-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

