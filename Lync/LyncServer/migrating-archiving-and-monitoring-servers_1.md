---
title: アーカイブサーバーと監視サーバーの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 799f2258344d94f4dcfc0e477bd3e77316c3a060
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>アーカイブサーバーと監視サーバーの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Office Communications Server 2007 R2 にアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Lync Server 2013 環境に展開することができます。 組織にアーカイブ機能と監視機能が欠かせない場合は、移行前にアーカイブと監視をパイロット プールに追加して、移行プロセス中もアーカイブ機能と監視機能を使用できるように対処する必要があります。

移行および共存フェーズで、アーカイブ機能と監視機能が必要な場合は、次の点を考慮してください。

  - アーカイブデータと監視データは、Lync Server 2013 展開に移動されません。 従来の環境を使用停止にする前にバックアップしたデータは、Office Communications Server 2007 R2 のアクティビティの履歴になります。

  - Office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーは、Office Communications Server 2007 R2 フロントエンドプールにのみ関連付けることができます。 Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなく、Lync Server 2013 フロントエンドプールに統合されたサービスです。

  - レガシおよび Lync Server 2013 の展開が共存する時間に、office Communications Server 2007 R2 バージョンのアーカイブサーバーと監視サーバーは、Office Communications Server 2007 R2 プールに所属するユーザーのデータを収集します。 Lync server 2013 バージョンのアーカイブサーバーおよび監視サーバーは、Lync Server 2013 プールに所属しているユーザーのデータを収集します。
    
    <div>
    

    > [!NOTE]  
    > 移行のフェーズでは、新しい Lync Server 2013 パイロットプールで従来のエッジサーバーを使用している場合、Office communications Server 2007 R2 バージョンのアーカイブサーバーは、Office Communications Server 2007 に所属するユーザーのデータを引き続き収集します。R2 プールおよび Lync Server 2013 バージョンのアーカイブサーバーは、Lync Server 2013 プールに所属しているユーザーのデータを収集します。

    
    </div>

  - サードパーティ製のアーカイブおよび監視ソリューションをアーカイブサーバーおよび監視サーバーと組み合わせて使用する場合は、サードパーティ製ソリューションと Lync Server 2013 を統合する時期と方法について、ベンダーに問い合わせてください。

</div>

<span> </span>

</div>

</div>

</div>

