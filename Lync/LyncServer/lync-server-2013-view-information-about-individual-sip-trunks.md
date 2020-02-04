---
title: 'Lync Server 2013: 個々の SIP trunks に関する情報を表示する'
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
ms.openlocfilehash: f18b65d119b917d5ba48ef3e6805e4f70ea482ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Lync Server 2013 で個別の SIP trunks に関する情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

SIP trunks は、Lync Server 2013 Voice over IP 電話ネットワークと公衆交換電話網を接続するために使用されます。 以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。 その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。 管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。

ただし、Lync Server 2013 では、複数の trunks を単一の PSTN ゲートウェイに割り当てることができるようになりました。これは、ゲートウェイと trunks が1つではなく、同じであることを意味します。 つまり、個々の SIP トランクに関する情報を表示するために、管理者は新しい[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)コマンドレットを使用する必要があります。

Get-CsTrunk コマンドレットは、Lync Server 2013 Management Shell または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>すべての SIP トランクに関する情報の表示

  - 次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>特定の SIP トランクに関する情報の表示

  - このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>プールに割り当てられているすべての SIP Trunks の情報を表示する

  - この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

