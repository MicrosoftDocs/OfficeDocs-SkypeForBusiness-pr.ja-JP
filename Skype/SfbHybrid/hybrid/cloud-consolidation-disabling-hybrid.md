---
title: ハイブリッドを無効にしてクラウドへの移行を完了する
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
description: この記事では、Teams と Skype for Business のクラウド統合の一環としてハイブリッドを無効にする詳細な手順について説明します。
ms.openlocfilehash: 90ec73246007542ad0215007b0da91f4fe9405e8
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874697"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a><span data-ttu-id="64cb0-103">ハイブリッドを無効にしてクラウドへの移行を完了する: 概要</span><span class="sxs-lookup"><span data-stu-id="64cb0-103">Disable hybrid to complete migration to the cloud: Overview</span></span>

<span data-ttu-id="64cb0-104">すべてのユーザーをオンプレミスからクラウドに移行した後は、オンプレミスの Skype for Business の配置を使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="64cb0-105">ハードウェアを削除する以外に、ハイブリッドを無効にして、オンプレミス展開を Microsoft 365 または Office 365 から論理的に分離する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="64cb0-106">ハイブリッドを無効にするには、3 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-106">Disabling hybrid consists of three steps:</span></span>

1. <span data-ttu-id="64cb0-107">Microsoft 365 または Microsoft 365 または 365 をポイントOffice更新します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="64cb0-108">Microsoft 365 または 365 組織で共有 SIP アドレス空間 ("スプリット ドメイン" とも呼ばれる) を無効Officeします。</span><span class="sxs-lookup"><span data-stu-id="64cb0-108">Disable shared sip address space (also known as "split domain") in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="64cb0-109">オンプレミスで Microsoft 365 または Microsoft 365 または Office無効にします。</span><span class="sxs-lookup"><span data-stu-id="64cb0-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="64cb0-110">次の手順では、Skype for Business Server のオンプレミス展開を Office 365 から論理的に分離し、1 つの単位として一緒に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-110">These steps logically separate your on-premise deployment of Skype for Business Server from Office 365 and should be done together as a unit.</span></span> <span data-ttu-id="64cb0-111">各手順の詳細については、以下の記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-111">Details for each step are provided in this article below.</span></span> <span data-ttu-id="64cb0-112">完了したら、以下で参照する 2 つの方法のいずれかを使用して、オンプレミスの Skype for Business Deployment を使用停止できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-112">Once that is complete, you can decommission your on-premises Skype for Business Deployment using one of two methods referenced below.</span></span>

> [!Important] 
><span data-ttu-id="64cb0-113">この論理的な分離が完了すると、オンプレミス Active Directory の msRTCSIP 属性には値が残り、Azure AD Connect を介して Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-113">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="64cb0-114">オンプレミス環境を使用停止する方法は、これらの属性をそのままにするか、最初にオンプレミスの Active Directory から削除するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-114">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="64cb0-115">オンプレミスから移行した後にオンプレミスの msRTCSIP 属性をクリアすると、ユーザーのサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-115">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="64cb0-116">2 つの使用停止の方法の詳細とトレードオフについては、後述します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-116">Details and tradeoffs of the two decommissioning approaches are described later below.</span></span>

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a><span data-ttu-id="64cb0-117">ハイブリッドを無効にしてクラウドへの移行を完了する: 詳細な手順</span><span class="sxs-lookup"><span data-stu-id="64cb0-117">Disable hybrid to complete migration to the cloud: Detailed Steps</span></span>

