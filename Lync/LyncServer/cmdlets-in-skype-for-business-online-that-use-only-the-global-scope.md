---
title: グローバルスコープのみを使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af9bb88fc4dbe3b7814d1f2f69d711527a769a3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840099"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>グローバルスコープのみを使用する Skype for Business Online のコマンドレット

 


Skype for Business Online の設定の多くは、*グローバル範囲*でのみ利用できます。 これは、そのテナントに割り当てられているすべてのユーザーに適用される設定のコレクションが1つだけであることを意味します。 (各テナントにはグローバル設定の固有のコレクションがあります)。グローバルスコープに制限されているコマンドレットを使用している場合、Identity パラメーターは省略可能です。 たとえば、会議の構成設定を取得するには、次のコマンドを使用します。

    Get-CsMeetingConfiguration -Identity "global"

または、Identity パラメーターを省略して、代わりに次のような単純なコマンドを使うこともできます。

    Get-CsMeetingConfiguration

会議構成設定のグローバルコレクションは1つしかないため、2つのコマンドはまったく同じ情報を返します。 Identity パラメーターは、いずれかの**Set-Cs**コマンドレットを使っているときに省略することもできます。 次の2つのコマンドは同じです。

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

2つのコマンドは、Id パラメーターが含まれていない場合、既定では Windows PowerShell によってグローバルコレクションが変更されるため、同じです。

次のコマンドレットはグローバルスコープでのみ動作します。

  - [取得-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

**CsVoicePolicy**コマンドレットは異常であることに注意してください。 まず、このコマンドレットには Id パラメーターを含める必要があります。

    Remove-CsVoicePolicy -Identity "global"

次に、 **CsVoicePolicy**コマンドレットでは、グローバルボイスポリシーは実際には削除されません。Skype for Business Online では、グローバルポリシーや構成設定を削除することはできません。 コマンドレットでは、グローバルボイスポリシーのすべてのプロパティを既定値にリセットすることができます。 たとえば、既定では、AllowCallForwarding プロパティは False に設定されます。 ただし、AllowCallForwarding が変更された可能性があります。この値は True に設定されています。 **CsVoicePolicy**コマンドレットを実行すると、AllowCallForwarding プロパティは既定値の "False" に戻ります。 次の表は、このシナリオをまとめたものです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 値</th>
<th>シナリオ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>既定値</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>グローバルポリシーが変更された後</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p><strong>CsVoicePolicy</strong>コマンドレットが実行された後</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

