---
title: 会議構成設定の既存コレクションの削除
TOCTitle: 会議構成設定の既存コレクションの削除
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49887055
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議構成設定の既存コレクションの削除

 

_**トピックの最終更新日:** 2013-02-23_

サイトやユーザーの構成は削除できます。グローバル構成は削除できません。グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。

## サイトまたはユーザーの会議構成を削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**会議**\] をクリックし、\[**会議構成**\] をクリックします。

4.  会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、\[編集\] をクリックして、\[削除\] をクリックします。

## Lync Server PowerShell コマンドレットを使用した会議構成設定の削除

Windows PowerShell および Remove-CsMeetingConfiguration コマンドレットを使用して会議の設定を削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定した会議構成設定のコレクションの削除

  - このコマンドは、Redmond サイトに適用された会議構成設定を削除します。
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

## サイト スコープに適用されたすべての会議構成設定の削除

  - このコマンドは、サイト スコープに適用された会議構成設定をすべて削除します。
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

## 匿名ユーザーを既定で許可するすべての会議構成設定の削除

  - このコマンドは、匿名ユーザーの参加を既定で許可する設定をすべて削除します。
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

詳細については、[Remove-CsMeetingConfiguration](ttps://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMeetingConfiguration) コマンドレットのヘルプ トピックを参照してください。

