---
title: デバイス更新の構成設定のコレクションの削除
TOCTitle: デバイス更新の構成設定のコレクションの削除
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994019(v=OCS.15)
ms:contentKeyID: 52056546
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新の構成設定のコレクションの削除

 

_**トピックの最終更新日:** 2013-02-20_

デバイス更新の構成設定は、Windows PowerShell と **Remove-CsdeviceUpdateConfiguration** コマンドレットを使用して削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。


## デバイス更新の構成設定の特定のコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用されたデバイス更新の構成設定を削除します。
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

## サイト スコープに適用されたデバイス更新の構成設定をすべて削除するには

  - 次のコマンドは、サイト スコープに適用されたデバイス更新の構成設定をすべて削除します。
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

## LogCleanUpInterval プロパティの値に基づいてデバイス更新の構成設定を削除するには

  - 次のコマンドは、ログのクリーンアップ間隔が 10 日 (10.00:00:00) を超えている場合にデバイス更新の構成設定をすべて削除します。
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

詳細については、[Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) コマンドレットに関するヘルプ トピックを参照してください。

