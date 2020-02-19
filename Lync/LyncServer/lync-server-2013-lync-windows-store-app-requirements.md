---
title: 'Lync Server 2013: Lync Windows ストアアプリの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84e4c7c9f4fb07d737b4f384faa5559a69c2392c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="958e6-102">Lync Server 2013 の lync Windows ストアアプリの要件</span><span class="sxs-lookup"><span data-stu-id="958e6-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="958e6-103">_**トピックの最終更新日:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="958e6-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="958e6-104">社内で Lync Server を展開している組織は、Lync Windows ストアアプリをサポートするために以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="958e6-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="958e6-105">Lync server 2010 の場合は、lync server 2010 の累積的な更新プログラム (2 月 1 <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp2012 日 (kbid = 2670352</A>) 以降) を実行します。</span><span class="sxs-lookup"><span data-stu-id="958e6-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="958e6-106">ユーザーが会議に参加できるようにするには、サーバー上で Lync Server 2010 の累積的<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp</A>な更新プログラム (10 月 2012) を実行します (kbid = 2737915)。</span><span class="sxs-lookup"><span data-stu-id="958e6-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="958e6-107">サーバー上の自動検出、Lync Web App、および Web チケットサービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="958e6-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="958e6-108">フロントエンドサーバーまたはフロントエンドプールで証明書認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="958e6-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="958e6-109">(フロントエンドサーバーまたはフロントエンドプールでのユーザー登録プロセスは、多くの場合レジストラーと呼ばれます)。詳細については、「 [Create レジストラー configuration settings In Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958e6-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="958e6-110">自動検出サービスの DNS エイリアス (CNAME) リソースレコードを公開します。</span><span class="sxs-lookup"><span data-stu-id="958e6-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="958e6-111">Lync server に発行された証明書の証明書失効リスト (CRL) 配布ポイント (CDP) が、LDAP リソースではなく HTTP リソースを指していることを確認する必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="958e6-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="958e6-112">ただし、クライアントコンピューターに最新の Windows 更新プログラムがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="958e6-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="958e6-113">Lync server 関連の HTTP トラフィックを許可するように、エンタープライズで HTTP プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="958e6-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="958e6-114">必要に応じて、自動検出、Lync Web App、および WebTicket サービスの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="958e6-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="958e6-115">クライアントで、Windows 8.1 と Lync Windows ストアアプリの最新バージョンをインストールして、複数のドメインを使用するときに一般的に発生するサインインの問題を修正します (たとえば、SIP URI が**userA@domainZ.com** 、エッジサーバーが**sip.domainX.com**)。</span><span class="sxs-lookup"><span data-stu-id="958e6-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="958e6-116">組織が Lync Online または Office 365 をサブスクライブしていて、独自のドメイン名を使用している場合は、Lync サーバーの自動検出のためにネットワークをセットアップするための特別な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958e6-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="958e6-117">ネットワーク構成の要件は、モバイルデバイスの Lync Windows ストアアプリと Lync で同じです。</span><span class="sxs-lookup"><span data-stu-id="958e6-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="958e6-118">「Office 365 wiki」の「ネットワークをセットアップする」の手順に従い[https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822)ます (「Lync モバイルデバイスをセットアップする」の記事を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="958e6-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="958e6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="958e6-119">See Also</span></span>


[<span data-ttu-id="958e6-120">Lync Server 2013 での Lync Windows ストアアプリの展開</span><span class="sxs-lookup"><span data-stu-id="958e6-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

