---
title: 'Lync Server 2013: IP およびネットワークプロトコルのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a9792ea8365dcd8941b831c43ab0406f9e33b90
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Lync Server 2013 での IP およびネットワークプロトコルのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 では、次の IP およびネットワークプロトコルがサポートされています。

  - **IP プロトコル。**   Lync server 2013 では、サーバーネットワークの ip バージョン 4 (IPv4) または ip version 6 (IPv6) のいずれかがサポートされています。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 は、デュアル IP スタックが有効になっているネットワークで機能します。

    
    </div>

  - **SIP トランスポートプロトコル。**   一般的に、SIP は少なくとも3つのトランスポートの種類 (ユーザーデータグラムプロトコル (UDP)、伝送制御プロトコル (TCP)、およびトランスポート層セキュリティ (TLS) を使用できます。 既定の SIP 転送構成では、TLS は TCP 上で動作します。 TLS は、Lync Server 2013 ネットワーク内で使用されます。 ネットワークのエッジでは、Lync Server 2013 は TCP 経由で相互運用できます。 Lync Server 2013 は、エンタープライズ通信のセキュリティ、信頼性、およびスケーラビリティに関する最低限の標準を満たしていないため、SIP トランスポートの UDP をサポートしていません。 詳細については、「」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)。「NextHop」のブログ記事「udp または udp では使用できません。
    
    <div>
    

    > [!NOTE]  
    > 各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

