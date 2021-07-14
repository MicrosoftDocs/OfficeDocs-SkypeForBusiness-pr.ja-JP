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
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420842"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="6e595-103">ハイブリッド構成を無効にして、ハイブリッド構成への移行Teamsのみ</span><span class="sxs-lookup"><span data-stu-id="6e595-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="6e595-104">この記事では、オンプレミス環境を使用停止する前にハイブリッド構成を無効にするSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="6e595-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="6e595-105">これは、オンプレミス環境を使用停止するための次の手順の手順 2 です。</span><span class="sxs-lookup"><span data-stu-id="6e595-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="6e595-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="6e595-106">Step 1.</span></span> <span data-ttu-id="6e595-107">[必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="6e595-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="6e595-108">**手順 2.ハイブリッド構成を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="6e595-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="6e595-109">(この記事)</span><span class="sxs-lookup"><span data-stu-id="6e595-109">(This article)</span></span>

- <span data-ttu-id="6e595-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="6e595-110">Step 3.</span></span> <span data-ttu-id="6e595-111">[ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行します](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="6e595-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="6e595-112">手順 4.</span><span class="sxs-lookup"><span data-stu-id="6e595-112">Step 4.</span></span> <span data-ttu-id="6e595-113">[オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="6e595-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6e595-114">手順 2 と手順 3 は、手順 2 と手順 3 の完了の間に既存のハイブリッド アプリケーション エンドポイントを検出できないので、同じメンテナンス ウィンドウで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>

## <a name="overview"></a><span data-ttu-id="6e595-115">概要</span><span class="sxs-lookup"><span data-stu-id="6e595-115">Overview</span></span>

<span data-ttu-id="6e595-116">すべてのユーザーを Skype for Business オンプレミスから Teams のみ Microsoft 365 にアップグレードした後、オンプレミスの展開をSkype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="6e595-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6e595-117">オンプレミスの Skype for Business 展開を使用停止し、ハードウェアを削除する前に、ハイブリッドを無効にして、オンプレミス展開と Microsoft 365を論理的に分離する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="6e595-118">ハイブリッドの無効化は、次の 4 つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6e595-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="6e595-119">Microsoft 365 を指すように DNS レコードを更新する。</span><span class="sxs-lookup"><span data-stu-id="6e595-119">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="6e595-120">組織の共存モードを [のみ] にTeamsします。</span><span class="sxs-lookup"><span data-stu-id="6e595-120">Change the coexistence mode for your organization to Teams Only.</span></span>

3. <span data-ttu-id="6e595-121">組織で共有 SIP アドレス空間 ("分割ドメイン" とも呼ばれる) を無効Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="6e595-121">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

4. <span data-ttu-id="6e595-122">オンプレミスでユーザーと通信する機能を無効Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6e595-122">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="6e595-123">次の手順では、オンプレミスの展開と Skype for Business Serverを論理的にMicrosoft 365、組織が完全にTeamsします。</span><span class="sxs-lookup"><span data-stu-id="6e595-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="6e595-124">各手順の詳細については、この記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="6e595-124">Details for each step are provided in this article.</span></span> <span data-ttu-id="6e595-125">完了したら、以下で参照する 2 つのSkype for Businessを使用して、オンプレミスの展開を停止できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-125">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="6e595-126">この論理的な分離が完了すると、オンプレミスの Active Directory の msRTCSIP 属性には値が残り、Azure AD Connect を介して Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="6e595-126">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="6e595-127">オンプレミス環境を使用停止する方法は、これらの属性をそのままにするか、最初にオンプレミスの Active Directory から削除するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6e595-127">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="6e595-128">オンプレミスから移行した後にオンプレミスの msRTCSIP 属性をクリアすると、ユーザーのサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-128">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="6e595-129">2 つの使用停止アプローチの詳細とトレードオフについては、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="6e595-129">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="6e595-130">詳細な手順</span><span class="sxs-lookup"><span data-stu-id="6e595-130">Detailed Steps</span></span>

1. <span data-ttu-id="6e595-131">*DNS を更新して、DNS をポイントMicrosoft 365。*</span><span class="sxs-lookup"><span data-stu-id="6e595-131">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="6e595-132">オンプレミス組織の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミス展開ではなく Microsoft 365 を指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-132">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="6e595-133">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e595-133">Specifically:</span></span>

    |<span data-ttu-id="6e595-134">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="6e595-134">Record type</span></span>|<span data-ttu-id="6e595-135">名前</span><span class="sxs-lookup"><span data-stu-id="6e595-135">Name</span></span>|<span data-ttu-id="6e595-136">TTL</span><span class="sxs-lookup"><span data-stu-id="6e595-136">TTL</span></span>|<span data-ttu-id="6e595-137">優先度</span><span class="sxs-lookup"><span data-stu-id="6e595-137">Priority</span></span>|<span data-ttu-id="6e595-138">太さ</span><span class="sxs-lookup"><span data-stu-id="6e595-138">Weight</span></span>|<span data-ttu-id="6e595-139">ポート</span><span class="sxs-lookup"><span data-stu-id="6e595-139">Port</span></span>|<span data-ttu-id="6e595-140">Value</span><span class="sxs-lookup"><span data-stu-id="6e595-140">Value</span></span>|
    |---|---|---|---|---|---|---|
    |<span data-ttu-id="6e595-141">SRV</span><span class="sxs-lookup"><span data-stu-id="6e595-141">SRV</span></span>|<span data-ttu-id="6e595-142">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="6e595-142">_sipfederationtls._tcp</span></span>|<span data-ttu-id="6e595-143">3600</span><span class="sxs-lookup"><span data-stu-id="6e595-143">3600</span></span>|<span data-ttu-id="6e595-144">100</span><span class="sxs-lookup"><span data-stu-id="6e595-144">100</span></span>|<span data-ttu-id="6e595-145">1</span><span class="sxs-lookup"><span data-stu-id="6e595-145">1</span></span>|<span data-ttu-id="6e595-146">5061</span><span class="sxs-lookup"><span data-stu-id="6e595-146">5061</span></span>|<span data-ttu-id="6e595-147">sipfed.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6e595-147">sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6e595-148">SRV</span><span class="sxs-lookup"><span data-stu-id="6e595-148">SRV</span></span>|<span data-ttu-id="6e595-149">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6e595-149">_sip._tls</span></span>|<span data-ttu-id="6e595-150">3600</span><span class="sxs-lookup"><span data-stu-id="6e595-150">3600</span></span>|<span data-ttu-id="6e595-151">100</span><span class="sxs-lookup"><span data-stu-id="6e595-151">100</span></span>|<span data-ttu-id="6e595-152">1</span><span class="sxs-lookup"><span data-stu-id="6e595-152">1</span></span>|<span data-ttu-id="6e595-153">443</span><span class="sxs-lookup"><span data-stu-id="6e595-153">443</span></span>|<span data-ttu-id="6e595-154">sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6e595-154">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6e595-155">CNAME</span><span class="sxs-lookup"><span data-stu-id="6e595-155">CNAME</span></span>| <span data-ttu-id="6e595-156">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6e595-156">lyncdiscover</span></span>|   <span data-ttu-id="6e595-157">3600</span><span class="sxs-lookup"><span data-stu-id="6e595-157">3600</span></span>| | | |<span data-ttu-id="6e595-158">webdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6e595-158">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6e595-159">CNAME</span><span class="sxs-lookup"><span data-stu-id="6e595-159">CNAME</span></span>| <span data-ttu-id="6e595-160">sip</span><span class="sxs-lookup"><span data-stu-id="6e595-160">sip</span></span>|    <span data-ttu-id="6e595-161">3600</span><span class="sxs-lookup"><span data-stu-id="6e595-161">3600</span></span>| | | | <span data-ttu-id="6e595-162">sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6e595-162">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="6e595-163">さらに、会議またはダイヤルインの CNAME レコード (存在する場合) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-163">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="6e595-164">最後に、内部ネットワーク内Skype for Business DNS レコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-164">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="6e595-165">まれに、組織の DNS をオンプレミスのポイントから Microsoft 365 に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-165">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="6e595-166">以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれる) を使用しているフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-166">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="6e595-167">この従来のフェデレーション モデルは DNS SRV レコードに基づいていないので、組織がクラウドに移行すると、このような構成は古くなる。</span><span class="sxs-lookup"><span data-stu-id="6e595-167">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="6e595-168">sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。 <span>com は構成を更新して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-168">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="6e595-169">この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとフェデレーションしたことがない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="6e595-169">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="6e595-170">このような場合、ホスティング プロバイダーを有効にするまで、これらの組織とのフェデレーションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6e595-170">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="6e595-171">フェデレーション パートナーが直接フェデレーションを使用している可能性がある、またはオンラインまたはハイブリッド組織とフェデレーションしていないと疑われる場合は、クラウドへの移行を完了する準備をしている間に、この情報に関する通信を送信してください。</span><span class="sxs-lookup"><span data-stu-id="6e595-171">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="6e595-172">*組織の共存モードを [のみ] にTeamsします。*</span><span class="sxs-lookup"><span data-stu-id="6e595-172">*Change the coexistence mode for your organization to Teams Only.*</span></span> <span data-ttu-id="6e595-173">これにより、組織内のすべての新しいユーザーが常に [ユーザーのみ] Teams作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e595-173">This ensures that any new user in your organization is always created as a Teams Only user.</span></span> <span data-ttu-id="6e595-174">さらに、テナント モードを Teams のみに変更しようとすると、手順 1 で見つからない可能性のあるオンプレミス DNS レコードが自動的に存在することを確認し、出力でこれらのレコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="6e595-174">In addition,  attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span>  <span data-ttu-id="6e595-175">テナント モードを [Teamsのみ] に変更すると、組織用のすべての DNS レコードが更新されるまで成功しません。</span><span class="sxs-lookup"><span data-stu-id="6e595-175">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organizaiton are updated.</span></span> <span data-ttu-id="6e595-176">テナント モードを [テナント モード] にTeams PowerShell ウィンドウから次のコマンドTeams実行します。</span><span class="sxs-lookup"><span data-stu-id="6e595-176">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
