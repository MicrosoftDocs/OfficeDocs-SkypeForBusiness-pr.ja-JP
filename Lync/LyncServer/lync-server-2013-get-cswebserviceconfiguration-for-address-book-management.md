---
title: アドレス帳管理用の Get-CsWebServiceConfiguration
TOCTitle: アドレス帳管理用の Get-CsWebServiceConfiguration
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48271227
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Get-CsWebServiceConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Get-CsWebServiceConfiguration コマンドレットのローカル実行を承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Get-CsWebServiceConfiguration は、現在組織で使用されている Web サービス構成の情報を戻します。 アドレス帳サービスにとって、配布リスト拡張機能のステータスは重要です。 EnableGroupExpansion 属性が True の場合、現在、ユーザーの組織はグループ拡張を許可しています。

次にその例を示します。

    Get-CsWebServiceConfiguration -Identity site:Redmond

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Get-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWebServiceConfiguration)

