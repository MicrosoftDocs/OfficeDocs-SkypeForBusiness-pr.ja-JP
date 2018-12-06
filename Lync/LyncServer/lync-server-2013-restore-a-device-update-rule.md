---
title: デバイス更新ルールの復元
TOCTitle: デバイス更新ルールの復元
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994061(v=OCS.15)
ms:contentKeyID: 52056676
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新ルールの復元

 

_**トピックの最終更新日:** 2013-02-23_

展開内のデバイスからデバイス更新ルールをアンインストールするには、デバイス更新ルールを復元します。デバイス更新ルールを復元すると、更新ルールがアンインストールされ、その更新ルールの前のバージョンが再インストールされます。

Lync Server コントロール パネルまたは Windows PowerShell を使用して、デバイス更新ルールを復元できます。

## Lync Server コントロール パネルを使用してデバイス更新ルールを復元するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの更新**\] ナビゲーション ボタンをクリックします。

4.  \[**デバイスの更新**\] ページで、次のどちらかの操作を行います。
    
      - 1 つのルールを復元するには、そのルールを選択します。
    
      - すべてのルールを復元するには、\[**編集**\]、\[**すべて選択**\] の順にクリックします。

5.  \[**アクション**\] メニューをクリックし、\[**復元**\] をクリックします。

## Windows PowerShell コマンドレットを使用してデバイス更新ルールを復元する

デバイス更新ルールは、Windows PowerShell および **Restore-CsDeviceUpdateRule** コマンドレットを使用して復元することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


## サーバー上の単一のデバイス更新ルールを復元するには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com 上のデバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を復元します。
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## サーバー上のすべてのデバイス更新ルールを復元するには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com のすべてのデバイス更新ルールを復元します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

詳細については、[Restore-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Restore-CsDeviceUpdateRule) コマンドレットに関するヘルプ トピックを参照してください。

