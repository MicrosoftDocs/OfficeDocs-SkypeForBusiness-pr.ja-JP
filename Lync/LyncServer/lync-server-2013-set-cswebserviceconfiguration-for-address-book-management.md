---
title: アドレス帳管理用の Set-CsWebServiceConfiguration
TOCTitle: アドレス帳管理用の Set-CsWebServiceConfiguration
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48272581
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Set-CsWebServiceConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Set-CsWebServiceConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

Set-CsWebServiceConfiguration コマンドレットを使用すると、管理者は Web サービスの構成内の既存の属性を再定義できます。

次にその例を示します。

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

