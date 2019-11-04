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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams と Skype for Business のクラウド統合の一部としてハイブリッドを無効にするための詳細な手順が含まれています。
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924968"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="15340-103">ハイブリッドを無効にしてクラウドへの移行を完了する</span><span class="sxs-lookup"><span data-stu-id="15340-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="15340-104">オンプレミスのすべてのユーザーをクラウドに移行した後、オンプレミスの Skype for Business の展開を使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="15340-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="15340-105">ハードウェアを削除することに加えて、ハイブリッドを無効にすることによって、オンプレミスの展開を Office 365 から論理的に分離することが重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="15340-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="15340-106">ハイブリッドの無効化は、3つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="15340-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="15340-107">Office 365 をポイントするように DNS レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="15340-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="15340-108">Office 365 テナントの分割ドメインを無効にします。</span><span class="sxs-lookup"><span data-stu-id="15340-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="15340-109">オンプレミスで Office 365 と通信する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="15340-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="15340-110">これらの手順は、1つの単位として一緒に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="15340-111">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15340-111">Details are provided below.</span></span> <span data-ttu-id="15340-112">また、移行したユーザーの電話番号を管理するためのガイドラインについては、オンプレミスの展開が切断された場合です。</span><span class="sxs-lookup"><span data-stu-id="15340-112">In addition, guidelines for managing phone numbers for migrated users, once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="15340-113">まれなケースとして、組織の 365 DNS を変更することによって、他の組織がフェデレーションの構成を更新するまで、他の組織とのフェデレーションを停止させることがあります。</span><span class="sxs-lookup"><span data-stu-id="15340-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="15340-114">以前の直接フェデレーションモデル (許可されたパートナーサーバーとも呼ばれる) を使用しているフェデレーション組織は、組織がプロキシ FQDN を削除するために許可されているドメインエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="15340-115">この従来のフェデレーションモデルは DNS SRV レコードに基づくものではないため、組織がクラウドに移行すると、このような構成は古くなります。</span><span class="sxs-lookup"><span data-stu-id="15340-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="15340-116">Sipfed のホスティングプロバイダーが有効になっていないフェデレーション組織。<span>com は、を有効にするために、構成を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="15340-117">この状況は、フェデレーション組織が純粋にオンプレミスにあり、ハイブリッドまたはオンラインテナントとのフェデレーションが行われていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="15340-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="15340-118">このような場合、これらの組織とのフェデレーションは、ホスティングプロバイダーを有効にするまでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="15340-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="15340-119">フェデレーションパートナーのいずれかが直接フェデレーションを使用しているか、またはすべてのオンラインまたはハイブリッド組織とフェデレーションされている可能性がある場合は、クラウドへの移行を完了するための準備として、これに関する連絡をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15340-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="15340-120">*Office 365 を指すように DNS を更新します。*</span><span class="sxs-lookup"><span data-stu-id="15340-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="15340-121">社内の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミスの展開ではなく Office 365 をポイントできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="15340-122">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15340-122">Specifically:</span></span>

    |<span data-ttu-id="15340-123">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="15340-123">Record type</span></span>|<span data-ttu-id="15340-124">名前</span><span class="sxs-lookup"><span data-stu-id="15340-124">Name</span></span>|<span data-ttu-id="15340-125">TTL</span><span class="sxs-lookup"><span data-stu-id="15340-125">TTL</span></span>|<span data-ttu-id="15340-126">Value</span><span class="sxs-lookup"><span data-stu-id="15340-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="15340-127">SRV</span><span class="sxs-lookup"><span data-stu-id="15340-127">SRV</span></span>|<span data-ttu-id="15340-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="15340-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="15340-129">3600</span><span class="sxs-lookup"><span data-stu-id="15340-129">3600</span></span>|<span data-ttu-id="15340-130">100 1 5061 sipfed。<span>com</span><span class="sxs-lookup"><span data-stu-id="15340-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="15340-131">SRV</span><span class="sxs-lookup"><span data-stu-id="15340-131">SRV</span></span>|<span data-ttu-id="15340-132">(sip) tls</span><span class="sxs-lookup"><span data-stu-id="15340-132">_sip._tls</span></span>|<span data-ttu-id="15340-133">3600</span><span class="sxs-lookup"><span data-stu-id="15340-133">3600</span></span>|<span data-ttu-id="15340-134">100 1 443 sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="15340-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="15340-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="15340-135">CNAME</span></span>| <span data-ttu-id="15340-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="15340-136">lyncdiscover</span></span>|   <span data-ttu-id="15340-137">3600</span><span class="sxs-lookup"><span data-stu-id="15340-137">3600</span></span>|   <span data-ttu-id="15340-138">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="15340-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="15340-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="15340-139">CNAME</span></span>| <span data-ttu-id="15340-140">sip</span><span class="sxs-lookup"><span data-stu-id="15340-140">sip</span></span>|    <span data-ttu-id="15340-141">3600</span><span class="sxs-lookup"><span data-stu-id="15340-141">3600</span></span>|   <span data-ttu-id="15340-142">sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="15340-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="15340-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="15340-143">CNAME</span></span>| <span data-ttu-id="15340-144">満たせ</span><span class="sxs-lookup"><span data-stu-id="15340-144">meet</span></span>|   <span data-ttu-id="15340-145">3600</span><span class="sxs-lookup"><span data-stu-id="15340-145">3600</span></span>|   <span data-ttu-id="15340-146">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="15340-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="15340-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="15340-147">CNAME</span></span>| <span data-ttu-id="15340-148">deny</span><span class="sxs-lookup"><span data-stu-id="15340-148">dialin</span></span>  |<span data-ttu-id="15340-149">3600</span><span class="sxs-lookup"><span data-stu-id="15340-149">3600</span></span>|  <span data-ttu-id="15340-150">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="15340-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="15340-151">*Office 365 テナントの共有 SIP アドレススペースを無効にします。*</span><span class="sxs-lookup"><span data-stu-id="15340-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="15340-152">次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="15340-153">*オンプレミスで Office 365 と通信する機能を無効にします。*</span><span class="sxs-lookup"><span data-stu-id="15340-153">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="15340-154">次のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-154">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="15340-155">以前に Skype for Business Online セッションをインポートしたことがある場合は、新しい Skype for Business PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="15340-155">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="15340-156">オンプレミスから移行されたユーザーの電話番号の管理</span><span class="sxs-lookup"><span data-stu-id="15340-156">Managing phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="15340-157">管理者は、オンプレミスの展開を使用停止にした後であっても、オンプレミスの Skype for Business Server からクラウドに移動されたユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="15340-157">Admins can manage users that were previously moved from on-premise Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="15340-158">2つの異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15340-158">There are 2 different possibilities:</span></span>
