---
title: デバイスと関連付けられていないデバイス更新プログラム ファイルを削除する
TOCTitle: デバイスと関連付けられていないデバイス更新プログラム ファイルを削除する
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994084(v=OCS.15)
ms:contentKeyID: 52056744
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイスと関連付けられていないデバイス更新プログラム ファイルを削除する

 

_**トピックの最終更新日:** 2013-02-20_

新しいデバイス更新プログラムがシステムにアップロードされるごとに、対応するデバイス更新プログラム ルールが作成されます。これらの新しいデバイス更新プログラム ルールは、既定で Pending 状態に割り当てられます。これは、テスト デバイスにルールをダウンロードしてインストールすることはできても、実働デバイスではそれができないことを意味します。これにより、ユーザーが更新プログラムを使用できるようにする前に、それをテストできます。テストに基づき、受け入れて展開するか、拒否してその更新プログラムを削除できます。ある更新プログラムを拒否したとき、そのデバイス更新プログラムはデバイス更新プログラム ルールから除外されます。


デバイスとの関連付けが解除されたデバイス更新プログラム ファイルは、Windows PowerShell と **Clear-CsDeviceUpdateFile** コマンドレットを使用して削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。



  - たとえば、以下のコマンドを実行すると、デバイスに関連付けられていないすべてのデバイス更新プログラム ルールが Web サーバー atl-cs-001.litwareinc.com から削除されます。
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

詳細については、[Clear-CsDeviceUpdateFile](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateFile) コマンドレットに関するヘルプ トピックを参照してください。

