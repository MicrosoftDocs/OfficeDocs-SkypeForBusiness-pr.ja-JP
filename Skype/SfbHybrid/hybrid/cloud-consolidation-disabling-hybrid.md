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
description: この付録には、Teams と Skype for Business のクラウド統合の一部としてハイブリッドを無効にするための詳細な手順が含まれています。
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173973"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="4455a-103">ハイブリッドを無効にしてクラウドへの移行を完了する</span><span class="sxs-lookup"><span data-stu-id="4455a-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="4455a-104">すべてのユーザーをオンプレミスからクラウドに移行した後は、オンプレミスの Skype for Business の配置を使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4455a-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="4455a-105">ハードウェアを削除する以外に、重要なステップとして、ハイブリッドを無効にすることによってオンプレミスの配置を Office 365 から論理的に分離します。</span><span class="sxs-lookup"><span data-stu-id="4455a-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="4455a-106">ハイブリッドの無効化は、3つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4455a-106">Disabling hybrid consists of 3 steps:</span></span>

- <span data-ttu-id="4455a-107">Office 365 を指すようにドメインの DNS レコードを更新する。</span><span class="sxs-lookup"><span data-stu-id="4455a-107">Update DNS records to point to Office 365.</span></span>
- <span data-ttu-id="4455a-108">Office 365 組織の分割ドメインを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4455a-108">Disable split domain in the Office 365 organization.</span></span>
- <span data-ttu-id="4455a-109">オンプレミスの Office 365 との通信機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4455a-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="4455a-110">これらの手順は、1つの単位として一緒に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="4455a-111">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4455a-111">Details are provided below.</span></span> <span data-ttu-id="4455a-112">また、オンプレミスの展開が切断されると、移行されたユーザーの電話番号を管理するためのガイドラインが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4455a-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Important] 
><span data-ttu-id="4455a-113">Azure ad Connect into Azure AD を使用して、Active Directory 同期の msRTCSIP 属性を引き続き使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-113">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="4455a-114">サポートからの指示がない限り、これらの属性はクリアしないでください。</span><span class="sxs-lookup"><span data-stu-id="4455a-114">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="4455a-115">オンプレミス環境では、Disable-CsUser を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="4455a-115">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="4455a-116">ユーザーの SIP アドレスを変更する必要がある場合は、オンプレミスの Active Directory でこれを実行し、以下に説明するように Azure AD Connect を使用して azure AD にこの変更を同期させます。</span><span class="sxs-lookup"><span data-stu-id="4455a-116">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="4455a-117">同様に、電話番号を変更する必要があり、ユーザーの LineURI が既にオンプレミスで定義されている場合は、オンプレミスの Active Directory でこれを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-117">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="4455a-118">オンプレミスから移行した後でオンプレミスの msRTCSIP 属性をオフにすると、ユーザーのサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-118">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>



