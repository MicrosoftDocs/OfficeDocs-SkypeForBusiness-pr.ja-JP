---
title: デバイス更新プログラム ルールをインポートする
TOCTitle: デバイス更新プログラム ルールをインポートする
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994056(v=OCS.15)
ms:contentKeyID: 52056653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新プログラム ルールをインポートする

 

_**トピックの最終更新日:** 2013-02-23_

デバイス更新プログラム ルールは、Windows PowerShell と **Import-CsDeviceUpdate** コマンドレットを使用してのみインポートできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。



## 単一の Web サーバーにデバイス更新プログラム ルールをインポートするには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com にデバイス更新プログラム ルールをインポートします。
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

## すべての Web サーバーにデバイス更新プログラム ルールをインポートするには

  - このサンプルでは、デバイス更新プログラム ルールは、組織に展開されたすべての Web サーバーにインポートされます。このコマンドを機能させるには、フォルダー \\\\atl-fs-001.litwareinc.com\\Updates をすべての Web サーバーで共有して、使用可能にする必要があります。
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

詳細については、[Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### タスク

[デバイス更新ルールに関する情報の表示](lync-server-2013-view-information-about-device-update-rules.md)  
[デバイス更新プログラム ルールを承認する](lync-server-2013-approve-a-device-update-rule.md)

