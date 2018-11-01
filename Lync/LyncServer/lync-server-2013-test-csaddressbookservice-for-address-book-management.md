---
title: アドレス帳管理用の Test-CsAddressBookService
TOCTitle: アドレス帳管理用の Test-CsAddressBookService
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48273391
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Test-CsAddressBookService

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Test-CsAddressBookService コマンドレットの実行を承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 には、多数のコマンドレットがあります。これらのコマンドレットは、総合的なコマンドを起動して、特定の関数や機能が正常に動作していることを確認します。 Test-CsAddressBookService は、定義されているユーザーが接続できることと、アドレス帳 Web サービスからローカル ファイルを要求できることを確認します。

次にその例を示します。

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

## 関連項目

#### その他のリソース

[Test-CsAddressBookService](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookService)

