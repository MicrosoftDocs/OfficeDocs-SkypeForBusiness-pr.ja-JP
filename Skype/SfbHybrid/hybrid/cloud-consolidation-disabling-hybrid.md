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
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160652"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="08e9c-103">ハイブリッドを無効にしてクラウドへの移行を完了する</span><span class="sxs-lookup"><span data-stu-id="08e9c-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="08e9c-104">オンプレミスのすべてのユーザーをクラウドに移行した後、オンプレミスの Skype for Business の展開を使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="08e9c-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="08e9c-105">ハードウェアを削除することに加えて、ハイブリッドを無効にすることによって、オンプレミスの展開を Office 365 から論理的に分離することが重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="08e9c-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="08e9c-106">ハイブリッドの無効化は、3つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="08e9c-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="08e9c-107">Office 365 をポイントするように DNS レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="08e9c-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="08e9c-108">Office 365 テナントの分割ドメインを無効にします。</span><span class="sxs-lookup"><span data-stu-id="08e9c-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="08e9c-109">オンプレミスで Office 365 と通信する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="08e9c-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="08e9c-110">これらの手順は、1つの単位として一緒に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="08e9c-111">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e9c-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="08e9c-112">まれなケースとして、組織の 365 DNS を変更することによって、他の組織がフェデレーションの構成を更新するまで、他の組織とのフェデレーションを停止させることがあります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="08e9c-113">以前の直接フェデレーションモデル (許可されたパートナーサーバーとも呼ばれる) を使用しているフェデレーション組織は、組織がプロキシ FQDN を削除するために許可されているドメインエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="08e9c-114">この従来のフェデレーションモデルは DNS SRV レコードに基づくものではないため、組織がクラウドに移行すると、このような構成は古くなります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="08e9c-115">Sipfed のホスティングプロバイダーが有効になっていないフェデレーション組織。<span>com は、を有効にするために、構成を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="08e9c-116">この状況は、フェデレーション組織が純粋にオンプレミスにあり、ハイブリッドまたはオンラインテナントとのフェデレーションが行われていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="08e9c-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="08e9c-117">このような場合、これらの組織とのフェデレーションは、ホスティングプロバイダーを有効にするまでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="08e9c-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="08e9c-118">フェデレーションパートナーのいずれかが直接フェデレーションを使用しているか、またはすべてのオンラインまたはハイブリッド組織とフェデレーションされている可能性がある場合は、クラウドへの移行を完了するための準備として、これに関する連絡をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08e9c-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="08e9c-119">*Office 365 を指すように DNS を更新します。*</span><span class="sxs-lookup"><span data-stu-id="08e9c-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="08e9c-120">社内の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミスの展開ではなく Office 365 をポイントできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="08e9c-121">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="08e9c-121">Specifically:</span></span>

    |<span data-ttu-id="08e9c-122">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="08e9c-122">Record type</span></span>|<span data-ttu-id="08e9c-123">名前</span><span class="sxs-lookup"><span data-stu-id="08e9c-123">Name</span></span>|<span data-ttu-id="08e9c-124">TTL</span><span class="sxs-lookup"><span data-stu-id="08e9c-124">TTL</span></span>|<span data-ttu-id="08e9c-125">Value</span><span class="sxs-lookup"><span data-stu-id="08e9c-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="08e9c-126">SRV</span><span class="sxs-lookup"><span data-stu-id="08e9c-126">SRV</span></span>|<span data-ttu-id="08e9c-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="08e9c-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="08e9c-128">3600</span><span class="sxs-lookup"><span data-stu-id="08e9c-128">3600</span></span>|<span data-ttu-id="08e9c-129">100 1 5061 sipfed。<span>com</span><span class="sxs-lookup"><span data-stu-id="08e9c-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="08e9c-130">SRV</span><span class="sxs-lookup"><span data-stu-id="08e9c-130">SRV</span></span>|<span data-ttu-id="08e9c-131">(sip) tls</span><span class="sxs-lookup"><span data-stu-id="08e9c-131">_sip._tls</span></span>|<span data-ttu-id="08e9c-132">3600</span><span class="sxs-lookup"><span data-stu-id="08e9c-132">3600</span></span>|<span data-ttu-id="08e9c-133">100 1 443 sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="08e9c-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="08e9c-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="08e9c-134">CNAME</span></span>| <span data-ttu-id="08e9c-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="08e9c-135">lyncdiscover</span></span>|   <span data-ttu-id="08e9c-136">3600</span><span class="sxs-lookup"><span data-stu-id="08e9c-136">3600</span></span>|   <span data-ttu-id="08e9c-137">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="08e9c-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="08e9c-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="08e9c-138">CNAME</span></span>| <span data-ttu-id="08e9c-139">sip</span><span class="sxs-lookup"><span data-stu-id="08e9c-139">sip</span></span>|    <span data-ttu-id="08e9c-140">3600</span><span class="sxs-lookup"><span data-stu-id="08e9c-140">3600</span></span>|   <span data-ttu-id="08e9c-141">sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="08e9c-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="08e9c-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="08e9c-142">CNAME</span></span>| <span data-ttu-id="08e9c-143">満たせ</span><span class="sxs-lookup"><span data-stu-id="08e9c-143">meet</span></span>|   <span data-ttu-id="08e9c-144">3600</span><span class="sxs-lookup"><span data-stu-id="08e9c-144">3600</span></span>|   <span data-ttu-id="08e9c-145">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="08e9c-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="08e9c-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="08e9c-146">CNAME</span></span>| <span data-ttu-id="08e9c-147">deny</span><span class="sxs-lookup"><span data-stu-id="08e9c-147">dialin</span></span>  |<span data-ttu-id="08e9c-148">3600</span><span class="sxs-lookup"><span data-stu-id="08e9c-148">3600</span></span>|  <span data-ttu-id="08e9c-149">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="08e9c-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="08e9c-150">*Office 365 テナントの共有 SIP アドレススペースを無効にします。*</span><span class="sxs-lookup"><span data-stu-id="08e9c-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="08e9c-151">次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="08e9c-152">*オンプレミスで Office 365 と通信する機能を無効にします。*</span><span class="sxs-lookup"><span data-stu-id="08e9c-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="08e9c-153">次のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9c-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="08e9c-154">以前に Skype for Business Online セッションをインポートしたことがある場合は、新しい Skype for Business PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="08e9c-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="08e9c-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="08e9c-155">See also</span></span>

[<span data-ttu-id="08e9c-156">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="08e9c-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)