---
title: デバイス更新プログラム ルールを承認する
TOCTitle: デバイス更新プログラム ルールを承認する
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994053(v=OCS.15)
ms:contentKeyID: 52056661
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新プログラム ルールを承認する

 

_**トピックの最終更新日:** 2013-02-23_

デバイス更新プログラム ルールをインポートした後、それはテスト デバイスにインストールされます。テストが正常に完了し、更新を組織にロールアウトする場合、Lync Server コントロール パネルまたは Windows PowerShell を使用してそれを承認します。

## Lync Server コントロール パネルを使用してデバイス更新プログラム ルールを承認するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  \[**デバイスの更新**\] ページで、次のどちらかの操作を行います。
    
      - 1 つのルールを承認するには、そのルールを選択します。
    
      - すべてのルールを承認するには、\[**編集**\]、\[**すべて選択**\] の順にクリックします。

4.  \[**操作**\] をクリックして、\[**承認**\] をクリックします。

## Windows PowerShell コマンドレットを使用してデバイス更新プログラム ルールを承認する

デバイス更新プログラム ルールは、Windows PowerShell と **Approve-CsDeviceUpdateRule** コマンドレットを使用して承認することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


## 1 つのデバイス更新プログラム ルールを承認するには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com 上にあるデバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を承認します。
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## 複数のデバイス更新プログラム ルールを承認するには

  - このコマンドは、Microsoft ブランドのデバイスのすべてのデバイス更新プログラム ルールを承認します。
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

詳細については、[Approve-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Approve-CsDeviceUpdateRule) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### タスク

[デバイス更新プログラム ルールをインポートする](lync-server-2013-import-device-update-rules.md)  
[デバイス更新ルールの復元](lync-server-2013-restore-a-device-update-rule.md)

