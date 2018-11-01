---
title: 会議プロバイダー ID を使用するコマンドレット
TOCTitle: 会議プロバイダー ID を使用するコマンドレット
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56270142
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議プロバイダー ID を使用するコマンドレット

 

_**トピックの最終更新日:** 2015-06-22_

組織が契約しているすべての電話会議プロバイダーに関する情報を返すには、パラメーターなしで [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider) コマンドレットを実行するだけです。

    Get-CsAudioConferencingProvider

返されるデータを 1 つのプロバイダー (この例では Contoso Audio Services) に限定したい場合は、Identity パラメーターを使用します。

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

電話会議プロバイダー ID を使用できる Skype for Business Online コマンドレットは 1 つだけです。

  - [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider)

## 関連項目

#### 概念

[ID、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

