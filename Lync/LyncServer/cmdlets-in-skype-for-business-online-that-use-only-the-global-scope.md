---
title: グローバル スコープのみを使用するコマンドレット
TOCTitle: グローバル スコープのみを使用するコマンドレット
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56270052
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グローバル スコープのみを使用するコマンドレット

 

_**トピックの最終更新日:** 2015-06-22_

Skype for Business Online の設定の多くは、グローバル スコープのみで使用できます。これは、そのテナントに割り当てられているすべてのユーザーに適用される設定のコレクションは 1 つだけであることを意味します (各テナントには、グローバル設定の独自のコレクションがあります)。グローバル スコープに限定されているコマンドレットを使用している場合、Identity パラメーターは省略可能です。たとえば、会議構成設定を取得するには、次のコマンドを使用する方法があります。

    Get-CsMeetingConfiguration -Identity "global"

または、Identity パラメーターを省略して、代わりに次のよりシンプルなコマンドを使用できます。

    Get-CsMeetingConfiguration

会議構成設定のグローバル コレクションは 1 つだけであるため、上記の 2 つのコマンドはまったく同じ情報を返します。いずれかの **Set-Cs** コマンドレットを使用する場合は、Identity パラメーターを省略することもできます。次の 2 つのコマンドは同じです。

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

上記の 2 つのコマンドが同じであるのは、既定では、Identity パラメーターを含めない場合に Windows PowerShell ではグローバル コレクションを変更するためです。

次のコマンドレットは、グローバル スコープのみで動作します。

  - [Get-CsImFilterConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsImFilterConfiguration)

  - [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration)

  - [Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

  - [Get-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantPublicProvider)

  - [Remove-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsVoicePolicy)

  - [Set-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingConfiguration)

  - [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

**Remove-CsVoicePolicy** コマンドレットは通常のコマンドレットと多少異なることに注意してください。まず、このコマンドレットには Identity パラメーターを含める必要がありません。

    Remove-CsVoicePolicy -Identity "global"

第 2 に、**Remove-CsVoicePolicy** コマンドレットは、実際にはグローバル音声ポリシーを削除しません。Skype for Business Online では、グローバル ポリシーまたは構成設定を削除できません。コマンドレットが実行する内容は、グローバル音声ポリシーのすべてのプロパティを既定値にリセットできるようにすることです。たとえば、既定では AllowCallForwarding プロパティは False に設定されていますが、AllowCallForwarding は変更されていて現在の値は True に設定されている可能性があります。**Remove-CsVoicePolicy** コマンドレットを実行すると、AllowCallForwarding プロパティは既定値の False に戻ります。次の表に、このシナリオの概要を示します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding の値</th>
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
<td><p>グローバル ポリシーの変更後</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p><strong>Remove-CsVoicePolicy</strong> コマンドレットの実行後</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[ID、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

