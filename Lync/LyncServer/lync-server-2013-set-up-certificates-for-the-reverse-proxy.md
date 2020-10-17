---
title: 'Lync Server 2013: リバースプロキシの証明書の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e5bf87e02dbcdebeb8b1bb5a7a360c2c91ab00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509874"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2f264-102">Lync Server 2013 でリバースプロキシの証明書をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2f264-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f264-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2f264-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2f264-104">各リバースプロキシサーバーは、リスニングサービスで使用する web サーバー証明書を必要とします。</span><span class="sxs-lookup"><span data-stu-id="2f264-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="2f264-105">Web サーバー証明書は、パブリック証明機関 (CA) によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f264-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="2f264-106">この他の証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f264-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="2f264-107">リバースプロキシの Web サービス証明書を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f264-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="2f264-108">Web サービス証明書の設定を含めて、リバースプロキシを既にセットアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f264-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="2f264-109">エッジサーバーの展開を開始する前に実行していない場合は、「 [Lync Server 2013 のリバースプロキシサーバーの設定](lync-server-2013-setting-up-reverse-proxy-servers.md) 」の手順を使用して要求を作成し、web サービス証明書をインストールしてから、各 web 公開ルールを作成して、証明書を使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="2f264-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

