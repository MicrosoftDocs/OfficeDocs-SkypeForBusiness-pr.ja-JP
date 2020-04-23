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
ms.openlocfilehash: 053d632b5a07b7ce7cca8ef7a1ddf45a673bcf59
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780146"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="f722f-103">ハイブリッドを無効にしてクラウドへの移行を完了する</span><span class="sxs-lookup"><span data-stu-id="f722f-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="f722f-104">すべてのユーザーをオンプレミスからクラウドに移行した後は、オンプレミスの Skype for Business の配置を使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f722f-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="f722f-105">ハードウェアを削除する以外に、重要なステップとして、ハイブリッドを無効にすることによってオンプレミスの配置を Office 365 から論理的に分離します。</span><span class="sxs-lookup"><span data-stu-id="f722f-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="f722f-106">ハイブリッドの無効化は、3つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f722f-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="f722f-107">Office 365 を指すようにドメインの DNS レコードを更新する。</span><span class="sxs-lookup"><span data-stu-id="f722f-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="f722f-108">Office 365 組織の分割ドメインを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f722f-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="f722f-109">オンプレミスの Office 365 との通信機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f722f-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="f722f-110">これらの手順は、1つの単位として一緒に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="f722f-111">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f722f-111">Details are provided below.</span></span> <span data-ttu-id="f722f-112">また、オンプレミスの展開が切断されると、移行されたユーザーの電話番号を管理するためのガイドラインが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f722f-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="f722f-113">まれなケースとして、組織の 365 DNS を変更することによって、他の組織がフェデレーションの構成を更新するまで、他の組織とのフェデレーションを停止させることがあります。</span><span class="sxs-lookup"><span data-stu-id="f722f-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="f722f-114">以前の直接フェデレーションモデル (許可されたパートナーサーバーとも呼ばれる) を使用しているフェデレーション組織は、組織がプロキシ FQDN を削除するために許可されているドメインエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="f722f-115">この従来のフェデレーションモデルは DNS SRV レコードに基づくものではないため、組織がクラウドに移行すると、このような構成は古くなります。</span><span class="sxs-lookup"><span data-stu-id="f722f-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="f722f-116">Sipfed のホスティングプロバイダーが有効になっていないフェデレーション組織。<span>com は、を有効にするために、構成を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="f722f-117">この状況は、フェデレーション組織が純粋にオンプレミスにあり、ハイブリッドまたはオンラインテナントとのフェデレーションが行われていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="f722f-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="f722f-118">このような場合、これらの組織とのフェデレーションは、ホスティングプロバイダーを有効にするまでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="f722f-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="f722f-119">フェデレーションパートナーのいずれかが直接フェデレーションを使用しているか、またはすべてのオンラインまたはハイブリッド組織とフェデレーションされている可能性がある場合は、クラウドへの移行を完了するための準備として、これに関する連絡をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f722f-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="f722f-120">*Office 365 を指すように DNS を更新します。*</span><span class="sxs-lookup"><span data-stu-id="f722f-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="f722f-121">社内の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミスの展開ではなく Office 365 をポイントできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="f722f-122">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f722f-122">Specifically:</span></span>

    |<span data-ttu-id="f722f-123">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="f722f-123">Record type</span></span>|<span data-ttu-id="f722f-124">名前</span><span class="sxs-lookup"><span data-stu-id="f722f-124">Name</span></span>|<span data-ttu-id="f722f-125">TTL</span><span class="sxs-lookup"><span data-stu-id="f722f-125">TTL</span></span>|<span data-ttu-id="f722f-126">Value</span><span class="sxs-lookup"><span data-stu-id="f722f-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="f722f-127">SRV</span><span class="sxs-lookup"><span data-stu-id="f722f-127">SRV</span></span>|<span data-ttu-id="f722f-128">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="f722f-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="f722f-129">3600</span><span class="sxs-lookup"><span data-stu-id="f722f-129">3600</span></span>|<span data-ttu-id="f722f-130">100 1 5061 sipfed。<span>com</span><span class="sxs-lookup"><span data-stu-id="f722f-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="f722f-131">SRV</span><span class="sxs-lookup"><span data-stu-id="f722f-131">SRV</span></span>|<span data-ttu-id="f722f-132">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="f722f-132">_sip._tls</span></span>|<span data-ttu-id="f722f-133">3600</span><span class="sxs-lookup"><span data-stu-id="f722f-133">3600</span></span>|<span data-ttu-id="f722f-134">100 1 443 sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="f722f-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="f722f-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="f722f-135">CNAME</span></span>| <span data-ttu-id="f722f-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f722f-136">lyncdiscover</span></span>|   <span data-ttu-id="f722f-137">3600</span><span class="sxs-lookup"><span data-stu-id="f722f-137">3600</span></span>|   <span data-ttu-id="f722f-138">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="f722f-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="f722f-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="f722f-139">CNAME</span></span>| <span data-ttu-id="f722f-140">sip</span><span class="sxs-lookup"><span data-stu-id="f722f-140">sip</span></span>|    <span data-ttu-id="f722f-141">3600</span><span class="sxs-lookup"><span data-stu-id="f722f-141">3600</span></span>|   <span data-ttu-id="f722f-142">sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="f722f-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="f722f-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="f722f-143">CNAME</span></span>| <span data-ttu-id="f722f-144">満たせ</span><span class="sxs-lookup"><span data-stu-id="f722f-144">meet</span></span>|   <span data-ttu-id="f722f-145">3600</span><span class="sxs-lookup"><span data-stu-id="f722f-145">3600</span></span>|   <span data-ttu-id="f722f-146">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="f722f-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="f722f-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="f722f-147">CNAME</span></span>| <span data-ttu-id="f722f-148">deny</span><span class="sxs-lookup"><span data-stu-id="f722f-148">dialin</span></span>  |<span data-ttu-id="f722f-149">3600</span><span class="sxs-lookup"><span data-stu-id="f722f-149">3600</span></span>|  <span data-ttu-id="f722f-150">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="f722f-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="f722f-151">*Office 365 組織の共有 SIP アドレススペースを無効にします。*</span><span class="sxs-lookup"><span data-stu-id="f722f-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="f722f-152">次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="f722f-153">*オンプレミスの Office 365 との通信機能を無効にします。*</span><span class="sxs-lookup"><span data-stu-id="f722f-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="f722f-154">次のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="f722f-155">オンプレミスから移行されたユーザーの電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="f722f-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="f722f-156">管理者は、オンプレミスの展開を使用停止にした後であっても、オンプレミスの Skype for Business Server からクラウドに移動されたユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f722f-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="f722f-157">2つの異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-157">There are two different possibilities:</span></span>