1.  <span data-ttu-id="4455a-119">*Office 365 を指すように DNS を更新します。*</span><span class="sxs-lookup"><span data-stu-id="4455a-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="4455a-120">社内組織の既存の外部 DNS レコードを更新して、Skype for Business レコードがオンプレミス展開ではなく Office 365 をポイントできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-120">The organization’s existing external DNS records for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="4455a-121">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4455a-121">Specifically:</span></span>

    |<span data-ttu-id="4455a-122">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="4455a-122">Record type</span></span>|<span data-ttu-id="4455a-123">名前</span><span class="sxs-lookup"><span data-stu-id="4455a-123">Name</span></span>|<span data-ttu-id="4455a-124">TTL</span><span class="sxs-lookup"><span data-stu-id="4455a-124">TTL</span></span>|<span data-ttu-id="4455a-125">値</span><span class="sxs-lookup"><span data-stu-id="4455a-125">Value</span></span>|<span data-ttu-id="4455a-126">用途</span><span class="sxs-lookup"><span data-stu-id="4455a-126">Purpose</span></span>|
    |---|---|---|---|---|
    |<span data-ttu-id="4455a-127">SRV</span><span class="sxs-lookup"><span data-stu-id="4455a-127">SRV</span></span>|<span data-ttu-id="4455a-128">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="4455a-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4455a-129">3600</span><span class="sxs-lookup"><span data-stu-id="4455a-129">3600</span></span>|<span data-ttu-id="4455a-130">100 1 5061 sipfed。<span>com</span><span class="sxs-lookup"><span data-stu-id="4455a-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|<span data-ttu-id="4455a-131">フェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="4455a-131">Enables federation</span></span>|
    |<span data-ttu-id="4455a-132">SRV</span><span class="sxs-lookup"><span data-stu-id="4455a-132">SRV</span></span>|<span data-ttu-id="4455a-133">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="4455a-133">_sip._tls</span></span>|<span data-ttu-id="4455a-134">3600</span><span class="sxs-lookup"><span data-stu-id="4455a-134">3600</span></span>|<span data-ttu-id="4455a-135">100 1 443 sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="4455a-135">100 1 443 sipdir.online.lync.<span>com</span></span>|<span data-ttu-id="4455a-136">Skype for Business ユーザーにとって必須</span><span class="sxs-lookup"><span data-stu-id="4455a-136">Required for Skype for Business users</span></span>|
    |<span data-ttu-id="4455a-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="4455a-137">CNAME</span></span>| <span data-ttu-id="4455a-138">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4455a-138">lyncdiscover</span></span>|   <span data-ttu-id="4455a-139">3600</span><span class="sxs-lookup"><span data-stu-id="4455a-139">3600</span></span>|   <span data-ttu-id="4455a-140">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="4455a-140">webdir.online.lync.<span>com</span></span>|<span data-ttu-id="4455a-141">Skype for Business ユーザーにとって必須</span><span class="sxs-lookup"><span data-stu-id="4455a-141">Required for Skype for Business users</span></span>|
    |<span data-ttu-id="4455a-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="4455a-142">CNAME</span></span>| <span data-ttu-id="4455a-143">sip</span><span class="sxs-lookup"><span data-stu-id="4455a-143">sip</span></span>|    <span data-ttu-id="4455a-144">3600</span><span class="sxs-lookup"><span data-stu-id="4455a-144">3600</span></span>|   <span data-ttu-id="4455a-145">sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="4455a-145">sipdir.online.lync.<span>com</span></span>|<span data-ttu-id="4455a-146">以前の従来の SIP 電話にのみ必要</span><span class="sxs-lookup"><span data-stu-id="4455a-146">Required only for older legacy SIP phones</span></span>|

    <span data-ttu-id="4455a-147">また、会議またはダイヤルイン (存在する場合) の CNAME レコードを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4455a-147">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span>

    > [!Note] 
    > <span data-ttu-id="4455a-148">まれなケースとして、組織の 365 DNS を変更することによって、他の組織がフェデレーションの構成を更新するまで、他の組織とのフェデレーションを停止させることがあります。</span><span class="sxs-lookup"><span data-stu-id="4455a-148">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="4455a-149">以前の直接フェデレーションモデル (許可されたパートナーサーバーとも呼ばれる) を使用しているフェデレーション組織は、組織がプロキシ FQDN を削除するために許可されているドメインエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-149">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="4455a-150">この従来のフェデレーションモデルは DNS SRV レコードに基づくものではないため、組織がクラウドに移行すると、このような構成は古くなります。</span><span class="sxs-lookup"><span data-stu-id="4455a-150">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="4455a-151">Sipfed のホスティングプロバイダーが有効になっていないフェデレーション組織。<span>com は、を有効にするために、構成を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-151">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="4455a-152">このような状況は、フェデレーション組織が純粋にオンプレミスにあり、ハイブリッドまたはオンラインのテナントと共にフェデレーションが行われていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="4455a-152">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="4455a-153">このような場合、これらの組織とのフェデレーションは、ホスティングプロバイダーを有効にするまでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4455a-153">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="4455a-154">フェデレーションパートナーのいずれかが直接フェデレーションを使用しているか、またはオンラインまたはハイブリッド組織とフェデレーションされていない可能性がある場合は、クラウドへの移行を完了するための準備として、これに関する連絡をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4455a-154">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="4455a-155">*Office 365 組織の共有 SIP アドレススペースを無効にします。*</span><span class="sxs-lookup"><span data-stu-id="4455a-155">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="4455a-156">次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-156">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="4455a-157">*オンプレミスの Office 365 との通信機能を無効にします。*</span><span class="sxs-lookup"><span data-stu-id="4455a-157">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="4455a-158">次のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-158">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="4455a-159">オンプレミスから移行されたユーザーの sip アドレスと電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="4455a-159">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="4455a-160">管理者は、オンプレミスの展開を使用停止にした後であっても、オンプレミスの Skype for Business Server からクラウドに移動されたユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4455a-160">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="4455a-161">ユーザーの SIP アドレスまたはユーザーの回線 URI を変更する場合 (かつ、オンプレミスの Active Directory で SIP アドレスまたは回線 URI が既に定義されている場合) は、オンプレミスの Active Directory でこれを実行して、その値を Azure AD に流す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4455a-161">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="4455a-162">これには、オンプレミスの Skype for Business Server は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4455a-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="4455a-163">代わりに、これらの属性は、Active Directory ユーザーとコンピューター MMC スナップインを使用するか、PowerShell を使用して、社内の Active Directory で直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="4455a-163">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="4455a-164">MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を検索します。</span><span class="sxs-lookup"><span data-stu-id="4455a-164">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="4455a-165">ユーザーの SIP アドレスを変更するには、 `msRTCSIP-PrimaryUserAddress`を変更します。</span><span class="sxs-lookup"><span data-stu-id="4455a-165">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="4455a-166">さらに、 `ProxyAddresses`属性に sip 値が含まれている場合は、その sip 値を新しい値`msRTCSIP-PrimaryUserAddress`と一致するように更新します。</span><span class="sxs-lookup"><span data-stu-id="4455a-166">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="4455a-167">SIP の値が含まれていない場合は、空白のままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="4455a-167">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="4455a-168">ユーザーの電話番号を変更するには`msRTCSIP-Line` 、*既に値がある場合*に変更します。</span><span class="sxs-lookup"><span data-stu-id="4455a-168">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory ユーザーとコンピューターツール](../media/disable-hybrid-1.png)
  
<span data-ttu-id="4455a-170">移行前に、ユーザーがオンプレミスの`LineURI`値を持っていなかった場合は、Skype For Business Online PowerShell モジュール`onpremLineUri`で-パラメーターを使用して[、-パラメーター](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用して lineuri を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4455a-170">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="4455a-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="4455a-171">See also</span></span>

[<span data-ttu-id="4455a-172">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="4455a-172">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
