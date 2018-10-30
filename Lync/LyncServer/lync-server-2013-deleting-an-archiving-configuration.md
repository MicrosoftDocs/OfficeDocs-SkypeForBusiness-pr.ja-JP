---
title: アーカイブ構成の削除
TOCTitle: アーカイブ構成の削除
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48273180
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブ構成の削除

 

_**トピックの最終更新日:** 2013-02-23_

サイトまたはプールの構成を削除できます。グローバル構成は削除できません。グローバル構成を削除すると、自動的に既定値にリセットされます。指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」のドキュメント、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

## アーカイブ用のサイトまたはプールの構成を削除するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ構成**\] をクリックします。

4.  アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

5.  \[**確定**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用してアーカイブ構成設定を削除する

アーカイブ構成設定は、Windows PowerShell と Remove-CsArchivingConfiguration コマンドレットを使用して削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモート Windows PowerShell の使用の詳細については、リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定したアーカイブ構成設定のコレクションを削除する

  - 次のコマンドを実行すると、レドモンド サイトに適用されているアーカイブ構成設定が削除されます。
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

## サイト スコープに適用されているすべてのアーカイブ構成設定を削除する

  - このコマンドを実行すると、サービス スコープに適用されているすべてのアーカイブ構成設定が削除されます。
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

## 指定したプロパティ値に基づいてアーカイブ構成設定を削除する

  - このコマンドを実行すると、Exchange のアーカイブが無効になっているすべてのアーカイブ構成設定が削除されます。
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

詳細については、[Remove-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### 概念

[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  

#### その他のリソース

[Lync Server 2013 での内部通信および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

