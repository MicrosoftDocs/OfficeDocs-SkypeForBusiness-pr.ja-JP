---
title: 'Lync Server 2013: 電話会議プロバイダー用にフェデレーションを構成する'
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
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="ee771-102">Lync Server 2013 で電話会議プロバイダーのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="ee771-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee771-103">_**最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="ee771-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="ee771-104">ハイブリッド展開で電話会議プロバイダー (ACP) を使用する場合 (lync Online でオンプレミスの lync Server を使用する場合)、オンプレミスの Lync 展開と ACP パートナーとの間のフェデレーションを許可パートナーサーバーとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee771-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="ee771-105">フェデレーションは、ACP パートナー ドメインとエッジ サーバー (アクセス プロキシとも呼ばれます) をオンプレミス展開のフェデレーション ドメイン リストに追加すると設定できます。</span><span class="sxs-lookup"><span data-stu-id="ee771-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="ee771-106">その後、APC パートナーは、オンプレミスのエッジ サーバー プールの FQDN を、許可されるフェデレーション ドメイン リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee771-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="ee771-107">ACP プロバイダーにお問い合わせください。詳細については、ACP パートナーが、許可されているフェデレーションドメインリストにオンプレミスエッジサーバープールの FQDN を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee771-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="ee771-108">**許可されるフェデレーション ドメインとしての ACP ドメインおよびエッジ サーバーの追加**</span><span class="sxs-lookup"><span data-stu-id="ee771-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="ee771-109">許可されたパートナーサーバー (許可されたフェデレーションドメイン) として ACP ドメインを追加するには、「 [Lync server 2013 で許可されている外部ドメインのサポートを構成](lync-server-2013-configure-support-for-allowed-external-domains.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ee771-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="ee771-110">エッジ サーバーには、ACP パートナーのエッジ サーバーの FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="ee771-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="ee771-111">ACP からもアクセス プロキシとして参照される可能性があるエッジ サーバーの FQDN を取得するには ACP パートナーへの問い合わせが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ee771-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="ee771-112">**ACP パートナーへのエッジ サーバー プールの FQDN の指定**</span><span class="sxs-lookup"><span data-stu-id="ee771-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="ee771-113">ACP パートナーは、フェデレーションを構成してオンプレミスのドメインを許可されるパートナー サーバーとして追加する必要があります。そのためには、エッジ サーバー プールの FQDN を許可されるフェデレーション ドメインとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ee771-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