- <span data-ttu-id="f722f-158">ユーザーは、移動前に、オンプレミスの LineURI の値を持っていませんでした。</span><span class="sxs-lookup"><span data-stu-id="f722f-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="f722f-159">この場合は、Skype for Business Online PowerShell[モジュールの-](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) onpremLineUri パラメーターを使用して、lineuri を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f722f-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="f722f-160">ユーザーは、移動前に、オンプレミスの LineURI を使用しました (ユーザーがエンタープライズ Voip を有効にしているため)。</span><span class="sxs-lookup"><span data-stu-id="f722f-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="f722f-161">LineURI を変更する場合は、オンプレミスの Active Directory でこれを実行し、その値が Azure AD に流れるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f722f-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="f722f-162">これには、オンプレミスの Skype for Business Server は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f722f-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="f722f-163">代わりに、この属性 msRTCSIP は、Active Directory ユーザーとコンピューター MMC スナップインを使用するか、PowerShell を使用して、オンプレミスの Active Directory で直接編集することができます。</span><span class="sxs-lookup"><span data-stu-id="f722f-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="f722f-164">MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、msRTCSIP 行を検索します。</span><span class="sxs-lookup"><span data-stu-id="f722f-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Active Directory ユーザーとコンピューターツール](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="f722f-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="f722f-166">See also</span></span>

[<span data-ttu-id="f722f-167">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="f722f-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
