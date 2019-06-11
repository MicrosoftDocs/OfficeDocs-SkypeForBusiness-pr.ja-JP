---
title: 'Lync Server 2013: Lync Windows ストアアプリの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="70338-102">Lync Server 2013 の lync Windows ストアアプリの要件</span><span class="sxs-lookup"><span data-stu-id="70338-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70338-103">_**最終更新日:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="70338-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="70338-104">Lync Server のオンプレミス展開を使用する組織は、Lync Windows ストアアプリをサポートするために、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70338-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70338-105">Lync server 2010 の場合は、lync server 2010 の累積的な更新プログラムを実行し<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp</A>ます (2 月 2012 (使用可能)、またはその後のすべてのサーバーの場合)。</span><span class="sxs-lookup"><span data-stu-id="70338-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="70338-106">ユーザーが会議に参加できるようにするには、Lync Server 2010 の累積的な<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp</A>更新プログラム (2012 年10月、2737915) をサーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="70338-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="70338-107">サーバー上で自動検出、Lync Web App、Web Ticket の各サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="70338-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="70338-108">フロントエンドサーバーまたはフロントエンドプールで証明書の認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="70338-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="70338-109">(フロントエンドサーバーまたはフロントエンドプールでのユーザー登録プロセスは、レジストラーとも呼ばれます)。詳細については、「 [Lync Server 2013 でレジストラー構成の設定を作成する](lync-server-2013-create-registrar-configuration-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70338-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="70338-110">自動検出サービスの DNS エイリアス (CNAME) リソースレコードを公開します。</span><span class="sxs-lookup"><span data-stu-id="70338-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="70338-111">Lync server に発行された証明書の証明書失効リスト (CRL) 配布ポイント (CDP) が、LDAP リソースではなく HTTP リソースをポイントしていることを確認する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="70338-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="70338-112">ただし、クライアントコンピューターに最新の Windows 更新プログラムがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="70338-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="70338-113">Lync server 関連の HTTP トラフィックを許可するように、エンタープライズの HTTP プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="70338-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="70338-114">必要に応じて、自動検出、Lync Web App、WebTicket の各サービスの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="70338-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="70338-115">クライアントで、Windows 8.1 と最新バージョンの Lync Windows ストアアプリをインストールして、複数のドメインを使用する場合に一般的に発生するサインインの問題を解決します (たとえば、SIP URI が**userA@domainZ.com** 、エッジサーバーが**sip.domainX.com**されている場合)。</span><span class="sxs-lookup"><span data-stu-id="70338-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="70338-116">組織が Lync Online または Office 365 をサブスクライブしていて、独自のドメイン名を使用している場合は、Lync サーバーの自動検出用にネットワークをセットアップするための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70338-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="70338-117">ネットワーク構成要件は、Lync Windows ストアアプリとモバイルデバイス上の Lync と同じです。</span><span class="sxs-lookup"><span data-stu-id="70338-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="70338-118">Office 365 wiki の記事「Lync モバイルデバイスをセットアップする」の「ネットワークのセットアップ」の指示に従って[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)ください。</span><span class="sxs-lookup"><span data-stu-id="70338-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="70338-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="70338-119">See Also</span></span>


[<span data-ttu-id="70338-120">Lync Server 2013 での Lync Windows ストアアプリの展開</span><span class="sxs-lookup"><span data-stu-id="70338-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

