---
title: 'Lync Server 2013: オンプレミスのユニファイドメッセージングのコンポーネントとトポロジ'
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
ms.openlocfilehash: 94a22348ca5b0f17415edf0a4f259d5c58d473a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="41a33-102">Lync Server 2013 でのオンプレミスのユニファイドメッセージングのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="41a33-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a33-103">_**トピックの最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="41a33-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="41a33-104">このトピックでは、Exchange ユニファイドメッセージング (UM) 機能を Lync Server 2013 展開に提供するために必要な Microsoft Exchange Server 2013 コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="41a33-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="41a33-105">また、オンプレミスの Exchange UM 統合に対してサポートされているトポロジについても説明します。</span><span class="sxs-lookup"><span data-stu-id="41a33-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="41a33-106">Exchange Server コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41a33-106">Exchange Server Components</span></span>

<span data-ttu-id="41a33-107">統合された[ユニファイドメッセージングと Lync Server 2013 の機能](lync-server-2013-features-of-integrated-unified-messaging.md)について説明されている exchange UM の機能とサービスを組織のエンタープライズ voip ユーザーに提供するには、ユーザーメールボックスをホストする Microsoft Exchange メールボックスサーバーとクライアントアクセスサーバーを展開し、電子メールとボイスメール用の単一の格納場所を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a33-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="41a33-108">Exchange UM は、Exchange メールボックスサーバーおよびクライアントアクセスサーバー上のサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="41a33-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="41a33-109">Microsoft Exchange Server 2007 と Microsoft Exchange Server 2010 の Exchange UM コンポーネントの詳細については、「展開」のドキュメントの「[社内 EXCHANGE um を展開して Lync Server 2013 ボイスメールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41a33-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="41a33-110">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="41a33-110">Supported Topologies</span></span>

<span data-ttu-id="41a33-111">Lync Server 2013 と Exchange ユニファイドメッセージング (UM) を同じフォレストまたは複数のフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="41a33-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="41a33-112">複数のフォレストにまたがる展開の場合は、exchange UM フォレストごとに Exchange 統合の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a33-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="41a33-113">さらに、Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼して各 Exchange UM フォレストを信頼するように、各 Microsoft Exchange フォレストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a33-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="41a33-114">このフォレストの信頼に加えて、Lync Server 2013 フォレスト内のユーザーオブジェクトに対して、すべてのユーザーの Exchange UM 設定を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a33-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="41a33-115">Lync Server 2013 は、Exchange UM 統合のために次のトポロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="41a33-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="41a33-116">単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="41a33-116">Single forest</span></span>

  - <span data-ttu-id="41a33-117">単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。</span><span class="sxs-lookup"><span data-stu-id="41a33-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="41a33-118">Lync Server 2013、Microsoft Exchange、およびユーザーはすべて同じドメインに存在します。</span><span class="sxs-lookup"><span data-stu-id="41a33-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="41a33-119">複数のドメイン (つまり、1つ以上の子ドメインを持つルートドメイン)。</span><span class="sxs-lookup"><span data-stu-id="41a33-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="41a33-120">Lync Server 2013 と Microsoft Exchange サーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。</span><span class="sxs-lookup"><span data-stu-id="41a33-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="41a33-121">Exchange UM サーバーは、サポートする Lync Server 2013 プールとは異なるドメインに展開できます。</span><span class="sxs-lookup"><span data-stu-id="41a33-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="41a33-122">複数のフォレスト (すなわち、リソース フォレスト)。</span><span class="sxs-lookup"><span data-stu-id="41a33-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="41a33-123">Lync Server 2013 は単一のフォレストに展開され、ユーザーは複数のフォレスト間で分散されます。</span><span class="sxs-lookup"><span data-stu-id="41a33-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="41a33-124">ユーザーの Exchange UM 属性は、Lync Server 2013 フォレストにレプリケートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41a33-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41a33-125">Exchange は複数のフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="41a33-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="41a33-126">各 Exchange 組織は Exchange UM をユーザーに提供できます。または、Exchange UM を Lync Server 2013 と同じフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="41a33-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

