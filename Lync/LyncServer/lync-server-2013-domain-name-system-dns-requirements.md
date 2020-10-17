---
title: 'Lync Server 2013: ドメインネームシステム (DNS) の要件'
description: 'Lync Server 2013: ドメインネームシステム (DNS) の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f84868d4929cc410cddbb6c9ad2019a12841e80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553203"
---
# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="6c8a4-103">Lync Server 2013 のドメインネームシステム (DNS) の要件</span><span class="sxs-lookup"><span data-stu-id="6c8a4-103">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c8a4-104">_**トピックの最終更新日:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="6c8a4-104">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="6c8a4-105">Lync Server を展開するには、クライアントとサーバーの検出を有効にするドメインネームシステム (DNS) レコードを作成する必要があります。また、必要に応じて、組織でサポートする必要がある場合に、自動クライアントサインインをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-105">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="6c8a4-106">Lync Server は、次の方法で DNS を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-106">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="6c8a4-107">サーバー間通信用の内部のサーバーまたはプールを検出する。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-107">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="6c8a4-108">クライアントが、さまざまな SIP トランザクションに使用されるフロントエンドプールまたは Standard Edition サーバーを検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-108">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="6c8a4-109">ログオンしていない統合コミュニケーション (UC) デバイスによる、デバイス更新 Web サービスを実行しているフロントエンドプールまたは Standard Edition サーバーの検出、更新プログラムの取得、およびログの送信を許可します。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-109">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="6c8a4-110">外部サーバーとクライアントが、インスタントメッセージング (IM) または会議用のエッジサーバーまたは HTTP リバースプロキシに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-110">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="6c8a4-111">外部 UC デバイスがエッジサーバーまたは HTTP リバースプロキシ経由でデバイス更新 Web サービスに接続できるようにするには、更新を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-111">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="6c8a4-112">モバイル クライアントによる、ユーザーがデバイスの設定で URL を手動で入力する必要がない、Web サービス リソースの自動検出を許可する。</span><span class="sxs-lookup"><span data-stu-id="6c8a4-112">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c8a4-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6c8a4-113">In This Section</span></span>

  - [<span data-ttu-id="6c8a4-114">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="6c8a4-114">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="6c8a4-115">Lync Server 2013 のフロントエンドプールの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6c8a4-115">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="6c8a4-116">Lync Server 2013 の Standard Edition サーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6c8a4-116">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="6c8a4-117">Lync Server 2013 の簡易 Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6c8a4-117">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="6c8a4-118">Lync Server 2013 での自動クライアントサインインの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6c8a4-118">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="6c8a4-119">Lync Server 2013 を使用したモビリティの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6c8a4-119">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="6c8a4-120">Lync Server 2013 での DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6c8a4-120">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

