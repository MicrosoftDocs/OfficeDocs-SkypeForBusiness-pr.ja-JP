---
title: アドレス帳管理用の New-CsAddressBookConfiguration
TOCTitle: アドレス帳管理用の New-CsAddressBookConfiguration
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48273093
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の New-CsAddressBookConfiguration

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが New-CsAddressBookConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

New-CsAddressBookConfiguration コマンドレットは、アドレス帳の動作を管理する新しい構成を作成します。 アドレス帳サービスによるクライアント ダウンロード ファイルの作成の有無、正規化ルールの使用方法と使用の有無、差分ファイルと圧縮差分ファイルの保持期間、新しい完全なファイルを作成する前の圧縮ファイル サイズ、完全なファイルのアドレス帳の作成時刻、ユーザー データベース情報の同期間隔は、このコマンドレットでのみ定義できます。

次にその例を示します。

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[New-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAddressBookConfiguration)

