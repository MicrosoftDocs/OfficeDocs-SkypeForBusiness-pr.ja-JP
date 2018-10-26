---
title: CDR 構成情報の表示
TOCTitle: CDR 構成情報の表示
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49887005
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CDR 構成情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。

Microsoft Lync Server 2013 をインストールすると、CDR 構成設定のグローバル コレクションが 1 つ、自動的に作成されます。管理者は、個別のサイトに適用できるカスタム設定コレクションを作成することもできます。Lync Server コントロール パネルまたは [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration) コマンドレットを使用すると、組織で使用されている CDR の構成設定を表示できます。

## Lync Server コントロール パネルを使用して CDR の構成情報を表示するには

1.  Lync Server コントロール パネルで \[**監視およびアーカイブ**\] をクリックします。

2.  すべての CDR 構成設定の一覧が、\[**通話詳細記録**\] タブに表示されます。設定の各コレクションについて、コレクションの \[**名前**\]、CDR が有効になっているかどうか (\[**CDR**\] プロパティ)、削除が有効になっているかどうか (\[**CDR の削除**\] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して \[**編集**\] をクリックし、続いて \[**詳細の表示**\] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。

## Lync Server 管理シェル コマンドレットを使用して CDR 構成情報を表示するには

Lync Server 管理シェルと Get-CsCdrConfiguration コマンドレットを使用して CDR 構成設定を表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## CDR の構成情報を表示するには

  - すべての CDR 構成設定についての情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsCdrConfiguration
    
    次のような情報を戻します。
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

詳細については、[Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration) コマンドレットのヘルプ トピックを参照してください。

