---
title: 'Lync Server 2013: オンプレミスのユニファイドメッセージングのコンポーネントとトポロジ'
description: 'Lync Server 2013: オンプレミスのユニファイドメッセージングのコンポーネントとトポロジ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe2ca16ec9fbd39e9245fd366e1f7046dd16d42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576823"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="c182f-103">Lync Server 2013 でのオンプレミスのユニファイドメッセージングのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="c182f-103">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c182f-104">_**トピックの最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="c182f-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="c182f-105">このトピックでは、Exchange ユニファイドメッセージング (UM) 機能を Lync Server 2013 展開に提供するために必要な Microsoft Exchange Server 2013 コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c182f-105">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="c182f-106">また、オンプレミスの Exchange UM 統合に対してサポートされているトポロジについても説明します。</span><span class="sxs-lookup"><span data-stu-id="c182f-106">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="c182f-107">Exchange Server コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c182f-107">Exchange Server Components</span></span>

<span data-ttu-id="c182f-108">統合された [ユニファイドメッセージングと Lync Server 2013 の機能](lync-server-2013-features-of-integrated-unified-messaging.md) について説明されている exchange UM の機能とサービスを組織のエンタープライズ voip ユーザーに提供するには、ユーザーメールボックスをホストする Microsoft Exchange メールボックスサーバーとクライアントアクセスサーバーを展開し、電子メールとボイスメール用の単一の格納場所を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c182f-108">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="c182f-109">Exchange UM は、Exchange メールボックスサーバーおよびクライアントアクセスサーバー上のサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="c182f-109">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="c182f-110">Microsoft Exchange Server 2007 と Microsoft Exchange Server 2010 の Exchange UM コンポーネントの詳細については、「展開」のドキュメントの「 [社内 EXCHANGE um を展開して Lync Server 2013 ボイスメールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c182f-110">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="c182f-111">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="c182f-111">Supported Topologies</span></span>

<span data-ttu-id="c182f-112">Lync Server 2013 と Exchange ユニファイドメッセージング (UM) を同じフォレストまたは複数のフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c182f-112">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="c182f-113">複数のフォレストにまたがる展開の場合は、exchange UM フォレストごとに Exchange 統合の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c182f-113">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="c182f-114">さらに、Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼して各 Exchange UM フォレストを信頼するように、各 Microsoft Exchange フォレストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c182f-114">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="c182f-115">このフォレストの信頼に加えて、Lync Server 2013 フォレスト内のユーザーオブジェクトに対して、すべてのユーザーの Exchange UM 設定を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c182f-115">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="c182f-116">Lync Server 2013 は、Exchange UM 統合のために次のトポロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c182f-116">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="c182f-117">単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="c182f-117">Single forest</span></span>

  - <span data-ttu-id="c182f-118">単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。</span><span class="sxs-lookup"><span data-stu-id="c182f-118">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="c182f-119">Lync Server 2013、Microsoft Exchange、およびユーザーはすべて同じドメインに存在します。</span><span class="sxs-lookup"><span data-stu-id="c182f-119">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="c182f-120">複数のドメイン (つまり、1つ以上の子ドメインを持つルートドメイン)。</span><span class="sxs-lookup"><span data-stu-id="c182f-120">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="c182f-121">Lync Server 2013 と Microsoft Exchange サーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。</span><span class="sxs-lookup"><span data-stu-id="c182f-121">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="c182f-122">Exchange UM サーバーは、サポートする Lync Server 2013 プールとは異なるドメインに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c182f-122">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="c182f-123">複数のフォレスト (すなわち、リソース フォレスト)。</span><span class="sxs-lookup"><span data-stu-id="c182f-123">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="c182f-124">Lync Server 2013 は単一のフォレストに展開され、ユーザーは複数のフォレスト間で分散されます。</span><span class="sxs-lookup"><span data-stu-id="c182f-124">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="c182f-125">ユーザーの Exchange UM 属性は、Lync Server 2013 フォレストにレプリケートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c182f-125">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c182f-126">Exchange は複数のフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c182f-126">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="c182f-127">各 Exchange 組織は Exchange UM をユーザーに提供できます。または、Exchange UM を Lync Server 2013 と同じフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c182f-127">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

