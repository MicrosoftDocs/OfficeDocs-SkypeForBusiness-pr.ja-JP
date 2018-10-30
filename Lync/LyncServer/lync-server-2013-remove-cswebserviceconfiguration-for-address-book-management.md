---
title: アドレス帳管理用の Remove-CsWebServiceConfiguration
TOCTitle: アドレス帳管理用の Remove-CsWebServiceConfiguration
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48272859
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Remove-CsWebServiceConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Remove-CsWebServiceConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

Remove-CsWebServiceConfiguration コマンドレットを使用して、管理者は以前に作成した Web サービス構成を削除できます。 このコマンドレットで、グローバル Web サービス構成を削除することはできません。

次にその例を示します。

    Remove-CsWebServiceConfiguration -Identity site:Redmond

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)

