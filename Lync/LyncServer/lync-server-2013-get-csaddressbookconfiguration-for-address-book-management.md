---
title: アドレス帳管理用の Get-CsAddressBookConfiguration
TOCTitle: アドレス帳管理用の Get-CsAddressBookConfiguration
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48273442
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Get-CsAddressBookConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Get-CsAddressBookConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Get-CsAddressBookConfiguration コマンドレットは、既存の構成に関する情報を返します。

次にその例を示します。

    Get-CsAddressBookConfiguration -Identity site:Redmond

Get-CsAddressBookConfiguration と Set-CsAddressBookConfiguration の機能を組み合わせることで、管理者は変更する構成を定義して、変更を適用することができます。 たとえば、次のように組み合わせます。

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

すべてのサイトの構成を返し、RunTimeOfDay を 23:00 にして、これらの構成に適用しています。

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Get-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAddressBookConfiguration)

