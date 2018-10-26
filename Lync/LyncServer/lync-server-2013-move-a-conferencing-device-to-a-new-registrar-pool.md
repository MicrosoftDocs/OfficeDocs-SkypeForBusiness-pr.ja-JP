---
title: 新しいレジストラー プールに会議デバイスを移動する
TOCTitle: 新しいレジストラー プールに会議デバイスを移動する
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994025(v=OCS.15)
ms:contentKeyID: 52056558
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 新しいレジストラー プールに会議デバイスを移動する

 

_**トピックの最終更新日:** 2013-02-20_

**Move-CsMeetingRoom** コマンドレットを使用して会議デバイスをレジストラー プール間で移動します。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。



## 新しいレジストラー プールへの会議デバイスの移動

  - 会議デバイスを移動するには、移動元の部屋の ID を指定した後、Target パラメータを、デバイスの移動先のレジストラー プールの完全修飾ドメイン名 (FQDN) に設定する必要があります。たとえば、次のようになります。
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

詳細については、[Move-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsMeetingRoom) コマンドレットに関するヘルプ トピックを参照してください。

