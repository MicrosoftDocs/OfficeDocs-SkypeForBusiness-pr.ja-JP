---
title: 'Lync Server 2013: ディレクターを使用するための自動クライアントサインインの構成'
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
ms.openlocfilehash: 634bfad77e61846528b6013b82921dfdc366f372
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="4bb0d-102">Lync Server 2013 でディレクターを使用するように自動クライアントサインインを構成する</span><span class="sxs-lookup"><span data-stu-id="4bb0d-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bb0d-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4bb0d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4bb0d-104">Lync Server 2013、ディレクター、またはディレクターのプールを展開する場合、ベストプラクティスとして、自動クライアントサインインを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bb0d-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="4bb0d-105">自動クライアントサインイン用に DNS サーバーを構成する方法の詳細については、「計画」のドキュメントの「 [Lync Server 2013 での自動クライアントサインインの dns 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bb0d-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="4bb0d-106">自動クライアント サインインを既に展開している場合は、次のセクションを参照してディレクターに構成してください。</span><span class="sxs-lookup"><span data-stu-id="4bb0d-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="4bb0d-107">単一のディレクター インスタンス</span><span class="sxs-lookup"><span data-stu-id="4bb0d-107">Single Director Instance</span></span>

<span data-ttu-id="4bb0d-108">自動クライアントサインインを既に展開していて、フロントエンドサーバーまたはフロントエンドプールをポイントしている場合は、ディレクターをポイントするように DNS SRV レコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb0d-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="4bb0d-109">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="4bb0d-109">Director Pool</span></span>

<span data-ttu-id="4bb0d-110">自動クライアントサインインを既に展開していて、フロントエンドサーバーまたはフロントエンドプールを指している場合は、ディレクタープールを指すように DNS SRV レコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb0d-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

