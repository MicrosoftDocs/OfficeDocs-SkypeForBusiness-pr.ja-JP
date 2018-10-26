---
title: アドレス帳管理用の Set-CsAddressBookConfiguration
TOCTitle: アドレス帳管理用の Set-CsAddressBookConfiguration
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48271802
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Set-CsAddressBookConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーは Set-CsAddressBookConfiguration コマンドレットのローカル実行を承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

Set-CsAddressBookConfiguration は、既存の構成を変更するために使用するという点を除けば、New-CsAddressBookConfiguration コマンドレットによく似ています。

次にその例を示します。

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Set-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAddressBookConfiguration)

