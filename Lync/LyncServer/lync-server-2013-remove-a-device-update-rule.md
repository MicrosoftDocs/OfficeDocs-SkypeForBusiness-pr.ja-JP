---
title: デバイス更新ルールの削除
TOCTitle: デバイス更新ルールの削除
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994066(v=OCS.15)
ms:contentKeyID: 52056678
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新ルールの削除

 

_**トピックの最終更新日:** 2013-02-23_

デバイス更新ルールを削除すると、デバイス更新ルールはデバイス更新キューから完全に削除されます。

ルールを削除することと、展開内のデバイスまたはテスト デバイスから更新をアンインストールすることは異なります。展開から承認済みの更新をアンインストールするには、デバイス更新ルールを復元します。詳細については、「[デバイス更新ルールの復元](lync-server-2013-restore-a-device-update-rule.md)」を参照してください。未承認の更新をテスト デバイスからアンインストールするには、更新をリセットします。詳細については、「[デバイス更新ルールのリセット](lync-server-2013-reset-a-device-update-rule.md)」を参照してください。

Lync Server コントロール パネルまたは Windows PowerShell を使用して、デバイス更新ルールを削除できます。

## Lync Server コントロール パネルを使用してデバイス更新ルールを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの更新**\] ナビゲーション ボタンをクリックします。

4.  \[**デバイスの更新**\] ページで、次のどちらかの操作を行います。
    
      - 1 つのルールを削除するには、削除するルールを選択します。
    
      - すべてのルールを削除するには、\[**編集**\] メニュー、\[**すべて選択**\] の順にクリックします。

5.  \[**編集**\] をクリックして、\[**削除**\] をクリックします。

## Windows PowerShell コマンドレットを使用してデバイス更新ルールを削除する

デバイス更新ルールは、Windows PowerShell および **Remove-CsDeviceUpdateRule** コマンドレットを使用して削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## サーバーから単一のデバイス更新ルールを削除するには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com からデバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を削除します。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## サーバーからすべてのデバイス更新ルールを削除するには

  - 以下コマンドは、Web サーバー atl-cs-001.litwareinc.com からすべてのデバイス更新ルールを削除します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

詳細については、[Remove-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateRule) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### タスク

[デバイス更新プログラム ルールを承認する](lync-server-2013-approve-a-device-update-rule.md)

