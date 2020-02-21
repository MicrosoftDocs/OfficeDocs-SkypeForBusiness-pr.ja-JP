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
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 のディレクターに必要なコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

ディレクターを作成して構成するために必要なコンポーネントは、ディレクターサーバーの役割を展開することだけです。 これを行うには、トポロジビルダーを使用して、ディレクタープールノードに1台のコンピュータープールまたは複数のコンピュータープールを定義します。 ディレクターまたはディレクタープールを定義した後、ディレクターになるコンピューターで Lync Server 展開ウィザードを実行します。 ディレクタープールの場合は、プールのメンバーになる各サーバーで Lync Server 展開ウィザードを実行します。

<div>

## <a name="topologies"></a>テクノロジ

単一のディレクターサーバーまたはディレクタープールを実装できます。 ディレクターは常に別個のサーバーまたはプールで、Lync Server 2013 の他のサーバーの役割とは併置されていません。

<div>


> [!NOTE]  
> ディレクターを展開しない場合は、フロントエンドサーバーまたはフロントエンドプールがディレクターの役割を引き受けます。



</div>

ディレクターのプールは負荷分散されている必要があります。 これには次のどちらかの方法を使用します。

  - Web サービスおよびドメイン ネーム システム (DNS) の負荷分散用のロード バランサー機器を他の種類のトラフィックに使用するトポロジを作成する。
    
    [拡張ディレクタープール-Lync Server 2013 での DNS 負荷分散とロードバランサー機器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - ディレクタープールに必要な負荷分散のためにロードバランサー機器を使用するトポロジを作成します。
    
    [拡張ディレクタープール-Lync Server 2013 のハードウェアロードバランサー](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

