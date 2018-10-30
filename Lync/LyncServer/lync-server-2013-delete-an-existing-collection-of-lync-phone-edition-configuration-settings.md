---
title: Lync Phone Edition 構成設定の既存コレクションの削除
TOCTitle: Lync Phone Edition 構成設定の既存コレクションの削除
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49886863
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Phone Edition 構成設定の既存コレクションの削除

 

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition を実行しているデバイスの、設定のコレクションをもう使用しない場合は、これを削除します。サイトのコレクションを削除すると、そのサイト内の電話にはグローバル設定が適用されます。グローバル コレクションは削除できません。

> [!NOTE]
> コレクションを削除するのではなく、一部の設定の変更のみ必要な場合があります。その方法の詳細については、「<a href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Lync Phone Edition 構成設定のコレクションの作成または変更</a>」を参照してください。


## Lync Phone Edition の構成設定のコレクションを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの構成**\] 移動ボタンをクリックします。

4.  \[**デバイスの構成**\] ページで、削除するコレクションをクリックし、\[**編集**\] メニューの \[**削除**\] をクリックします。
    
    > [!NOTE]
    > グローバル コレクションを削除すると、設定が既定の設定に戻ります。コレクションがなくなることはありません。


5.  確認ボックスで \[**OK**\] をクリックします。

## Lync Server 管理シェルのコマンドレットを使用して Lync Phone Edition の構成設定を削除するには

Windows PowerShell および **Remove-CsUCConfiguration** コマンドレットを使用して、Lync Phone Edition の構成設定を削除できます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## Lync Phone Edition の構成設定の特定のコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用される UC 電話の構成設定を削除します。
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

## サイト スコープに適用される Lync Phone Edition の構成設定をすべて削除するには

  - 次のコマンドは、サービス スコープに適用される UC 電話の構成設定をすべて削除します。
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

## 電話のロックが無効な Lync Phone Edition の構成設定をすべて削除するには

  - 次のコマンドは、電話のロックが無効にされている UC 電話の構成設定のコレクションをすべて削除します。
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

詳細については、「[Remove-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUCPhoneConfiguration)」を参照してください。

