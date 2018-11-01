---
title: Lync Server 2013 ユーザー アカウントの再有効化または無効化
TOCTitle: Lync Server 2013 ユーザー アカウントの再有効化または無効化
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48271317
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 ユーザー アカウントの再有効化または無効化

 

_**トピックの最終更新日:** 2016-04-04_

次の手順を実行すると、以前に Lync Server 2013 に対して有効にしたユーザー アカウントを、そのユーザー アカウントについて構成した Lync Server 設定を失うことなく、無効にできます。Lync Server ユーザー アカウントの設定が失われないので、以前に有効にしたことがあるユーザー アカウントを再構成しなくても再度有効にできます。

## 以前に Lync Server に対して有効にしたユーザー アカウントを無効または再度有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  \[**ユーザーの検索**\] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。

5.  表で、無効または再度有効にするユーザー アカウントをクリックします。

6.  \[**アクション**\] メニューで、次のいずれかを実行します。
    
      - ユーザー アカウントを Lync Server 2013 に対して一時的に無効にする場合は、\[**Lync Server に対して一時的に無効にする**\] をクリックします。
    
      - ユーザー アカウントを Lync Server 2013 に対して有効にする場合は、\[**Lync Server に対して再度有効にする**\] をクリックします。

## Windows PowerShell コマンドレットを使用してユーザー アカウントを無効または再度有効にする

**Set-CsUser** コマンドレットを使用して、ユーザー アカウントを一時的に無効にしたり、再度有効にしたりすることもできます。このコマンドレットは、Lync Server 2013 管理シェルからも、Windows PowerShell のリモート セッションからも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザー アカウントを無効にする

  - ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。次に例を示します。
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

## ユーザー アカウントを再度有効にする

  - 無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。次に例を示します。
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

詳細については、[Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server ユーザー アカウントの追加および有効化](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  

#### その他のリソース

[Lync Server 2013 のユーザーの有効化または無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