1. <span data-ttu-id="64cb0-118">*Microsoft 365 または 365 をポイントOffice DNS を更新します。*</span><span class="sxs-lookup"><span data-stu-id="64cb0-118">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span> <span data-ttu-id="64cb0-119">オンプレミス組織の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミス展開ではなく Microsoft 365 または Office 365 を指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-119">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="64cb0-120">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64cb0-120">Specifically:</span></span>

    |<span data-ttu-id="64cb0-121">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="64cb0-121">Record type</span></span>|<span data-ttu-id="64cb0-122">Name</span><span class="sxs-lookup"><span data-stu-id="64cb0-122">Name</span></span>|<span data-ttu-id="64cb0-123">TTL</span><span class="sxs-lookup"><span data-stu-id="64cb0-123">TTL</span></span>|<span data-ttu-id="64cb0-124">Value</span><span class="sxs-lookup"><span data-stu-id="64cb0-124">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="64cb0-125">SRV</span><span class="sxs-lookup"><span data-stu-id="64cb0-125">SRV</span></span>|<span data-ttu-id="64cb0-126">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="64cb0-126">_sipfederationtls._tcp</span></span>|<span data-ttu-id="64cb0-127">3600</span><span class="sxs-lookup"><span data-stu-id="64cb0-127">3600</span></span>|<span data-ttu-id="64cb0-128">100 1 5061 sipfed.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="64cb0-128">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="64cb0-129">SRV</span><span class="sxs-lookup"><span data-stu-id="64cb0-129">SRV</span></span>|<span data-ttu-id="64cb0-130">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="64cb0-130">_sip._tls</span></span>|<span data-ttu-id="64cb0-131">3600</span><span class="sxs-lookup"><span data-stu-id="64cb0-131">3600</span></span>|<span data-ttu-id="64cb0-132">100 1 443 sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="64cb0-132">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="64cb0-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="64cb0-133">CNAME</span></span>| <span data-ttu-id="64cb0-134">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="64cb0-134">lyncdiscover</span></span>|   <span data-ttu-id="64cb0-135">3600</span><span class="sxs-lookup"><span data-stu-id="64cb0-135">3600</span></span>|   <span data-ttu-id="64cb0-136">webdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="64cb0-136">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="64cb0-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="64cb0-137">CNAME</span></span>| <span data-ttu-id="64cb0-138">sip</span><span class="sxs-lookup"><span data-stu-id="64cb0-138">sip</span></span>|    <span data-ttu-id="64cb0-139">3600</span><span class="sxs-lookup"><span data-stu-id="64cb0-139">3600</span></span>|   <span data-ttu-id="64cb0-140">sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="64cb0-140">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="64cb0-141">さらに、会議またはダイヤルインの CNAME レコード (存在する場合) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-141">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="64cb0-142">最後に、内部ネットワーク内の Skype for Business の DNS レコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-142">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="64cb0-143">まれに、DNS をオンプレミスのポイントから Microsoft 365 または Office 365 に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが停止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-143">In rare cases, changing DNS from pointing on premises to Microsoft 365 or Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="64cb0-144">以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれる) を使用しているフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-144">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="64cb0-145">この従来のフェデレーション モデルは DNS SRV レコードに基づいていないので、組織がクラウドに移行すると、このような構成は古くなる。</span><span class="sxs-lookup"><span data-stu-id="64cb0-145">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="64cb0-146">sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。 <span>com は構成を更新して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-146">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="64cb0-147">この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとフェデレーションしたことがない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="64cb0-147">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="64cb0-148">このような場合、ホスティング プロバイダーを有効にするまで、これらの組織とのフェデレーションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="64cb0-148">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="64cb0-149">フェデレーション パートナーが直接フェデレーションを使用している可能性がある、またはオンラインまたはハイブリッド組織とフェデレーションしていないと疑われる場合は、クラウドへの移行を完了する準備をしている間に、この情報に関する通信を送信してください。</span><span class="sxs-lookup"><span data-stu-id="64cb0-149">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="64cb0-150">*Microsoft 365 または 365 組織の共有 sip アドレスOffice無効にします。*</span><span class="sxs-lookup"><span data-stu-id="64cb0-150">*Disable shared sip address space in Microsoft 365 or Office 365 organization.*</span></span> <span data-ttu-id="64cb0-151">次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="64cb0-152">*オンプレミスで Microsoft 365 または Microsoft 365 または Office無効にします。*</span><span class="sxs-lookup"><span data-stu-id="64cb0-152">*Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span> <span data-ttu-id="64cb0-153">以下のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-153">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="64cb0-154">オンプレミスからクラウドにユーザーを移動した後の属性の管理</span><span class="sxs-lookup"><span data-stu-id="64cb0-154">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="64cb0-155">既定では、Skype for Business Server で以前に有効にされ、その後クラウドに移動されたすべてのユーザーに、オンプレミスの Active Directory で msRTCSIP 属性が構成されています。</span><span class="sxs-lookup"><span data-stu-id="64cb0-155">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="64cb0-156">これらの属性、特に sip アドレス (msRTCSIP-PrimaryUserAddress) と電話番号 (msRTCSIP-Line) は、引き続き Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-156">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="64cb0-157">msRTCSIP 属性に対して変更が必要な場合は、オンプレミスの Active Directory でこれらの変更を行い、Azure AD に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-157">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="64cb0-158">ただし、Skype for Business Server 展開が削除されると、Skype for Business Server ツールを使用してこれらの属性を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="64cb0-158">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="64cb0-159">この状況を処理するには、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-159">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="64cb0-160">Skype for Business サーバー アカウントで有効にされたユーザーはそのままにし、Active Directory ツールを使用して msRTCSIP 属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-160">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="64cb0-161">これにより、移行されたユーザーのサービスが失われるのを防ぐので、完全な使用停止なしでサーバーを削除 (ワイプなど) することで、Skype for Business Server の展開を簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-161">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="64cb0-162">ただし、新しくライセンスを取得したユーザーは、オンプレミスの Active Directory にこれらの属性を設定し、オンラインで管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-162">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="64cb0-163">オンプレミスの Active Directory で移行されたユーザーからすべての msRTCSIP 属性をクリアし、オンライン ツールを使用してこれらの属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-163">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="64cb0-164">このメソッドを使用すると、既存のユーザーと新しいユーザーに対して一貫した管理アプローチが可能になりますが、オンプレミスの使用停止プロセス中に一時的にサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-164">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="64cb0-165">方法 1 - Active Directory でユーザーの SIP アドレスと電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="64cb0-165">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="64cb0-166">管理者は、オンプレミスの展開が使用停止された後でも、オンプレミスの Skype for Business Server からクラウドに以前に移動されたユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-166">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="64cb0-167">ユーザーの SIP アドレスまたはユーザーの電話番号 (および sip アドレスまたは電話番号に既にオンプレミスの Active Directory に値が含まれる) を変更する場合は、オンプレミスの Active Directory でこれを行い、値を Azure AD に流す必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-167">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="64cb0-168">これは、オンプレミスの Skype for Business Server を必要としません。</span><span class="sxs-lookup"><span data-stu-id="64cb0-168">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="64cb0-169">代わりに、Active Directory ユーザーとコンピューター MMC スナップイン (以下に示す) を使用するか、PowerShell を使用して、オンプレミスの Active Directory でこれらの属性を直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-169">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="64cb0-170">MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を探します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-170">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="64cb0-171">ユーザーの sip アドレスを変更するには、 を変更します `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="64cb0-171">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="64cb0-172">属性に sip `ProxyAddresses` アドレスが含まれている場合は、その値もベスト プラクティスとして更新してください。</span><span class="sxs-lookup"><span data-stu-id="64cb0-172">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="64cb0-173">入力されている場合、SIP アドレスは O365 によって無視されます。ただし、他のオンプレミス コンポーネント `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` で使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-173">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="64cb0-174">ユーザーの電話番号を変更するには、値 `msRTCSIP-Line` *が既に設定されている場合に変更します*。</span><span class="sxs-lookup"><span data-stu-id="64cb0-174">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory ユーザーとコンピューター ツール](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="64cb0-176">ユーザーが移動前にオンプレミスの値を持っていなかった場合は、Skype for Business Online PowerShell モジュールの `msRTCSIP-Line` `onpremLineUri` [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) コマンドレットの - パラメーターを使用して電話番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-176">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="64cb0-177">これらの手順は、ハイブリッドを無効にした後に作成された新しいユーザーには必要ありません。また、それらのユーザーはクラウドで直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-177">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="64cb0-178">これらのメソッドを組み合わせ、msRTCSIP 属性をオンプレミスの Active Directory に置き去りにする場合は、オンプレミスの Skype for Business サーバーを簡単に再イメージできます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-178">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="64cb0-179">ただし、すべての msRTCSIP 属性をクリアし、Skype for Business Server の従来のアンインストールを行う場合は、方法 2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-179">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="64cb0-180">方法 2 - Active Directory のすべてのオンプレミス ユーザーの Skype for Business 属性をクリアする</span><span class="sxs-lookup"><span data-stu-id="64cb0-180">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="64cb0-181">このオプションでは、オンプレミスの Skype for Business Server からクラウドに移動したユーザーを再プロビジョニングする必要があるため、追加の作業と適切な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="64cb0-181">This option requires additional effort and proper planning because users that were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="64cb0-182">これらのユーザーは、電話システムのないユーザーと電話システムを持つユーザーの 2 つの異なるカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-182">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="64cb0-183">電話システムを使用しているユーザーは、オンプレミスの Active Directory で管理されている電話番号からクラウドへの移行の一環として、電話サービスが一時的に失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-183">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="64cb0-184">**一括ユーザー操作を開始する前に、電話システムを使用するユーザーの数が少ないパイロットを実行してください。**</span><span class="sxs-lookup"><span data-stu-id="64cb0-184">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="64cb0-185">大規模な展開では、ユーザーは異なるタイム ウィンドウ内の小さなグループで処理できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-185">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE]
> <span data-ttu-id="64cb0-186">このプロセスは、一致する sip アドレスと UserPrincipalName を持つユーザーに対して最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="64cb0-186">The process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="64cb0-187">これら 2 つの属性で一致しない値を持つユーザーを持つ組織では、スムーズな移行を行う場合は、以下の点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-187">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span> 


1. <span data-ttu-id="64cb0-188">次のオンプレミスの Skype for Business PowerShell コマンドレットが空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-188">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="64cb0-189">空の結果は、ユーザーがオンプレミスにいて、365 から 365 に移動Office無効になっている場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-189">An empty result means no users are homed on-premises and have either been moved to Office 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="64cb0-190">次のオンプレミスの Skype for Business Server PowerShell コマンドレットを実行して、ユーザーの現在の電話番号 (LineUri)、UserPrincipalName、および関連情報を記録し、ユーザー データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="64cb0-190">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="64cb0-191">ファイルを開いてSfbUserSettings.csv、すべてのユーザー データが正常にエクスポートされたことを確認する前に。</span><span class="sxs-lookup"><span data-stu-id="64cb0-191">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="64cb0-192">このファイルのコピーを保持してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64cb0-192">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="64cb0-193">ユーザーの処理には、次の手順でこのファイルを使用しない。</span><span class="sxs-lookup"><span data-stu-id="64cb0-193">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="64cb0-194">次の手順で使用するユーザーのグループを含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-194">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="64cb0-195">ユーザーの最初のグループが正常に完了したら、次のユーザー グループに進みます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-195">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="64cb0-196">次の例では、ユーザーのグループがアルファベット順に選択されますが、ユーザーの処理方法に一致する条件に基づいてユーザーにフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-196">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="64cb0-197">ファイルを開いてSfbUsers.csv、ユーザー データが正常にエクスポートされたことを確認する前に。</span><span class="sxs-lookup"><span data-stu-id="64cb0-197">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="64cb0-198">後の手順で、このファイルから LineUri (電話番号)、UserPrincipalName、SamAccountName、SipAddress が必要になります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-198">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="64cb0-199">更新する準備ができている一連のユーザーのアクティブ ディレクトリから Skype for Business Server に関連する属性情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-199">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="64cb0-200">以下に示すように、このプロセスには 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-200">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="64cb0-201">この手順を実行した後の次の AAD 同期サイクルの後、以前にオンプレミスの Skype for Business Server からクラウドに移動された電話システムを持つユーザーは、手順 8 が正常に完了して手順 9 で確認されるまで、通話を送受信する機能を失います。</span><span class="sxs-lookup"><span data-stu-id="64cb0-201">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="64cb0-202">また、手順 2 に基いてユーザーの電話番号と関連情報を保存済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="64cb0-202">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="64cb0-203">次に、同じユーザー セットについて、オンプレミスの Active Directory PowerShell を使用して msRTCSIP-DeploymentLocator の値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="64cb0-203">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="64cb0-204">次のオンプレミスの Skype for Business PowerShell コマンドレットを実行して、オンプレミスの Active Directory proxyAddresses に sip アドレス値を追加します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-204">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="64cb0-205">これにより、この属性に依存する相互運用性の問題が防止されます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-205">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="64cb0-206">Azure AD同期を実行する</span><span class="sxs-lookup"><span data-stu-id="64cb0-206">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="64cb0-207">ユーザー プロビジョニングが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-207">Wait for user provisioning to complete.</span></span> <span data-ttu-id="64cb0-208">次の Skype for Business Online PowerShell コマンドを実行して、ユーザー プロビジョニングの進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="64cb0-208">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="64cb0-209">次の Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-209">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="64cb0-210">次の Skype for Business Online PowerShell コマンドを実行して電話番号を割り当て、電話システムのユーザーを有効にする。</span><span class="sxs-lookup"><span data-stu-id="64cb0-210">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="64cb0-211">Skype for Business エンドポイント (Skype クライアントまたはサードパーティ製電話) がまだ存在する場合は、-HostedVoiceMail を $true に設定します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-211">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="64cb0-212">組織で音声が有効なユーザーに Teams エンドポイントのみを使用している場合、この設定はユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="64cb0-212">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="64cb0-213">電話システム機能を持つユーザーが正しくプロビジョニングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-213">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="64cb0-214">次の Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-214">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="64cb0-215">すべてのユーザーが処理されるまで、手順 3 ~ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-215">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="64cb0-216">次の 2 つの PowerShell コマンドを実行して、すべてのユーザーが正常に処理されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="64cb0-216">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="64cb0-217">オンプレミスの Skype for Business Server オンプレミス PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="64cb0-217">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="64cb0-218">Skype for Business Online PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="64cb0-218">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a><span data-ttu-id="64cb0-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="64cb0-219">See also</span></span>

[<span data-ttu-id="64cb0-220">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="64cb0-220">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
