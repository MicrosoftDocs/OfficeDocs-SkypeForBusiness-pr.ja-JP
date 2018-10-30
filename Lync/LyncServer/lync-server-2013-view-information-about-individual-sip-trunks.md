---
title: 個別の SIP トランク情報の表示
TOCTitle: 個別の SIP トランク情報の表示
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49887097
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 個別の SIP トランク情報の表示

 

_**トピックの最終更新日:** 2013-02-21_

SIP トランクは、Microsoft Lync Server 2013 のボイス オーバー IP 電話ネットワークを公衆交換電話網 (PSTN) と接続するために使用されます。以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。

ところが、Lync Server 2013 では、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができるようになりました。つまり、ゲートウェイとトランクは、もはや同じ 1 つのものでありません。また、管理者は、個々の SIP トランクに関する情報を表示するために新しい [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) コマンドレットを使用する必要があります。

Get-CsTrunk コマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## すべての SIP トランクに関する情報の表示

  - 次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。
    
        Get-CsTrunk

## 特定の SIP トランクに関する情報の表示

  - このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

## プールに割り当てられているすべての SIP トランクに関する情報の表示

  - この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

