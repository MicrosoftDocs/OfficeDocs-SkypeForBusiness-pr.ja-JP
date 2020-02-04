---
title: 'Lync Server 2013: ディレクターに必要なコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 のディレクターに必要なコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

ディレクターを作成して構成するために必要なコンポーネントは、ディレクターサーバーの役割を展開することだけです。 これを行うには、トポロジビルダーを使用し、1台のコンピュータープールまたはディレクタープールノードの複数のコンピュータープールを定義します。 ディレクターまたはディレクタープールを定義したら、ディレクターになるコンピューターで Lync Server Deployment ウィザードを実行します。 ディレクタープールの場合は、プールのメンバーになっている各サーバーで Lync Server Deployment ウィザードを実行します。

<div>

## <a name="topologies"></a>トポロジー

1つのディレクターサーバーまたはディレクタープールを実装できます。 ディレクターは常に個別のサーバーまたはプールであり、Lync Server 2013 では他のサーバーの役割とは関係ありません。

<div>


> [!NOTE]  
> ディレクターを展開しない場合は、フロントエンドサーバーまたはフロントエンドプールによってディレクターの役割が想定されます。



</div>

ディレクターのプールは、負荷分散されている必要があります。 次のいずれかの操作を行うことができます。

  - その他の種類のトラフィックに対して、web サービスとドメインネームシステム (DNS) 負荷分散用のハードウェアロードバランサーを使用するトポロジを作成します。
    
    [拡張ディレクター プール - Lync Server 2013 の DNS 負荷分散とロード バランサー機器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - ハードウェアロードバランサーを使用するトポロジを作成して、ディレクタープールに必要な負荷分散を行います。
    
    [拡張ディレクター プール - Lync Server 2013 のハードウェア負荷分散](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