<span data-ttu-id="6e595-177">または、Teams 管理センターを使用して、[組織全体の設定] -> "Teams アップグレード" の下で、テナント共存モードを TeamsOnly に変更できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-177">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    
    
3.  <span data-ttu-id="6e595-178">*組織で共有 SIP アドレス空間をMicrosoft 365します。*</span><span class="sxs-lookup"><span data-stu-id="6e595-178">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="6e595-179">次のコマンドは、PowerShell ウィンドウから実行Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-179">The command below needs to be done from a Teams PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  <span data-ttu-id="6e595-180">*オンプレミスでユーザーと通信する機能を無効Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="6e595-180">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="6e595-181">以下のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-181">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="6e595-182">オンプレミスからクラウドにユーザーを移動した後の属性の管理</span><span class="sxs-lookup"><span data-stu-id="6e595-182">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="6e595-183">既定では、以前に Skype for Business Server に対して有効にされ、その後クラウドに移動されたすべてのユーザーに、オンプレミスの Active Directory で msRTCSIP 属性が構成されています。</span><span class="sxs-lookup"><span data-stu-id="6e595-183">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="6e595-184">これらの属性、特に sip アドレス (msRTCSIP-PrimaryUserAddress) と電話番号 (msRTCSIP-Line) は、引き続き Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="6e595-184">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="6e595-185">msRTCSIP 属性に対して変更が必要な場合は、オンプレミスの Active Directory でこれらの変更を行い、Azure AD に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-185">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="6e595-186">ただし、Skype for Business Server展開が削除されると、これらの属性Skype for Business Serverツールを使用できません。</span><span class="sxs-lookup"><span data-stu-id="6e595-186">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="6e595-187">この状況を処理するには、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="6e595-187">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="6e595-188">サーバー アカウントに対して有効Skype for Businessユーザーはそのままにし、Active Directory ツールを使用して msRTCSIP 属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="6e595-188">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="6e595-189">これにより、移行されたユーザーのサービスが失われるのを防ぐので、完全な使用停止なしでサーバーを削除 (ワイプなど) することで、Skype for Business Server 展開を簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-189">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="6e595-190">ただし、新しくライセンスを取得したユーザーは、オンプレミスの Active Directory にこれらの属性を設定し、オンラインで管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-190">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="6e595-191">オンプレミスの Active Directory で移行されたユーザーからすべての msRTCSIP 属性をクリアし、オンライン ツールを使用してこれらの属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="6e595-191">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="6e595-192">このメソッドを使用すると、既存のユーザーと新しいユーザーに対して一貫した管理アプローチが可能になりますが、オンプレミスの使用停止プロセス中に一時的にサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-192">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="6e595-193">方法 1 - Active Directory でユーザーの SIP アドレスと電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="6e595-193">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="6e595-194">管理者は、オンプレミス展開が使用停止された後でも、Skype for Business Serverからクラウドに移動されたユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-194">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="6e595-195">ユーザーの SIP アドレスまたはユーザーの電話番号 (および sip アドレスまたは電話番号に既にオンプレミスの Active Directory に値が含まれる) を変更する場合は、オンプレミスの Active Directory でこれを行い、値を Azure AD に流す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-195">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="6e595-196">これは、オンプレミスのデータを必要とSkype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="6e595-196">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="6e595-197">代わりに、Active Directory ユーザーとコンピューター MMC スナップイン (以下に示す) を使用するか、PowerShell を使用して、オンプレミスの Active Directory でこれらの属性を直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-197">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="6e595-198">MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を探します。</span><span class="sxs-lookup"><span data-stu-id="6e595-198">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="6e595-199">ユーザーの sip アドレスを変更するには、 を変更します `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="6e595-199">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e595-200">属性に `ProxyAddresses` sip アドレスが含まれている場合は、その値もベスト プラクティスとして更新します。</span><span class="sxs-lookup"><span data-stu-id="6e595-200">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="6e595-201">入力されている場合、SIP アドレスは O365 によって無視されます。ただし、他のオンプレミス コンポーネント `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` で使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-201">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="6e595-202">ユーザーの電話番号を変更するには、値 `msRTCSIP-Line` *が既に設定されている場合に変更します*。</span><span class="sxs-lookup"><span data-stu-id="6e595-202">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory ユーザーとコンピューター ツール](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="6e595-204">ユーザーが移動前にオンプレミスの値を持っていなかった場合は、Skype for Business Online PowerShell モジュールの `msRTCSIP-Line` `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットの - パラメーターを使用して電話番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-204">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="6e595-205">これらの手順は、ハイブリッドを無効にした後に作成された新しいユーザーには必要ありません。また、それらのユーザーはクラウドで直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-205">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="6e595-206">これらのメソッドを組み合わせ、msRTCSIP 属性をオンプレミスの Active Directory に配置した状態にした方が快適な場合は、オンプレミスの Skype for Business サーバーをイメージしSkype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="6e595-206">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="6e595-207">ただし、すべての msRTCSIP 属性をクリアし、従来のアンインストールを実行する場合は、Skype for Business Server 2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e595-207">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="6e595-208">方法 2 - Active Directory Skype for Businessオンプレミス ユーザーの属性をクリアする</span><span class="sxs-lookup"><span data-stu-id="6e595-208">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="6e595-209">このオプションでは、以前にオンプレミスのユーザーからクラウドに移動されたユーザー Skype for Business Server再プロビジョニングが必要なので、追加の作業と適切な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="6e595-209">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="6e595-210">これらのユーザーは、2 つの異なるカテゴリに分類できます 電話システム 電話システム。</span><span class="sxs-lookup"><span data-stu-id="6e595-210">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="6e595-211">ユーザーが電話システム、オンプレミスの Active Directory で管理される電話番号をクラウドに移行する一環として、電話サービスが一時的に失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-211">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="6e595-212">**一括ユーザー操作を開始する前に、ユーザー数の少ないユーザーを含むパイロットを電話システムをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="6e595-212">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="6e595-213">大規模な展開では、ユーザーは異なるタイム ウィンドウ内の小さなグループで処理できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-213">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="6e595-214">このプロセスは、一致する sip アドレスと UserPrincipalName を持つユーザーに対して最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="6e595-214">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="6e595-215">これら 2 つの属性で一致しない値を持つユーザーを持つ組織では、スムーズな移行を行う場合は、以下の点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-215">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="6e595-216">自動応答または通話キュー用にオンプレミスハイブリッド アプリケーション エンドポイントを構成している場合は、これらのエンドポイントを Microsoft 365 に移動してから、Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="6e595-216">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="6e595-217">PowerShell コマンドレットが空の結果をSkype for Business次のオンプレミスのコマンドレットを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e595-217">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="6e595-218">空の結果は、ユーザーがオンプレミスにいて、ユーザーに移動された、または無効になっているMicrosoft 365意味します。</span><span class="sxs-lookup"><span data-stu-id="6e595-218">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="6e595-219">次のオンプレミスの Skype for Business Server PowerShell コマンドレットを実行して、ユーザーの現在の電話番号 (LineUri)、UserPrincipalName、および関連情報を記録し、ユーザー データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6e595-219">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="6e595-220">ファイルを開いてSfbUserSettings.csv、すべてのユーザー データが正常にエクスポートされたことを確認する前に。</span><span class="sxs-lookup"><span data-stu-id="6e595-220">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="6e595-221">このファイルのコピーを保持してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e595-221">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="6e595-222">ユーザーの処理には、次の手順でこのファイルを使用しない。</span><span class="sxs-lookup"><span data-stu-id="6e595-222">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="6e595-223">次の手順で使用するユーザーのグループを含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e595-223">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="6e595-224">ユーザーの最初のグループが正常に完了したら、次のユーザー グループに進みます。</span><span class="sxs-lookup"><span data-stu-id="6e595-224">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="6e595-225">次の例では、ユーザーのグループがアルファベット順に選択されますが、ユーザーの処理方法に一致する条件に基づいてユーザーにフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="6e595-225">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="6e595-226">ファイルを開いてSfbUsers.csv、ユーザー データが正常にエクスポートされたことを確認する前に。</span><span class="sxs-lookup"><span data-stu-id="6e595-226">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="6e595-227">後の手順で、このファイルから LineUri (電話番号)、UserPrincipalName、SamAccountName、SipAddress が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6e595-227">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="6e595-228">更新する準備ができている一連のユーザー Skype for Business Server Active Directory から、ユーザーに関連する属性情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="6e595-228">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="6e595-229">以下に示すように、このプロセスには 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-229">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="6e595-230">この手順を実行した後の次の AAD Sync サイクルの後、以前にオンプレミス Skype for Business Server からクラウドに移動された 電話システム を持つユーザーは、手順 8 が正常に完了して手順 9 で確認されるまで、通話を送受信する機能を失います。</span><span class="sxs-lookup"><span data-stu-id="6e595-230">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="6e595-231">また、手順 2 に基いてユーザーの電話番号と関連情報を保存済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e595-231">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="6e595-232">次に、同じユーザー セットについて、オンプレミスの Active Directory PowerShell を使用して msRTCSIP-DeploymentLocator の値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6e595-232">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="6e595-233">次のオンプレミス Active Directory モジュールを実行して、Windows PowerShell コマンドレットを実行して、オンプレミスの Active Directory proxyAddresses に sip アドレス値を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e595-233">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="6e595-234">これにより、この属性に依存する相互運用性の問題が防止されます。</span><span class="sxs-lookup"><span data-stu-id="6e595-234">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="6e595-235">実行Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="6e595-235">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="6e595-236">ユーザー プロビジョニングが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e595-236">Wait for user provisioning to complete.</span></span> <span data-ttu-id="6e595-237">ユーザー プロビジョニングの進行状況を監視するには、次の [オンライン PowerShell] コマンドSkype for Business実行します。</span><span class="sxs-lookup"><span data-stu-id="6e595-237">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="6e595-238">次の手順Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="6e595-238">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="6e595-239">[オンライン PowerShell] Skype for Businessを実行して電話番号を割り当て、ユーザーに電話番号を割り当電話システム。</span><span class="sxs-lookup"><span data-stu-id="6e595-239">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="6e595-240">引き続き Skype for Businessエンドポイント (Skype クライアントまたはサードパーティの電話) がある場合は、-HostedVoiceMail を $true に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e595-240">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="6e595-241">組織が音声が有効なユーザー Teamsエンドポイントのみを使用している場合、この設定はユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="6e595-241">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="6e595-242">機能が正電話システムユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e595-242">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="6e595-243">次の手順Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="6e595-243">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="6e595-244">すべてのユーザーが処理されるまで、手順 3 ~ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6e595-244">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="6e595-245">次の 2 つの PowerShell コマンドを実行して、すべてのユーザーが正常に処理されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e595-245">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="6e595-246">オンプレミスの PowerShell Skype for Business Serverを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e595-246">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="6e595-247">Skype for Businessオンライン PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="6e595-247">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="6e595-248">方法 2 のすべての手順を完了したら、「ハイブリッド[](decommission-move-on-prem-endpoints.md)アプリケーション エンドポイントをオンプレミスからオンラインに移動する」および「オンプレミス[Skype for Business Server](decommission-remove-on-prem.md)を削除する」を参照して、Skype for Business Server オンプレミス展開を削除する追加の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e595-248">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="6e595-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e595-249">See also</span></span>

- [<span data-ttu-id="6e595-250">クラウドの統合 :TeamsとSkype for Business</span><span class="sxs-lookup"><span data-stu-id="6e595-250">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="6e595-251">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="6e595-251">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

