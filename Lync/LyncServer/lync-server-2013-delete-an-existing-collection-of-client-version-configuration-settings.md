---
title: クライアント バージョン構成設定の既存コレクションを削除する
TOCTitle: クライアント バージョン構成設定の既存コレクションを削除する
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ898480(v=OCS.15)
ms:contentKeyID: 52056626
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント バージョン構成設定の既存コレクションを削除する

 

_**トピックの最終更新日:** 2013-02-23_

以前にサイトに対して構成されたクライアント構成設定を削除する場合、設定を Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルから削除できます。

## Lync Server コントロール パネルを使用してクライアント構成設定を削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョンの構成**\] ナビゲーション ボタンをクリックします。

4.  サイトを選択し、\[**編集**\]、\[**削除**\]、\[**OK**\] の順にクリックします。

## Windows PowerShell コマンドレットを使用してクライアント バージョン構成設定を削除する

**Remove-CsClientVersionConfiguration** コマンドレットを使用して、クライアント バージョン構成設定を削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定されたクライアント バージョン構成設定のコレクションを削除するには

  - 次のコマンドを実行すると、Redmond サイトに適用されていたクライアント バージョン構成設定が削除されます。
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

## サイト スコープに適用されたすべてのクライアント バージョン構成設定を削除するには

  - このコマンドは、サイト スコープで構成されたすべてのクライアント バージョン構成設定を削除します。
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## DefaultAction プロパティの値に基づいてすべてのクライアント バージョン構成設定を削除するには

  - このコマンドは、以下のように、既定のアクションが "Block" に設定されたすべてのクライアント バージョン構成設定を削除します。
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

詳細は、[Remove-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionConfiguration) コマンドレットのヘルプ トピックを参照してください。

