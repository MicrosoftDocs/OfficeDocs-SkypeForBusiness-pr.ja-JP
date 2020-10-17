---
title: 'Lync Server 2013: DNS インフラストラクチャのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed40fb498b93f0c6f3b1a8d32c7642f7714998ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528944"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="1ddec-102">Lync Server 2013 での DNS インフラストラクチャのサポート</span><span class="sxs-lookup"><span data-stu-id="1ddec-102">DNS infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ddec-103">_**トピックの最終更新日:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="1ddec-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="1ddec-104">Lync Server 2013 にはドメインネームシステム (DNS) が必要であり、次の方法で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ddec-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="1ddec-105">サーバー間通信用の内部のサーバーまたはプールを検出する。</span><span class="sxs-lookup"><span data-stu-id="1ddec-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="1ddec-106">クライアントによる、さまざまな SIP トランザクションに使用されるフロントエンド プールまたは Standard Edition サーバーの検出を有効にする。</span><span class="sxs-lookup"><span data-stu-id="1ddec-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="1ddec-107">会議用の簡易 URL をこれらの会議をホストするサーバーに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="1ddec-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="1ddec-108">外部のサーバーおよびクライアントによる、インスタント メッセージング (IM) または会議用のエッジ サーバーまたは HTTP リバース プロキシへの接続を有効にする。</span><span class="sxs-lookup"><span data-stu-id="1ddec-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="1ddec-109">ログインされていない統合コミュニケーション (UC) デバイスによる、デバイス更新 Web サービスを実行しているフロントエンド プールまたは Standard Edition サーバーの検出、更新プログラムの取得、およびログの送信を有効にする。</span><span class="sxs-lookup"><span data-stu-id="1ddec-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="1ddec-110">モバイル クライアントによる、ユーザーがデバイスの設定で URL を手動で入力する必要がない、Web サービス リソースの自動検出を有効にする。</span><span class="sxs-lookup"><span data-stu-id="1ddec-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="1ddec-111">DNS 負荷分散のため。</span><span class="sxs-lookup"><span data-stu-id="1ddec-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ddec-112">Lync Server 2013 は、国際化ドメイン名 (Idn) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1ddec-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ddec-113">指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddec-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="1ddec-114">既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="1ddec-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1ddec-115">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ddec-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="1ddec-116">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddec-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1ddec-117">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="1ddec-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="1ddec-118">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1ddec-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1ddec-119">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="1ddec-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

