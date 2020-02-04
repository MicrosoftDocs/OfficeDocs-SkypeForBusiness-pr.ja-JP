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
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728107"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="e704f-102">グローバルスコープのみを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e704f-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="e704f-103">Skype for Business Online の設定の多くは、*グローバル範囲*でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="e704f-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="e704f-104">これは、そのテナントに割り当てられているすべてのユーザーに適用される設定のコレクションが1つだけであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e704f-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="e704f-105">(各テナントにはグローバル設定の固有のコレクションがあります)。グローバルスコープに制限されているコマンドレットを使用している場合、Identity パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e704f-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="e704f-106">たとえば、会議の構成設定を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e704f-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="e704f-107">または、Identity パラメーターを省略して、代わりに次のような単純なコマンドを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e704f-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="e704f-108">会議構成設定のグローバルコレクションは1つしかないため、2つのコマンドはまったく同じ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e704f-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="e704f-109">Identity パラメーターは、いずれかの**Set-Cs**コマンドレットを使っているときに省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="e704f-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="e704f-110">次の2つのコマンドは同じです。</span><span class="sxs-lookup"><span data-stu-id="e704f-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="e704f-111">2つのコマンドは、Id パラメーターが含まれていない場合、既定では Windows PowerShell によってグローバルコレクションが変更されるため、同じです。</span><span class="sxs-lookup"><span data-stu-id="e704f-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="e704f-112">次のコマンドレットはグローバルスコープでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="e704f-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="e704f-113">[取得-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e704f-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="e704f-123">**CsVoicePolicy**コマンドレットは異常であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e704f-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="e704f-124">まず、このコマンドレットには Id パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e704f-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="e704f-125">次に、 **CsVoicePolicy**コマンドレットでは、グローバルボイスポリシーは実際には削除されません。Skype for Business Online では、グローバルポリシーや構成設定を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e704f-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="e704f-126">コマンドレットでは、グローバルボイスポリシーのすべてのプロパティを既定値にリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="e704f-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="e704f-127">たとえば、既定では、AllowCallForwarding プロパティは False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e704f-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="e704f-128">ただし、AllowCallForwarding が変更された可能性があります。この値は True に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e704f-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="e704f-129">**CsVoicePolicy**コマンドレットを実行すると、AllowCallForwarding プロパティは既定値の "False" に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e704f-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="e704f-130">次の表は、このシナリオをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e704f-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e704f-131">AllowCallForwarding 値</span><span class="sxs-lookup"><span data-stu-id="e704f-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="e704f-132">シナリオ</span><span class="sxs-lookup"><span data-stu-id="e704f-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e704f-133">False</span><span class="sxs-lookup"><span data-stu-id="e704f-133">False</span></span></p></td>
<td><p><span data-ttu-id="e704f-134">既定値</span><span class="sxs-lookup"><span data-stu-id="e704f-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e704f-135">True</span><span class="sxs-lookup"><span data-stu-id="e704f-135">True</span></span></p></td>
<td><p><span data-ttu-id="e704f-136">グローバルポリシーが変更された後</span><span class="sxs-lookup"><span data-stu-id="e704f-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e704f-137">False</span><span class="sxs-lookup"><span data-stu-id="e704f-137">False</span></span></p></td>
<td><p><span data-ttu-id="e704f-138"><strong>CsVoicePolicy</strong>コマンドレットが実行された後</span><span class="sxs-lookup"><span data-stu-id="e704f-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="e704f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e704f-139">See Also</span></span>


[<span data-ttu-id="e704f-140">Skype for Business Online の id、スコープ、テナント</span><span class="sxs-lookup"><span data-stu-id="e704f-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e704f-141">[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e704f-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

