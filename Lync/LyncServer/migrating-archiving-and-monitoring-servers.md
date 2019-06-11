---
title: アーカイブ サーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901961ad7456dfd8b0340cba03ff44a9e77a147f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>アーカイブ サーバーと監視サーバーの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Lync Server 2010 環境でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Lync Server 2013 環境に展開できます。 ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行を行う前に、アーカイブと監視を Lync Server 2013 パイロットプールに追加して、移行プロセス中に機能を利用できるようにする必要があります。

移行プロセス中にアーカイブと監視機能が必要な場合は、次の点に注意してください。

  - データのアーカイブとデータの監視は、Lync Server 2013 の展開には移行されません。 従来の環境を廃止する前にバックアップしたデータは、Lync Server 2010 環境でのアクティビティの履歴となります。

  - アーカイブサーバーと監視サーバーの Lync Server 2010 バージョンは、Lync Server 2010 フロントエンドプールにのみ関連付けることができます。 Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなくなりましたが、Lync Server 2013 フロントエンドプールに統合されたサービスです。

  - 従来の、および Lync Server 2013 の展開が共存する間、lync server 2010 バージョンのアーカイブサーバーと監視サーバーによって、Lync Server 2010 プールを使っているユーザーのデータが収集されます。 Lync Server 2013 でのアーカイブと監視 Lync Server 2013 プールに所属しているユーザーのデータを収集します。
    
    <div>
    

    > [!NOTE]  
    > 新しい Lync Server 2013 パイロットプールで従来のエッジサーバーを使用している場合、移行のフェーズ中に、lync server 2010 バージョンのアーカイブサーバーでは、lync server 2010 プールおよび Lync Server 2013 でのアーカイブを使っているユーザーのデータを収集し続けることができます。Lync Server 2013 プールに所属しているユーザーのデータを収集します。

    
    </div>

  - サードパーティのアーカイブと監視ソリューションを Lync Server 2013 のアーカイブと監視と組み合わせて使用する場合は、サードパーティのソリューションと Lync Server 2013 を統合する時期とその方法について、ベンダーにお問い合わせください。

</div>

<span> </span>

</div>

</div>

</div>

