---
title: アドレス帳管理用の Test-CsAddressBookWebQuery
TOCTitle: アドレス帳管理用の Test-CsAddressBookWebQuery
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48272913
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Test-CsAddressBookWebQuery

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Test-CsAddressBookWebQuery コマンドレットを実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Test-CsAddressBookService 代理トランザクションと同様、Test-CsAddressBookWebQuery はアドレス帳 Web クエリに対するクエリを実行し、アドレス帳 Web クエリが正常に動作しているかどうかを確認します。 コマンドレットは Web チケット認証に接続し、–UserCredential で指定した資格情報を提示します。 認証されたら –TargetSipAddress の情報を提示します。 連絡先の情報を取得できたら、成功したことをレポートします。

次にその例を示します。

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Test-CsAddressBookWebQuery](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookWebQuery)

