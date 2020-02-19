---
title: 'Lync Server 2013: 直接 SIP 接続'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e7491193d60aad3676400c91e9044b214237df3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="3d63a-102">Lync Server 2013 の直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="3d63a-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d63a-103">_**トピックの最終更新日:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="3d63a-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="3d63a-104">*直接 SIP 接続*を使用して、Lync Server を次のいずれかに接続できます。</span><span class="sxs-lookup"><span data-stu-id="3d63a-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="3d63a-105">IP-PBX (詳細については、「 [Lync Server 2013 の直接 SIP 展開のオプション](lync-server-2013-direct-sip-deployment-options.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3d63a-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="3d63a-106">PSTN ゲートウェイ (詳細については、「 [Lync Server 2013 の pstn ゲートウェイの展開オプション](lync-server-2013-pstn-gateway-deployment-options.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3d63a-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="3d63a-107">直接 SIP 接続を実装する場合、基本的に SIP トランクの実装と同じ展開ステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d63a-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="3d63a-108">どちらの場合も、仲介サーバーの外部インターフェイスを使用して接続を実装します。</span><span class="sxs-lookup"><span data-stu-id="3d63a-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="3d63a-109">唯一異なるのは、SIP トランクを外部エンティティ (ITSP ゲートウェイなど) に接続し、直接 SIP 接続をローカル ネットワーク内の内部エンティティ (IP-PBX や公衆交換電話網 (PSTN) ゲートウェイなど) に接続するという点です。</span><span class="sxs-lookup"><span data-stu-id="3d63a-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3d63a-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="3d63a-110">In This Section</span></span>

  - [<span data-ttu-id="3d63a-111">Lync Server 2013 の直接 SIP 展開のオプション</span><span class="sxs-lookup"><span data-stu-id="3d63a-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="3d63a-112">Lync Server 2013 の PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="3d63a-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

