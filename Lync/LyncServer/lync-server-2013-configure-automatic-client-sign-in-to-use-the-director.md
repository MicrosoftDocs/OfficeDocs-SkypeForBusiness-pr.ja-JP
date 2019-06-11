---
title: 'Lync Server 2013: ディレクターを使った自動クライアント サインインの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e885080879b2b7ce3cf87557b21822fe9cd26f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="c11bd-102">Lync Server 2013 でのディレクターを使った自動クライアント サインインの構成</span><span class="sxs-lookup"><span data-stu-id="c11bd-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c11bd-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c11bd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c11bd-104">Lync Server 2013、ディレクター、またはディレクタープールを展開する場合は、ベストプラクティスとして、自動クライアントサインインを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c11bd-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="c11bd-105">自動クライアントサインイン用に DNS サーバーを構成する方法について詳しくは、「計画ドキュメントの「 [Lync Server 2013 での自動クライアントサインインの dns 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c11bd-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="c11bd-106">既に自動クライアントサインインを展開している場合は、次のセクションを参照してディレクターで構成してください。</span><span class="sxs-lookup"><span data-stu-id="c11bd-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="c11bd-107">単一のディレクターインスタンス</span><span class="sxs-lookup"><span data-stu-id="c11bd-107">Single Director Instance</span></span>

<span data-ttu-id="c11bd-108">既にクライアントの自動サインインが導入されていて、フロントエンドサーバーまたはフロントエンドプールをポイントしている場合は、そのディレクターをポイントするように DNS SRV レコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11bd-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="c11bd-109">ディレクタープール</span><span class="sxs-lookup"><span data-stu-id="c11bd-109">Director Pool</span></span>

<span data-ttu-id="c11bd-110">既にクライアントの自動サインインが導入されていて、フロントエンドサーバーまたはフロントエンドプールを指している場合は、そのディレクタープールをポイントするように DNS SRV レコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11bd-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

