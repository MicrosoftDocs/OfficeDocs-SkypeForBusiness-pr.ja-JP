---
title: 'Lync Server 2013: エッジコンポーネントのサポートされるサーバーの併置位置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71c8e30cfd4257982781e446a61c18518b570e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524004"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Lync Server 2013 のエッジコンポーネントに対してサポートされているサーバーの併置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

アクセスエッジサービス、Web 会議エッジサービス、音声ビデオエッジサービス、および XMPP プロキシサービスがエッジサーバーに併置されます。 次のサーバーは、外部ユーザー アクセスに必要な機能を提供し、専用サーバーとして展開される必要があります。

  - エッジ サーバー

  - ディレクター (オプション)

  - リバース プロキシ

<div>


> [!IMPORTANT]  
> リバースプロキシは、Lync Server 2013 のサービスのみを提供するための専用である必要はありません。 たとえば、lync server Web サービスを公開するためのサービスを提供し、Lync Server にまったく影響を与えない別の Web サイトに対して同時に公開された Web サイトを提供することができます。 他のサービスをサポートするために、既に境界ネットワークにリバースプロキシサーバーがある場合は、それを Lync Server 2013 に使用できます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

