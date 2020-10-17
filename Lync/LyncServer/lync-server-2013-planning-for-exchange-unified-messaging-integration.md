---
title: 'Lync Server 2013: Exchange ユニファイドメッセージング統合の計画'
description: 'Lync Server 2013: Exchange ユニファイドメッセージング統合の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31296444d21a86a7837da3e29fc2152f3ca96ccc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571883"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="c68a4-103">Lync Server 2013 での Exchange ユニファイドメッセージング統合の計画</span><span class="sxs-lookup"><span data-stu-id="c68a4-103">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68a4-104">_**トピックの最終更新日:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="c68a4-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="c68a4-105">Lync Server 2013 は、ボイスメッセージングと電子メールメッセージングを単一のメッセージングインフラストラクチャに結合するための Exchange ユニファイドメッセージング (UM) との統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c68a4-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="c68a4-106">Microsoft Exchange Server 2007 Service Pack 1 (SP1) および Microsoft Exchange Server 2010 では、Exchange ユニファイドメッセージング (UM) は、インストールして構成できる複数の Exchange サーバーの役割の1つです。</span><span class="sxs-lookup"><span data-stu-id="c68a4-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="c68a4-107">Microsoft Exchange Server 2013 では、exchange UM は Exchange メールボックスサーバー上のサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="c68a4-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="c68a4-108">Lync Server 2013 エンタープライズ Voip 展開の場合、ユニファイドメッセージングは、ボイスメッセージングと電子メールメッセージングを、電話 (Outlook Voice Access) またはコンピューターから利用できる1つのストアに結合します。</span><span class="sxs-lookup"><span data-stu-id="c68a4-108">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="c68a4-109">ユニファイドメッセージングおよび Lync Server 2013 は、エンタープライズ Voip のユーザーに通話応答、Outlook Voice Access、および自動応答サービスを提供するために連携しています。</span><span class="sxs-lookup"><span data-stu-id="c68a4-109">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="c68a4-110">Microsoft Exchange Server 2013 のアーキテクチャの変更の詳細については、Microsoft Exchange Server 2013 ドキュメントの「Voice Architecture の変更点」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) 。</span><span class="sxs-lookup"><span data-stu-id="c68a4-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="c68a4-111">これらの機能がオンプレミスの Exchange UM 展開でサポートされるようにするには、次のいずれかを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68a4-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="c68a4-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) または最新のサービスパック</span><span class="sxs-lookup"><span data-stu-id="c68a4-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="c68a4-113">Microsoft Exchange Server 2010 または最新のサービスパック</span><span class="sxs-lookup"><span data-stu-id="c68a4-113">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="c68a4-114">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="c68a4-114">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c68a4-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c68a4-115">In This Section</span></span>

  - [<span data-ttu-id="c68a4-116">統合ユニファイドメッセージングと Lync Server 2013 の機能</span><span class="sxs-lookup"><span data-stu-id="c68a4-116">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="c68a4-117">Lync Server 2013 でのオンプレミスのユニファイドメッセージングのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="c68a4-117">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="c68a4-118">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c68a4-118">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="c68a4-119">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="c68a4-119">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

