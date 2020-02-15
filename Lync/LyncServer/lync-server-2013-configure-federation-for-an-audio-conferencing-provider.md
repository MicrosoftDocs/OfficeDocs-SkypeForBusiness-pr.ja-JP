---
title: 'Lync Server 2013: 電話会議プロバイダーのフェデレーションを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4725e80a00da46b7d446b8b8c938b65c569ef8d1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Lync Server 2013 で電話会議プロバイダーのフェデレーションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-07-24_

ハイブリッド展開でのオーディオ会議プロバイダー (ACP) (Lync Online を使用する Lync Server オンプレミス) を使用する場合は、オンプレミスの Lync 展開と ACP パートナーとの間のフェデレーションを許可されたパートナーサーバーとして構成する必要があります。 フェデレーションを構成するには、オンプレミス展開のために、ACP パートナードメインとエッジサーバー (アクセスプロキシとも呼ばれることもあります) をフェデレーションドメインリストに追加します。 その後、ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。 他の詳細については、ACP プロバイダーにお問い合わせください。 ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。

  - **許可されたフェデレーションドメインとしての ACP ドメインおよびエッジサーバーの追加**
    
    許可されたパートナーサーバー (許可されるフェデレーションドメイン) として ACP ドメインを追加するには、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成](lync-server-2013-configure-support-for-allowed-external-domains.md)する」の手順を実行します。 エッジサーバーには、ACP パートナーのエッジサーバーの FQDN を追加します。 エッジサーバーの FQDN を取得するには、ACP パートナーに連絡する必要がある場合があります。これは、アクセスプロキシとして ACP によって参照されることもあります。

  - **ACP パートナーへのエッジサーバープールの FQDN の指定**
    
    ACP パートナーは、許可されるフェデレーションドメインとしてエッジサーバープールの FQDN を追加することによって、オンプレミスのドメインを許可されたパートナーサーバーとして追加するようにフェデレーションを構成する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

