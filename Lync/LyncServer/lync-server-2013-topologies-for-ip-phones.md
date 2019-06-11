---
title: 'Lync Server 2013: IP 電話のトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Lync Server 2013 の IP 電話のトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-21_

このセクションでは、接続プロセスの概要について説明し、IP 電話が内部と外部のネットワークで接続する方法の違いについて説明します。

<div>


> [!NOTE]  
> Lync Server では、次の IP 電話のサポートが提供されます: Aastra 6721ip 共通エリアフォン、Aastra 6721ip 卓上電話、HP 4110 IP 電話 (共通エリア電話)、HP 4120 IP 電話 (卓上電話)、Polycom CX600 ip 卓上電話、Polycom CX700 ip 卓上電話、Polycom CX500 IP一般的なエリア電話と Polycom CX3000 IP 会議電話。 これらの携帯電話では、Polycom CX700 以外はすべて Lync Phone Edition を実行できます。



</div>

次の図は、企業環境内のデバイス接続に関連するすべてのコンポーネントについて説明しています。

**内部トポロジ**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> 上の図は論理的な表現であり、物理的な概要ではありません。 たとえば、Active Directory ドメインサービス (AD DS) は、Lync Server コンポーネントと同じコンピューター上に存在することはほとんどありません。 ユーザーストアはバックエンドサーバーまたはアーカイブおよび監視サーバー上に配置できます。 Lync Server 管理シェル、web サーバー、更新サービスはすべて、フロントエンドサーバーの役割の一部です。



</div>

次の図は、デバイスが企業ネットワークの外部にある場合に関連するコンポーネントの概要を示しています。

**外部トポロジ**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> デバイス更新 Web サービスでは、外部と内部の web サイトが提供されますが、外部の web サイトのみがここに表示されます。<BR>外部アクセスを有効にするには、レジストラーの場所と、組織のデバイス更新 Web サービスの URL が DNS に公開されている必要があります。 さらに、エッジサーバーを展開し、デバイスから企業環境への外部通信を許可するように適切に構成する必要があります。 Edge の展開はデバイス接続に固有ではないため、前の図では省略します。



</div>

</div>

<span> </span>

</div>

</div>

</div>

