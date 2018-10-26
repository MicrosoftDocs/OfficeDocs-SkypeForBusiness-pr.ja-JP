---
title: Lync Server からのユーザー アカウントの削除
TOCTitle: Lync Server からのユーザー アカウントの削除
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49886895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server からのユーザー アカウントの削除

 

_**トピックの最終更新日:** 2013-02-22_

次の手順を実行して、Lync Server 2013 に以前に追加したユーザー アカウントを削除できます。

> [!NOTE]
> ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。ユーザー アカウントを削除せずに一時的に無効にする場合は、「<a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 ユーザー アカウントの再有効化または無効化</a>」を参照してください。


## Lync Server から Lync Server ユーザー アカウントを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  \[**ユーザーの検索**\] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。

5.  表で、削除するユーザー アカウントをクリックします。

6.  \[**操作**\] メニューの \[**Lync Server から削除**\] をクリックします。ダイアログ ボックスが表示されます。

7.  ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。\[**OK**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用してユーザー アカウントを削除する

Disable-CsUser コマンドレットを使用してユーザー アカウントを削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたはリモート セッションの Windows PowerShell から実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザー アカウントの削除

  - ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。次に例を示します。
    
        Disable-CsUser -Identity "Ken Myer"
    
    このコマンドを実行した後、削除したアカウントおよびその以前の設定を再度有効化することはできません。Enable-CsUser コマンドレットを使用して、Ken Myer の新規アカウントを作成する必要があります。

詳細については、[Disable-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsUser) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 ユーザー アカウントの再有効化または無効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  

#### その他のリソース

[Lync Server 2013 のユーザーの有効化または無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

