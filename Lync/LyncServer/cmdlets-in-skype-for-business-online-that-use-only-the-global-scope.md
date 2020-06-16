---
title: グローバルスコープのみを使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755099"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>グローバルスコープのみを使用する Skype for Business Online のコマンドレット

 


いくつかの Skype for Business Online の設定は、*グローバルスコープ*でのみ利用できます。 これは、そのテナントに割り当てられているすべてのユーザーに適用される設定の単一のコレクションが存在することを意味します。 (各テナントには、グローバル設定の固有のコレクションがあります)。グローバルスコープに制限されているコマンドレットを使用している場合、Identity パラメーターは省略可能です。 たとえば、会議の構成設定を取得するには、次のコマンドを使用します。

    Get-CsMeetingConfiguration -Identity "global"

または、Identity パラメーターを省略して、代わりに次の簡単なコマンドを使用することもできます。

    Get-CsMeetingConfiguration

会議構成設定のグローバルコレクションは1つだけなので、2つのコマンドはまったく同じ情報を返します。 また、Identity パラメーターは、いずれか**のコマンドレット**を使用する場合には省略できます。 これらの2つのコマンドは同じです。

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Identity パラメーターが指定されていない場合、既定では、Windows PowerShell によってグローバルコレクションが変更されるため、2つのコマンドは同じです。

次のコマンドレットは、グローバルスコープでのみ動作します。

  - [Get-Cシム Filterconfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [-Cs会議構成の取得](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [設定-Cs会議構成](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

**Set-csvoicepolicy**コマンドレットは異常なものであることに注意してください。 最初に、このコマンドレットには Identity パラメーターを含める必要があります。

    Remove-CsVoicePolicy -Identity "global"

2番目に、 **set-csvoicepolicy**コマンドレットでは、グローバル音声ポリシーが実際に削除されることはありません。Skype for Business Online では、グローバルポリシーや構成設定を削除することはできません。 このコマンドレットを実行すると、グローバル音声ポリシーのすべてのプロパティを既定値にリセットすることができます。 たとえば、既定では、AllowCallForwarding プロパティは False に設定されています。 ただし、AllowCallForwarding が変更されていて、値が True に設定されている可能性があります。 **Set-csvoicepolicy**コマンドレットを実行すると、AllowCallForwarding プロパティは既定値の "False" に戻ります。 次の表に、このシナリオの概要を示します。


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
<td><p><strong>Set-csvoicepolicy</strong>コマンドレットが実行された後</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

