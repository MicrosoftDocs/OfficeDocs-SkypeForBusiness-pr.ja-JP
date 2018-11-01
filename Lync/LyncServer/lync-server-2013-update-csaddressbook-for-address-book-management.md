---
title: アドレス帳管理用の Update-CsAddressBook
TOCTitle: アドレス帳管理用の Update-CsAddressBook
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48271289
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の Update-CsAddressBook

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Update-CsAddressBook コマンドレットをローカルで実行することを承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Update-CsAddressBook コマンドレットは、Office Communications Server の **abserver.exe –syncNow** コマンドの代わりに使用されます。 このコマンドレットの目的は、スケジュールされた時間を待機することなくすぐに同期を開始することです。 最初の例のコマンドは、組織のすべてのアドレス帳を更新します。 2 番目のコマンドは、定義されたサーバーに関連付けられたアドレス帳だけを更新します。

> [!NOTE]
> Lync Server 2013 では、Lync Server ユーザー レプリケーターが Active Directory から変更を検出し、構成されている間隔に基づいて Lync Server ユーザー データベースを更新します。また、Lync Server ユーザー レプリケーターは、管理者が Update-CSAddressBook を実行しなくても、RTCab データベースに変更をすばやく反映します。管理者は、アドレス帳ファイルのダウンロードが有効になっている場合にのみ Update -CSAddressBook を実行する必要があります。


次にその例を示します。

    Update-CsAddressBook

&nbsp;

    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com

コマンド全体の詳細については、Lync Server Windows PowerShell RTCCmdlets メイン リファレンスの次の項目を参照してください。

## 関連項目

#### その他のリソース

[Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook)

