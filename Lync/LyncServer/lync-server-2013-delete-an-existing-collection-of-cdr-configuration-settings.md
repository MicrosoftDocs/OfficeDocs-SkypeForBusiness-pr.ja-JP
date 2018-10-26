---
title: CDR 構成設定の既存コレクションの削除
TOCTitle: CDR 構成設定の既存コレクションの削除
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49887044
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CDR 構成設定の既存コレクションの削除

 

_**トピックの最終更新日:** 2013-02-23_

通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。

Microsoft Lync Server 2013 をインストールすると、CDR の構成設定の単一のグローバル コレクションが作成されます。管理者は、個々のサイトに適用できるカスタム設定のコレクションを作成することもできます。設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。

なお、"削除" はグローバル設定に対しても実行できます。ただし、グローバル設定は実際には削除されません。代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。たとえば、既定では CDR 構成設定のコレクションでパージが有効になります。パージが無効になるようにグローバル コレクションを変更すると想定します。後でグローバル設定を削除した場合、すべてのプロパティが既定値にリセットされます。この場合、パージが再び有効になります。

CDR 構成設定は、Lync Server コントロール パネルまたは [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration) コマンドレットを使用して削除できます。

## Lync Server コントロール パネルを使用して CDR構成設定を削除するには

1.  Lync Server コントロール パネルで、\[**監視およびアーカイブ**\] をクリックします。

2.  \[**通話詳細記録**\] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。

3.  \[**編集**\] をクリックして、\[**削除**\] をクリックします。

4.  Lync Server コントロール パネル ダイアログ ボックスで \[**OK**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して CDR 構成設定を削除するには

Windows PowerShell および **Remove-CsCdrConfiguration** コマンドレットを使用して、通話詳細記録構成設定を削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定された CDR 構成設定のコレクションを削除するには

  - このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

## サイト スコープに適用されていた CDR 構成設定をすべて削除するには

  - このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

## 通話詳細記録を無効にする CDR 構成設定をすべて削除するには

  - このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

詳細については、[Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration) コマンドレットのヘルプ トピックを参照してください。