1.  <span data-ttu-id="15340-159">ユーザーが、(エンタープライズ Voip を有効にしているため) 移動前に、lineURI をオンプレミスで使用していた場合、lineURI を変更するには、オンプレミスの AD でこれを実行して、価値を AAD に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="15340-159">If the user had a lineURI on-premise before the move (presumably because the user was enabled for Enterprise Voice), if you want to change the lineURI, you must do this in on-premise AD and let the value flow up to AAD.</span></span> <span data-ttu-id="15340-160">これには、オンプレミスの Skype for Business Server は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="15340-160">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="15340-161">代わりに、この属性は、Active Directory ユーザーとコンピューター MMC スナップインを使用するか、PowerShell を使用して、社内の Active Directory で直接編集できます。</span><span class="sxs-lookup"><span data-stu-id="15340-161">Rather, this attribute, msRTCSIP-Line can be edited directly in the on-premises Active Directory, using either Active Directory Users and Computers MMC snap-in, or via PowerShell.</span></span> <span data-ttu-id="15340-162">MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開いて、[属性エディター] タブをクリックし、msRTCSIP 行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="15340-162">If using the MMC snap-in, open to properties page of the user, and click Attribute Editor tab and find msRTCSIP-Line.</span></span>

2.  <span data-ttu-id="15340-163">ユーザーが移動前の lineURI の値を持っていなかった場合、Skype for Business Online Powershell モジュールの-onpremLineUri パラメーターを使用して、LineURI を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="15340-163">If the user did not have a value for lineURI on-prem before the move, you can modify the LineURI using the -onpremLineUri parameters in the set-csuser cmdlet in the Skype for Business Online Powershell module.</span></span>

## <a name="see-also"></a><span data-ttu-id="15340-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="15340-164">See also</span></span>

[<span data-ttu-id="15340-165">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="15340-165">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
