---
title: アーカイブ ポリシーの削除
TOCTitle: アーカイブ ポリシーの削除
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48271956
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブ ポリシーの削除

 

_**トピックの最終更新日:** 2013-02-23_

ユーザー ポリシーやサイト ポリシーは削除できます。グローバル ポリシーは削除できません。グローバル ポリシーの削除を試みると、Lync Server 2013 によって自動的にポリシーが既定値にリセットされます。

> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange 2013 をホームとし、メールボックスにインプレース保持が適用されたユーザーに対してアーカイブを有効にするかどうかが Exchange のポリシーによって制御されます。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。


## アーカイブに関するユーザー ポリシーまたはサイト ポリシーを削除するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ ポリシー**\] をクリックします。

4.  アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

5.  \[**確定**\] をクリックします。

## Lync Server 管理シェルのコマンドレットを使用してアーカイブ ポリシーを削除する

アーカイブ ポリシーは、Windows PowerShell または **Remove-CsArchivingPolicy** コマンドレットを使用して削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定されたアーカイブ ポリシーを削除する

  - 例では、**Remove-CsArchivingPolicy** を使用して、site:Redmond という ID を持つポリシーを削除します。サイト スコープで構成されているポリシーを削除すると、サイト ポリシーによって管理されていたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。以下のコマンドでは、Redmond サイトに適用されているアーカイブを削除します。
    
        Remove-CsArchivingPolicy -Identity site:Redmond

## ユーザーごとのスコープに適用されているすべてのアーカイブ ポリシーを削除する

  - このコマンドでは、ユーザーごとのスコープに適用されているすべてのアーカイブ ポリシーを削除します。
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

## 内部アーカイブを無効にするすべてのアーカイブ ポリシーを削除する

  - このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

詳細については、[Remove-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での内部通信および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

