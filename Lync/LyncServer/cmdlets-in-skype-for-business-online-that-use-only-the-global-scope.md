---
title: グローバルスコープのみを使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4a894c4a9c6e2913abb003c49094bc6d6868483
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001252"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="8ce47-102">グローバルスコープのみを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="8ce47-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="8ce47-103">いくつかの Skype for Business Online の設定は、*グローバルスコープ*でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ce47-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="8ce47-104">これは、そのテナントに割り当てられているすべてのユーザーに適用される設定の単一のコレクションが存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8ce47-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="8ce47-105">(各テナントには、グローバル設定の固有のコレクションがあります)。グローバルスコープに制限されているコマンドレットを使用している場合、Identity パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8ce47-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="8ce47-106">たとえば、会議の構成設定を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ce47-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="8ce47-107">または、Identity パラメーターを省略して、代わりに次の簡単なコマンドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ce47-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="8ce47-108">会議構成設定のグローバルコレクションは1つだけなので、2つのコマンドはまったく同じ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8ce47-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="8ce47-109">また、Identity パラメーターは、いずれか**のコマンドレット**を使用する場合には省略できます。</span><span class="sxs-lookup"><span data-stu-id="8ce47-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="8ce47-110">これらの2つのコマンドは同じです。</span><span class="sxs-lookup"><span data-stu-id="8ce47-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="8ce47-111">Identity パラメーターが指定されていない場合、既定では、Windows PowerShell によってグローバルコレクションが変更されるため、2つのコマンドは同じです。</span><span class="sxs-lookup"><span data-stu-id="8ce47-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="8ce47-112">次のコマンドレットは、グローバルスコープでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="8ce47-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="8ce47-113">[Get-Cシム Filterconfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-114">[-Cs会議構成の取得](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-115">[Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-116">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-117">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-118">[Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-119">[CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-120">[Set-csvoicepolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-121">[設定-Cs会議構成](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8ce47-122">[Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="8ce47-123">**Set-csvoicepolicy**コマンドレットは異常なものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ce47-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="8ce47-124">最初に、このコマンドレットには Identity パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ce47-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="8ce47-125">2番目に、 **set-csvoicepolicy**コマンドレットでは、グローバル音声ポリシーが実際に削除されることはありません。Skype for Business Online では、グローバルポリシーや構成設定を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ce47-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="8ce47-126">このコマンドレットを実行すると、グローバル音声ポリシーのすべてのプロパティを既定値にリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ce47-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="8ce47-127">たとえば、既定では、AllowCallForwarding プロパティは False に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8ce47-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="8ce47-128">ただし、AllowCallForwarding が変更されていて、値が True に設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ce47-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="8ce47-129">**Set-csvoicepolicy**コマンドレットを実行すると、AllowCallForwarding プロパティは既定値の "False" に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8ce47-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="8ce47-130">次の表に、このシナリオの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="8ce47-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ce47-131">AllowCallForwarding 値</span><span class="sxs-lookup"><span data-stu-id="8ce47-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="8ce47-132">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8ce47-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ce47-133">False</span><span class="sxs-lookup"><span data-stu-id="8ce47-133">False</span></span></p></td>
<td><p><span data-ttu-id="8ce47-134">既定値</span><span class="sxs-lookup"><span data-stu-id="8ce47-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ce47-135">はい</span><span class="sxs-lookup"><span data-stu-id="8ce47-135">True</span></span></p></td>
<td><p><span data-ttu-id="8ce47-136">グローバルポリシーが変更された後</span><span class="sxs-lookup"><span data-stu-id="8ce47-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ce47-137">False</span><span class="sxs-lookup"><span data-stu-id="8ce47-137">False</span></span></p></td>
<td><p><span data-ttu-id="8ce47-138"><strong>Set-csvoicepolicy</strong>コマンドレットが実行された後</span><span class="sxs-lookup"><span data-stu-id="8ce47-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="8ce47-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ce47-139">See Also</span></span>


[<span data-ttu-id="8ce47-140">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="8ce47-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8ce47-141">[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ce47-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

