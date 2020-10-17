---
title: アーカイブ サーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba32bf2b35a0d2e8b0048ebb9c62aac09cb6eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527414"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>アーカイブ サーバーと監視サーバーの移行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Lync Server 2010 環境にアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Lync Server 2013 環境に展開することができます。 ただし、アーカイブおよび監視機能が組織にとって重要な場合は、移行の前に Lync Server 2013 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能を利用できるようにする必要があります。

移行プロセスで、アーカイブ機能と監視機能が必要な場合は、以下の点を考慮してください。

  - アーカイブデータと監視データは、Lync Server 2013 展開に移動されません。 レガシ環境を使用停止にする前にバックアップしたデータは、Lync Server 2010 環境でのアクティビティの履歴になります。

  - Lync Server 2010 バージョンのアーカイブサーバーと監視サーバーは、Lync Server 2010 のフロントエンドプールにのみ関連付けることができます。 Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなく、Lync Server 2013 フロントエンドプールに統合されたサービスです。

  - 従来の展開と Lync Server 2013 の展開が共存している間に、lync server 2010 バージョンのアーカイブサーバーと監視サーバーは、Lync Server の2010プールに所属するユーザーに対してデータを収集します。 Lync Server 2013 でのアーカイブと監視 Lync Server 2013 プールに所属するユーザーのためにデータを収集します。
    
    <div>
    

    > [!NOTE]  
    > 移行のフェーズでは、新しい Lync Server 2013 パイロットプールを使用して従来のエッジサーバーを引き続き使用している場合、lync server 2010 バージョンのアーカイブサーバーは、lync server 2010 プールに所属するユーザーのデータを引き続き収集し、lync server 2013 のアーカイブによって lync Server の2013プールに所属するユーザーのデータを収集します。

    
    </div>

  - Lync Server 2013 でのアーカイブと監視と共にサードパーティのアーカイブおよび監視ソリューションを使用する場合は、サードパーティ製ソリューションと Lync Server 2013 を統合する時期と方法についてベンダーにお問い合わせください。

</div>

<span> </span>

</div>

</div>

</div>

