---
title: 'Lync Server 2013: IP 電話のトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b01e4d98ced806b40cd5f092c0b8051ce86f47
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Lync Server 2013 での IP 電話のトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-21_

ここでは、接続プロセスの概要を示し、内部ネットワークと外部ネットワークでの IP 電話の接続方法の違いを説明します。

<div>


> [!NOTE]  
> Lync Server は、次の IP 電話のサポートを提供します。 Aastra 6721ip 共通領域電話、Aastra 6721ip 卓上電話、HP 4110 IP 電話 (共通領域電話)、HP 4120 IP 電話 (デスク電話)、Polycom CX600 IP デスク電話、Polycom CX700 IP 卓上電話、Polycom CX500 IP共通領域電話、Polycom CX3000 IP 電話会議 これらの電話の場合、Polycom CX700 以外はすべて Lync Phone Edition を実行できます。



</div>

次の図では、企業環境内でのデバイス接続に関係するすべてのコンポーネントを説明します。

**内部トポロジ**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> 前の図は論理的な表現であり、物理的な概要ではありません。 たとえば、Active Directory ドメインサービス (AD DS) は、ほとんどの場合、すべての Lync Server コンポーネントと同じコンピューターに配置されます。 ユーザー ストアは、バックエンド サーバー上、またはアーカイブ サーバーおよび監視サーバー上に配置できます。 Lync Server 管理シェル、web サーバー、更新サービスは、すべてフロントエンドサーバーの役割の一部です。



</div>

次の図では、デバイスが企業ネットワークの外部に配置される場合に関係するコンポーネントの概要を示します。

**外部トポロジ**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> デバイス更新 Web サービスは、外部および内部の Web サイトを提供しますが、ここでは外部の Web サイトだけを示しています。<BR>外部アクセスを有効にする場合は、レジストラーの場所、および組織に対するデバイス更新 Web サービスの URL を DNS で公開する必要があります。さらに、エッジ サーバーを展開し、デバイスと企業環境の間の双方向の外部通信を許可するように適切に構成する必要があります。エッジの展開がデバイスの接続に固有ではないので、前の図ではこれは省略されています。



</div>

</div>

<span> </span>

</div>

</div>

</div>

