---
title: アドレス帳管理用の Remove-CsAddressBookConfiguration
TOCTitle: アドレス帳管理用の Remove-CsAddressBookConfiguration
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48272212
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Remove-CsAddressBookConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーは Remove-CsAddressBookConfiguration コマンドレットのローカルでの実行を承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

名前が示すとおり、Remove-CsAddressBookConfiguration は定義済みのサイト ID に基づく構成を削除します。

次にその例を示します。

    Remove-CsAddressBookConfiguration -Identity site:Redmond

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Remove-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAddressBookConfiguration)

