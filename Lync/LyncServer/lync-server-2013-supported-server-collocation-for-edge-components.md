---
title: 'Lync Server 2013: エッジコンポーネントのサポートされるサーバーの併置位置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e52d1c630bba8c93193c2e309d4d3299f45a6388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="61f16-102">Lync Server 2013 のエッジコンポーネントに対してサポートされているサーバーの併置</span><span class="sxs-lookup"><span data-stu-id="61f16-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61f16-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="61f16-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="61f16-104">アクセスエッジサービス、Web 会議エッジサービス、音声ビデオエッジサービス、および XMPP プロキシサービスがエッジサーバーに併置されます。</span><span class="sxs-lookup"><span data-stu-id="61f16-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="61f16-105">次のサーバーは、外部ユーザー アクセスに必要な機能を提供し、専用サーバーとして展開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="61f16-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="61f16-106">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="61f16-106">Edge Server</span></span>

  - <span data-ttu-id="61f16-107">ディレクター (オプション)</span><span class="sxs-lookup"><span data-stu-id="61f16-107">Director (Optional)</span></span>

  - <span data-ttu-id="61f16-108">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="61f16-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61f16-109">リバースプロキシは、Lync Server 2013 のサービスのみを提供するための専用である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="61f16-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="61f16-110">たとえば、lync server Web サービスを公開するためのサービスを提供し、Lync Server にまったく影響を与えない別の Web サイトに対して同時に公開された Web サイトを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="61f16-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="61f16-111">他のサービスをサポートするために、既に境界ネットワークにリバースプロキシサーバーがある場合は、それを Lync Server 2013 に使用できます。</span><span class="sxs-lookup"><span data-stu-id="61f16-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

