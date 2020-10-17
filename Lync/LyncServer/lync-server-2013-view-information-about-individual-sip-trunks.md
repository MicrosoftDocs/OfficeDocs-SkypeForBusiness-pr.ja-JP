---
title: 'Lync Server 2013: 個別の SIP トランクに関する情報の表示'
description: 'Lync Server 2013: 個々の SIP トランクに関する情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569613"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Lync Server 2013 の個々の SIP トランクに関する情報を表示する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

SIP トランクは、Lync Server 2013 ボイスオーバー IP 電話ネットワークと公衆交換電話網を接続するために使用されます。 以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。 その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。 管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。

ただし、Lync Server 2013 では、複数のトランクを1つの PSTN ゲートウェイに割り当てることができるようになりました。これは、ゲートウェイとトランクが同じではなく、同じであることを意味します。 そのため、管理者は、個々の SIP トランクに関する情報を表示するために、新しい [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) コマンドレットを使用する必要があります。

Get-CsTrunk コマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>すべての SIP トランクに関する情報を表示するには

  - 次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>特定の SIP トランクに関する情報を表示するには

  - このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>プールに割り当てられているすべての SIP トランクに関する情報の表示

  - この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

