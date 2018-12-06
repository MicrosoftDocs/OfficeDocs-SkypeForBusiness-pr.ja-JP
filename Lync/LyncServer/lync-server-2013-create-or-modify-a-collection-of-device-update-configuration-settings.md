---
title: デバイス更新構成設定のコレクションの作成または変更
TOCTitle: デバイス更新構成設定のコレクションの作成または変更
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994029(v=OCS.15)
ms:contentKeyID: 52056575
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新構成設定のコレクションの作成または変更

 

_**トピックの最終更新日:** 2016-12-08_

デバイス更新の構成設定を作成するには (サイト スコープのみ)、Windows PowerShell および **New-CsDeviceUpdateConfiguration** コマンドレットを使用します。また、変更するには **Set-CsDeviceUpdateConfiguration** コマンドレットを使用します。これらのコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。



## 既定値を使用するデバイス更新の構成設定を作成するには

  - 次のコマンドでは、Redmond サイト用にデバイス更新の構成設定の新しいセットを作成します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないので、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。

## デバイス更新の構成設定の作成時に 1 つのプロパティ値を変更するには

  - 別のプロパティ値を使用する設定を作成するには、該当するパラメーターとパラメータ値を指定します。たとえば、既定で古いログ ファイルを 21 日ごとに削除するデバイス更新の構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

## デバイス更新の構成設定の作成時に複数のプロパティ値を変更するには

  - 複数のプロパティ値を変更するには、複数のパラメーターを指定します。たとえば、次のコマンドでは、ログのクリーンアップ間隔を 21 日に設定し、さらにログのフラッシュ間隔を 30 分に設定します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

既存のデバイス構成設定の変更の詳細については、[Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration) コマンドレットのヘルプ トピックを参照してください。構成設定コレクションの作成の詳細については、[New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsDeviceUpdateConfiguration) コマンドレットのヘルプ トピックを参照してください。

