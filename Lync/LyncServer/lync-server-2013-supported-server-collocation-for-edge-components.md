---
title: 'Lync Server 2013: エッジ コンポーネントのサポートされるサーバーの併置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ad78cc1060c64181a75acefa21e64809e0d7b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="1b00b-102">Lync Server 2013 での、エッジ コンポーネントのサポートされるサーバーの併置</span><span class="sxs-lookup"><span data-stu-id="1b00b-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b00b-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1b00b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1b00b-104">アクセスエッジサービス、Web 会議エッジサービス、A/V Edge サービス、および XMPP プロキシサービスは、エッジサーバーに併置されています。</span><span class="sxs-lookup"><span data-stu-id="1b00b-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="1b00b-105">次のサーバーは、外部ユーザーアクセスに必要な機能を提供し、専用サーバーとして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b00b-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="1b00b-106">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="1b00b-106">Edge Server</span></span>

  - <span data-ttu-id="1b00b-107">監督 (オプション)</span><span class="sxs-lookup"><span data-stu-id="1b00b-107">Director (Optional)</span></span>

  - <span data-ttu-id="1b00b-108">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="1b00b-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1b00b-109">リバースプロキシは、Lync Server 2013 のみを提供するための専用である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1b00b-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="1b00b-110">たとえば、Lync Server Web サービスを公開するためのサービスを提供し、Lync Server にまったく関係のない別の Web サイトに公開された Web サイトを同時に提供することができます。</span><span class="sxs-lookup"><span data-stu-id="1b00b-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="1b00b-111">他のサービスをサポートするために既に境界ネットワーク内に逆プロキシサーバーがある場合は、Lync Server 2013 で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1b00b-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

