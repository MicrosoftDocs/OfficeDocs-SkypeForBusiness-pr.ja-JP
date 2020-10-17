---
title: 'Lync Server 2013: ディレクターを使用するように自動クライアント Sign-In を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522964"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="c012f-102">Lync Server 2013 でディレクターを使用するようにクライアントの自動 Sign-In を構成する</span><span class="sxs-lookup"><span data-stu-id="c012f-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c012f-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c012f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c012f-104">Lync Server 2013、ディレクター、またはディレクターのプールを展開する場合、ベストプラクティスとして、自動クライアント Sign-In を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c012f-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="c012f-105">自動クライアントサインイン用に DNS サーバーを構成する方法の詳細については、「計画」のドキュメントの「 [Lync Server 2013 での自動クライアントサインインの dns 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c012f-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="c012f-106">自動クライアント サインインを既に展開している場合は、次のセクションを参照してディレクターに構成してください。</span><span class="sxs-lookup"><span data-stu-id="c012f-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="c012f-107">単一のディレクター インスタンス</span><span class="sxs-lookup"><span data-stu-id="c012f-107">Single Director Instance</span></span>

<span data-ttu-id="c012f-108">既に自動クライアント Sign-In を展開していて、フロントエンドサーバーまたはフロントエンドプールを指している場合は、そのディレクターをポイントするように DNS SRV レコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c012f-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="c012f-109">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="c012f-109">Director Pool</span></span>

<span data-ttu-id="c012f-110">クライアントの自動 Sign-In が既に展開されていて、フロントエンドサーバーまたはフロントエンドプールを指している場合は、そのディレクタープールをポイントするように DNS SRV レコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c012f-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

