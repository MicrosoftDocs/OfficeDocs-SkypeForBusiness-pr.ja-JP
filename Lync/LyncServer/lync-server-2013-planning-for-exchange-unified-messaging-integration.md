---
title: 'Lync Server 2013: Exchange ユニファイド メッセージング統合の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de7f3bc9a3e8a1330fc1a142c491e22a4407f104
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="b83b0-102">Lync Server 2013 での Exchange ユニファイド メッセージング統合の計画</span><span class="sxs-lookup"><span data-stu-id="b83b0-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b83b0-103">_**最終更新日:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="b83b0-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="b83b0-104">Lync Server 2013 は、音声メッセージとメールメッセージを1つのメッセージングインフラストラクチャに統合するための Exchange ユニファイドメッセージング (UM) との統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b83b0-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="b83b0-105">Microsoft Exchange Server 2007 Service Pack 1 (SP1) および Microsoft Exchange Server 2010 では、Exchange ユニファイドメッセージング (UM) は、インストールして構成できる Exchange Server の役割の1つです。</span><span class="sxs-lookup"><span data-stu-id="b83b0-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="b83b0-106">Microsoft Exchange Server 2013 では、exchange UM は Exchange メールボックスサーバー上のサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="b83b0-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="b83b0-107">Lync Server 2013 エンタープライズ Voip 展開の場合、ユニファイドメッセージングでは、音声メッセージとメールメッセージが電話 (Outlook Voice Access) またはコンピューターから利用できる単一のストアに統合されます。</span><span class="sxs-lookup"><span data-stu-id="b83b0-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="b83b0-108">ユニファイドメッセージングと Lync Server 2013 は、エンタープライズ Voip のユーザーに対して、通話応答、Outlook Voice Access、自動応答サービスを提供するために共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="b83b0-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="b83b0-109">Microsoft Exchange Server 2013 のアーキテクチャの変更について詳しくは、「Microsoft Exchange Server 2013 のドキュメント」の「ボイスアーキテクチャの[http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730)変更」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b83b0-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="b83b0-110">オンプレミスの Exchange UM 展開でこれらの機能をサポートするには、次のいずれかを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b0-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="b83b0-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) または最新の service pack</span><span class="sxs-lookup"><span data-stu-id="b83b0-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="b83b0-112">Microsoft Exchange Server 2010 または最新の service pack</span><span class="sxs-lookup"><span data-stu-id="b83b0-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="b83b0-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b83b0-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b83b0-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="b83b0-114">In This Section</span></span>

  - [<span data-ttu-id="b83b0-115">統合ユニファイド メッセージングと Lync Server 2013 の機能</span><span class="sxs-lookup"><span data-stu-id="b83b0-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="b83b0-116">Lync Server 2013 の社内ユニファイド メッセージングのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="b83b0-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="b83b0-117">内部設置型ユニファイド メッセージングおよび Lync Server 2013 を統合するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="b83b0-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="b83b0-118">内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="b83b0-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

