---
title: ハイブリッド クラウドへの移行を完了するを無効にします。
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、チームおよびビジネス用の Skype のためのクラウドの統合の一部としてハイブリッドを無効にする詳細な手順が含まれています。
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247690"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="7bf30-103">ハイブリッド クラウドへの移行を完了するを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7bf30-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="7bf30-104">オンプレミスからクラウドに移行するすべてのユーザーを移動した後は、ビジネスの展開の設置型の Skype を解除できます。</span><span class="sxs-lookup"><span data-stu-id="7bf30-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="7bf30-105">以外のハードウェアを削除するには、重要なステップは、ハイブリッドを無効にしてから Office 365 には、その設置型展開を論理的に分離。</span><span class="sxs-lookup"><span data-stu-id="7bf30-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="7bf30-106">ハイブリッドを無効にするには、3 つのステップで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7bf30-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="7bf30-107">Office 365 をポイントする DNS レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="7bf30-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="7bf30-108">Office 365 テナント ドメイン分割を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7bf30-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="7bf30-109">Prem 上での機能は、Office 365 との通信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7bf30-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="7bf30-110">次の手順は、単位としてまとめて行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf30-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="7bf30-111">詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="7bf30-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="7bf30-112">まれに、組織の Office 365 に施設内のポイントから DNS を変更する場合があります連合その他の組織が、フェデレーションの構成を更新するまで動作を停止するのにはいくつか他の組織。</span><span class="sxs-lookup"><span data-stu-id="7bf30-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="7bf30-113">古いの直接フェデレーション モデル (とも呼ばれる許可されたパートナー サーバー) を使用しているフェデレーションの組織は、プロキシの FQDN を削除するのには、組織に対して、許可されているドメインのエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf30-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="7bf30-114">この従来のフェデレーション モデルに基づかない DNS SRV レコードでは、組織がクラウドへの移動後に、このような構成が古くなったためです。</span><span class="sxs-lookup"><span data-stu-id="7bf30-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="7bf30-115">Sipfed.online.lync を有効になっているホスティング プロバイダーがない連合組織です。<span>com を有効にするのには、その構成を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf30-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="7bf30-116">このような状況を可能なは、フェデレーション組織設置型には、ハイブリッドまたはオンラインのテナントと連合がない場合だけです。</span><span class="sxs-lookup"><span data-stu-id="7bf30-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="7bf30-117">このような場合は、そのホスティング プロバイダーを有効にするまでこれらの組織とのフェデレーションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7bf30-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="7bf30-118">疑われる場合は、直接フェデレーションを使用して、フェデレーション パートナーのいずれか、またはオンラインのいずれかのフェデレーションがハイブリッド組織では、私たちを提案することを送信する通信について、クラウドへの移行を完了する前にします。</span><span class="sxs-lookup"><span data-stu-id="7bf30-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="7bf30-119">*Office 365 を指すように DNS を更新します。*</span><span class="sxs-lookup"><span data-stu-id="7bf30-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="7bf30-120">設置組織の組織の外部の DNS では、ビジネス記録の Skype は設置型展開ではなく Office 365 をポイントするように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf30-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="7bf30-121">具体的には：</span><span class="sxs-lookup"><span data-stu-id="7bf30-121">Specifically:</span></span>

    |<span data-ttu-id="7bf30-122">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="7bf30-122">Record type</span></span>|<span data-ttu-id="7bf30-123">名前</span><span class="sxs-lookup"><span data-stu-id="7bf30-123">Name</span></span>|<span data-ttu-id="7bf30-124">TTL</span><span class="sxs-lookup"><span data-stu-id="7bf30-124">TTL</span></span>|<span data-ttu-id="7bf30-125">値</span><span class="sxs-lookup"><span data-stu-id="7bf30-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="7bf30-126">SRV</span><span class="sxs-lookup"><span data-stu-id="7bf30-126">SRV</span></span>|<span data-ttu-id="7bf30-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7bf30-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7bf30-128">3600</span><span class="sxs-lookup"><span data-stu-id="7bf30-128">3600</span></span>|<span data-ttu-id="7bf30-129">100 1 5061 sipfed.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="7bf30-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7bf30-130">SRV</span><span class="sxs-lookup"><span data-stu-id="7bf30-130">SRV</span></span>|<span data-ttu-id="7bf30-131">ゾーンに追加</span><span class="sxs-lookup"><span data-stu-id="7bf30-131">_sip._tls</span></span>|<span data-ttu-id="7bf30-132">3600</span><span class="sxs-lookup"><span data-stu-id="7bf30-132">3600</span></span>|<span data-ttu-id="7bf30-133">100 1 443 sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="7bf30-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7bf30-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bf30-134">CNAME</span></span>| <span data-ttu-id="7bf30-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7bf30-135">lyncdiscover</span></span>|   <span data-ttu-id="7bf30-136">3600</span><span class="sxs-lookup"><span data-stu-id="7bf30-136">3600</span></span>|   <span data-ttu-id="7bf30-137">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="7bf30-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7bf30-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bf30-138">CNAME</span></span>| <span data-ttu-id="7bf30-139">sip</span><span class="sxs-lookup"><span data-stu-id="7bf30-139">sip</span></span>|    <span data-ttu-id="7bf30-140">3600</span><span class="sxs-lookup"><span data-stu-id="7bf30-140">3600</span></span>|   <span data-ttu-id="7bf30-141">sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="7bf30-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7bf30-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bf30-142">CNAME</span></span>| <span data-ttu-id="7bf30-143">対応</span><span class="sxs-lookup"><span data-stu-id="7bf30-143">meet</span></span>|   <span data-ttu-id="7bf30-144">3600</span><span class="sxs-lookup"><span data-stu-id="7bf30-144">3600</span></span>|   <span data-ttu-id="7bf30-145">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="7bf30-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7bf30-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bf30-146">CNAME</span></span>| <span data-ttu-id="7bf30-147">ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="7bf30-147">dialin</span></span>  |<span data-ttu-id="7bf30-148">3600</span><span class="sxs-lookup"><span data-stu-id="7bf30-148">3600</span></span>|  <span data-ttu-id="7bf30-149">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="7bf30-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="7bf30-150">*Office 365 のテナントでの SIP アドレス空間の共有を無効にします。*</span><span class="sxs-lookup"><span data-stu-id="7bf30-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="7bf30-151">次のコマンドは、Skype のビジネス オンライン PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf30-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="7bf30-152">*Prem 上での機能は、Office 365 との通信を無効にします。*</span><span class="sxs-lookup"><span data-stu-id="7bf30-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="7bf30-153">次のコマンドでは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf30-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="7bf30-154">ビジネスのオンライン セッションの以前の Skype をインポートした場合は、ビジネスの PowerShell セッションで新しい Skype を起動します。</span><span class="sxs-lookup"><span data-stu-id="7bf30-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="7bf30-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bf30-155">See also</span></span>

[<span data-ttu-id="7bf30-156">チームと Skype のビジネス向けのクラウド統合</span><span class="sxs-lookup"><span data-stu-id="7bf30-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)