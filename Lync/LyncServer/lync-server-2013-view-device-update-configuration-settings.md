---
title: 'Lync Server 2013: デバイス更新構成設定の表示'
TOCTitle: デバイス更新構成設定の表示
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994059(v=OCS.15)
ms:contentKeyID: 52056674
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのデバイス更新構成設定の表示

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 管理シェル と **Get-CsDeviceUpdateConfiguration** コマンドレットを使用すると、デバイス更新サービスの構成設定を表示することができます。このコマンドレットは、Lync Server 2013 管理シェル から、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。




  - すべての音声ルートに関する情報を表示するには、Lync Server 管理シェル で次のコマンドを入力し、Enter キーを押します。
    
        Get-CsDeviceUpdateConfiguration
    
    このコマンドは、次のような情報を返します。
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

このコマンドレットの詳細については、[Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateConfiguration) のヘルプ トピックを参照してください。

