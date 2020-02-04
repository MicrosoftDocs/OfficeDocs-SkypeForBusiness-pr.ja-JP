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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="aec90-102">Lync Server 2013 での DNS インフラストラクチャのサポート</span><span class="sxs-lookup"><span data-stu-id="aec90-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aec90-103">_**最終更新日:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="aec90-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="aec90-104">Lync Server 2013 には、ドメインネームシステム (DNS) が必要です。次のような方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="aec90-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="aec90-105">内部サーバーまたはサーバー間通信のプールを検出します。</span><span class="sxs-lookup"><span data-stu-id="aec90-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="aec90-106">クライアントが、さまざまな SIP トランザクションに使用されるフロントエンドプールまたは Standard Edition サーバーを検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aec90-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="aec90-107">会議の単純な Url を会議をホストしているサーバーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="aec90-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="aec90-108">外部サーバーとクライアントが、エッジサーバーまたはインスタントメッセージング (IM) または会議の HTTP リバースプロキシに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aec90-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="aec90-109">ログインしていないユニファイドコミュニケーション (UC) デバイスを有効にして、デバイス更新 Web サービスが実行されているフロントエンドプールまたは Standard Edition server を検出し、更新プログラムを入手してログを送信します。</span><span class="sxs-lookup"><span data-stu-id="aec90-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="aec90-110">モバイルクライアントがデバイス設定で Url を手動で入力する必要なく、Web サービスのリソースを自動的に検出できるようにする。</span><span class="sxs-lookup"><span data-stu-id="aec90-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="aec90-111">DNS の負荷分散の場合。</span><span class="sxs-lookup"><span data-stu-id="aec90-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aec90-112">Lync Server 2013 は、国際化ドメイン名 (Idn) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aec90-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aec90-113">指定する名前が、サーバーで構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec90-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="aec90-114">既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="aec90-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="aec90-115">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="aec90-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="aec90-116">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec90-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="aec90-117">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="aec90-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="aec90-118">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="aec90-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="aec90-119">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="aec90-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

