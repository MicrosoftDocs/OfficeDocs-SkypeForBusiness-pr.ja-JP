---
title: 'Lync Server 2013: 新しい応答グループアプリケーションの機能'
description: 'Lync Server 2013: 新しい応答グループアプリケーションの機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 191d3867758da427ade3470e78abfd417f6f00de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541963"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 の新しい応答グループアプリケーション機能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

応答グループ アプリケーションを使用すると、カスタマー サービス、社内のヘルプ デスク、またはある部門の一般的な電話サポートなど、特定の目的のために指定したユーザーに着信通話をルーティングして待機させることができます。

Lync Server 2013 の新しい応答グループアプリケーション機能は次のとおりです。

  - **マネージャーの役割**
    
    Lync Server 2013 には、新しい応答グループマネージャーの役割が導入されています。 応答グループには、応答グループマネージャーと応答グループ管理という2つの管理役割があります。 応答グループ管理者は、すべての応答グループに対して任意の要素を構成できますが、マネージャーは、自分が所有する応答グループに対してのみ特定の要素のみを構成できます。
    
    管理モデルのこの強化により、特に大規模な展開シナリオで応答グループの拡張性にメリットがもたらされます。

  - **高可用性**
    
    応答グループアプリケーションの高可用性サポートは、SQL Server ミラーリングの形式で、Lync Server 2013 の高可用性の全体的な構成および展開の一部として有効になっています。 高可用性を構成すると、プライマリ バックエンド サーバーへの接続が失われた場合でも、ミラー化されたバックエンド サーバーを利用できるため、応答グループの機能に影響を及ぼすことはありません。
    
    応答グループアプリケーションの SQL Server ミラーリングのサポートは、Lync Server 2013 高可用性構成の外部で個別に有効化または構成することはできません。

  - **障害回復**
    
    応答グループアプリケーションの障害復旧のサポートは、対になっているフロントエンドプールの構成および展開の一環として有効になります。これは、Lync Server 2013 の障害復旧構成全体の一部です。 また、応答グループのインポート/エクスポート コマンドレットは、バックアップ プールへのフェールオーバー プロセスと、プライマリ プールまたは新しいプールへのフェールバック プロセスをサポートします。 プライマリ プールで機能停止が発生した場合、応答グループをバックアップ プールにフェールオーバーし、機能が回復したら、プライマリ プールまたは新しいプールにフェールバックできます。

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

