---
title: Scope や Identity を使用しないコマンドレット
TOCTitle: Scope や Identity を使用しないコマンドレット
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56270125
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Scope や Identity を使用しないコマンドレット

 

_**トピックの最終更新日:** 2015-06-22_

許可リストや禁止リスト (通信できる外部組織を決定するリスト) の変更に使用するコマンドレットでは、範囲や ID は使用できません。実際、**New-CsEdgeAllowAllKnownDomains** コマンドレットにはそのようなパラメーターはありません。範囲や ID が使用されないコマンドレットは次のとおりです。

  - [New-CsEdgeAllowAllKnownDomains](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowAllKnownDomains)

  - [New-CsEdgeAllowList](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowList)

  - [New-CsEdgeDomainPattern](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeDomainPattern)

**New-CsEdgeAllowList** コマンドレットと **New-CsEdgeDomainPattern** コマンドレットでは、Domain パラメーターを含める必要があります。次に例を示します。

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## 関連項目

#### 概念

[ID、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

