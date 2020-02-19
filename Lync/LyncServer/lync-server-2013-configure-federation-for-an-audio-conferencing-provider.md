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
ms.openlocfilehash: a85a8ef64d43561a68dca7c850f79cc6a1632fc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="b0a91-102">Lync Server 2013 で電話会議プロバイダーのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="b0a91-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0a91-103">_**トピックの最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="b0a91-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="b0a91-104">ハイブリッド展開でのオーディオ会議プロバイダー (ACP) (Lync Online を使用する Lync Server オンプレミス) を使用する場合は、オンプレミスの Lync 展開と ACP パートナーとの間のフェデレーションを許可されたパートナーサーバーとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a91-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="b0a91-105">フェデレーションを構成するには、オンプレミス展開のために、ACP パートナードメインとエッジサーバー (アクセスプロキシとも呼ばれることもあります) をフェデレーションドメインリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="b0a91-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="b0a91-106">その後、ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a91-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="b0a91-107">他の詳細については、ACP プロバイダーにお問い合わせください。 ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a91-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="b0a91-108">**許可されたフェデレーションドメインとしての ACP ドメインおよびエッジサーバーの追加**</span><span class="sxs-lookup"><span data-stu-id="b0a91-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="b0a91-109">許可されたパートナーサーバー (許可されるフェデレーションドメイン) として ACP ドメインを追加するには、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成](lync-server-2013-configure-support-for-allowed-external-domains.md)する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0a91-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="b0a91-110">エッジサーバーには、ACP パートナーのエッジサーバーの FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="b0a91-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="b0a91-111">エッジサーバーの FQDN を取得するには、ACP パートナーに連絡する必要がある場合があります。これは、アクセスプロキシとして ACP によって参照されることもあります。</span><span class="sxs-lookup"><span data-stu-id="b0a91-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="b0a91-112">**ACP パートナーへのエッジサーバープールの FQDN の指定**</span><span class="sxs-lookup"><span data-stu-id="b0a91-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="b0a91-113">ACP パートナーは、許可されるフェデレーションドメインとしてエッジサーバープールの FQDN を追加することによって、オンプレミスのドメインを許可されたパートナーサーバーとして追加するようにフェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a91-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

