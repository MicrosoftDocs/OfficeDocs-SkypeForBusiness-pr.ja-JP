---
title: 'Lync Server 2013: 新しい応答グループ アプリケーションの機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 の新しい応答グループ アプリケーションの機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

応答グループアプリケーションを使用すると、顧客サービス、社内ヘルプデスク、または部門の一般的な電話のサポートなどの特殊な目的のために、指定したユーザーへの着信通話をルーティングしてキューに登録することができます。

次の応答グループアプリケーション機能は、Lync Server 2013 で新しく追加されています。

  - **管理職の役割**
    
    Lync Server 2013 で、新しい応答グループマネージャーの役割が導入されます。 応答グループには、応答グループマネージャーと応答グループの管理者の2つの役割があります。 グループ管理者は応答グループの要素をまだ構成できますが、マネージャーは、所有する応答グループに対してのみ、特定の要素のみを構成できます。
    
    特に大規模な展開シナリオの場合、管理モデルの改善による応答グループのスケーラビリティが向上します。

  - **高可用性**
    
    応答グループアプリケーションの高可用性サポートは、SQL Server のミラーリングの形式でサポートされており、Lync Server 2013 の高可用性の構成と展開の一部として有効になっています。 高可用性を実現するように構成し、プライマリバックエンドサーバーへの接続が切断されている場合、ミラーリングされたバックエンドサーバーを活用しても、応答グループの機能に影響はありません。
    
    応答グループアプリケーションの SQL Server ミラーリングのサポートは、全体的な Lync Server 2013 高可用性構成の外部で個別に有効にしたり構成したりすることはできません。

  - **障害復旧**
    
    応答グループアプリケーションの障害回復のサポートは、すべての Lync Server 2013 の障害回復構成の一部である、ペアリングされたフロントエンドプールの構成と展開の一環として有効になります。 さらに、応答グループのインポートとエクスポートのコマンドレットでは、バックアッププールへのフェールオーバープロセスと、プライマリプールまたは新しいプールへのフェールバック処理がサポートされています。 プライマリプールで障害が発生した場合、応答グループはバックアッププールにフェールオーバーされ、停止したときにプライマリプールまたは新しいプールにフェールバックすることができます。

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での応答グループの計画](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

