---
title: デバイス更新ログ ファイルの削除
TOCTitle: デバイス更新ログ ファイルの削除
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994039(v=OCS.15)
ms:contentKeyID: 52056612
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新ログ ファイルの削除

 

_**トピックの最終更新日:** 2013-02-23_

デバイス更新 Web サービスには、さまざまなログ ファイルのコレクションが保持されます。このコレクションには、サービス自体が実行する監査ログのほかに、クライアント デバイスからアップロードされるログ ファイルも含まれます。サーバーがデバイス更新 Web サービスのサービス ログでいっぱいにならないように、所定の日数が経過したらログ ファイルをクリアすることをお勧めします。この日数は、組織内の更新アクティビティとクライアント デバイス数に基づいて、Lync Server コントロール パネルまたは Lync Server 管理シェルを使用して設定します。

## Lync Server コントロール パネルを使用して、デバイス更新ログをクリアするには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイス ログ構成**\] をクリックします。

3.  \[**デバイス ログ構成**\] ページで、変更する構成をダブルクリックします。

4.  \[**編集ログ設定**\] ダイアログ ボックスの \[**ログ ファイルを保持する日数 (1 ～ 365)**\] で、日数を指定します。

5.  \[**確定**\] をクリックします。指定した日数が経過した、サーバー上のすべてのファイルが削除されます。この設定は、変更するまでこの構成に適用されます。

## Windows PowerShell コマンドレットを使用して、デバイス更新ログをクリアする

デバイス更新ログをクリアするには、Windows PowerShell と **Clear-CsDeviceUpdateLog** コマンドレットを使用します。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


## 1 台のサーバーでデバイス更新ログをクリアするには

  - 次のコマンドを実行すると、Web サーバー atl-cs-001.litwareinc.com のデバイス更新ログがクリアされます。作成してからの日数が 10 日 (DaysBack パラメーターで指定) を超えるすべてのログ エントリがログから削除されます。
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

## デバイス更新ログをクリアするには

  - 次のコマンドを実行すると、古くなったエントリ (この例では、作成してから 10 日を超えるエントリ) が、現在組織で使用されているすべてのデバイス更新ログからクリアされます。
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

詳細については、[Clear-CsDeviceUpdateLog](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateLog) コマンドレットに関するヘルプ トピックを参照してください。

