---
title: アーカイブ サーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848062"
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

Office Communications Server 2007 R2 でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Lync Server 2013 環境に展開できます。 ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行を行う前に、アーカイブと監視を試験的なプールに追加することをお勧めします。これにより、移行プロセス中に機能を利用できるようになります。

移行と共存の段階でアーカイブと監視の機能が必要な場合は、次の点に注意してください。

  - データのアーカイブとデータの監視は、Lync Server 2013 の展開には移行されません。 従来の環境を廃止する前にバックアップしたデータは、Office Communications Server 2007 R2 でのアクティビティの履歴となります。

  - Office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーは、Office Communications Server 2007 R2 フロントエンドプールにのみ関連付けることができます。 Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなくなりましたが、Lync Server 2013 フロントエンドプールに統合されたサービスです。

  - 従来の、および Lync Server 2013 の展開が共存する間、Office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーによって、Office Communications Server 2007 R2 プールを使用しているユーザーのデータが収集されます。 Lync server 2013 バージョンのアーカイブサーバーと監視サーバーは、Lync Server 2013 プールに所属しているユーザーのデータを収集します。
    
    <div>
    

    > [!NOTE]  
    > 新しい Lync Server 2013 パイロットプールで従来のエッジサーバーを使用している場合、移行のフェーズ中に、office communications Server 2007 R2 バージョンのアーカイブサーバーでは、Office Communications Server 2007 を使っているユーザーのデータを収集し続けることができます。R2 プールと Lync Server 2013 バージョンのアーカイブサーバーでは、Lync Server 2013 プールに所属しているユーザーのデータが収集されます。

    
    </div>

  - サードパーティのアーカイブと監視ソリューションをアーカイブサーバーおよび監視サーバーと組み合わせて使用する場合は、サードパーティソリューションと Lync Server 2013 を統合する時期とその方法について、ベンダーにお問い合わせください。

</div>

<span> </span>

</div>

</div>

</div>

