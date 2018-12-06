---
title: 既存のクライアント バージョン ポリシーの削除
TOCTitle: 既存のクライアント バージョン ポリシーの削除
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ923064(v=OCS.15)
ms:contentKeyID: 52056684
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存のクライアント バージョン ポリシーの削除

 

_**トピックの最終更新日:** 2013-02-23_

以前構成したクライアント バージョン ポリシーを削除する場合は、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルから削除できます。

## Lync Server コントロール パネルを使用してクライアント バージョン ポリシーを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョン ポリシー**\] ナビゲーション ボタンをクリックします。

4.  \[**クライアント バージョン ポリシー**\] ページで、削除するクライアント バージョン ポリシー (複数選択可) を選択し、\[**編集**\]、\[**削除**\] の順にクリックします。

## Windows PowerShell コマンドレットを使用してクライアント バージョン ポリシーを削除する

クライアント バージョン ポリシーは、**Remove-CsClientVersionPolicy** コマンドレットを使用して削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 特定のクライアント バージョン ポリシーを削除するには

  - 次のコマンドは、Redmond サイトに適用されているクライアント バージョン ポリシーを削除します。
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

## サイト スコープに適用されていたクライアント バージョン ポリシーをすべて削除するには

  - 次のコマンドは、サイト スコープで構成されたすべてのクライアント バージョン ポリシーを削除します。
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

## 特定のユーザー エージェントを含まないクライアント バージョン ポリシーを削除するには

  - また次のコマンドは、Windows Phone Lync (WPLync) ユーザー エージェントのルールを含まないクライアント バージョン ポリシーを削除します。
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

詳細については、[Remove-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionPolicy) コマンドレットに関するヘルプ トピックを参照してください。

