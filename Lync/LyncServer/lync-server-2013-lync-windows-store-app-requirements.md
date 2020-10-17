---
title: 'Lync Server 2013: Lync Windows ストアアプリの要件'
description: 'Lync Server 2013: Lync Windows ストアアプリの要件。'
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
ms.openlocfilehash: 17e8705a55625bcf0ad099ead1000a82c994d867
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566503"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="b22e2-103">Lync Server 2013 の lync Windows ストアアプリの要件</span><span class="sxs-lookup"><span data-stu-id="b22e2-103">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b22e2-104">_**トピックの最終更新日:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="b22e2-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="b22e2-105">社内で Lync Server を展開している組織は、Lync Windows ストアアプリをサポートするために以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b22e2-105">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b22e2-106">Lync Server 2010 の場合は、Lync Server 2010 の累積的な更新プログラム (2 月 1 2012 日 ( <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp kbid = 2670352</A>) 以降) を実行します。</span><span class="sxs-lookup"><span data-stu-id="b22e2-106">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="b22e2-107">ユーザーが会議に参加できるようにするには、サーバー上で Lync Server 2010 の累積的な更新プログラム (10 月 2012) を実行します ( <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp kbid = 2737915</A>)。</span><span class="sxs-lookup"><span data-stu-id="b22e2-107">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="b22e2-108">サーバー上の自動検出、Lync Web App、および Web チケットサービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b22e2-108">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="b22e2-109">フロントエンドサーバーまたはフロントエンドプールで証明書認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b22e2-109">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="b22e2-110">(フロントエンドサーバーまたはフロントエンドプールでのユーザー登録プロセスは、多くの場合レジストラーと呼ばれます)。詳細については、「 [Create レジストラー configuration settings In Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b22e2-110">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="b22e2-111">自動検出サービスの DNS エイリアス (CNAME) リソースレコードを公開します。</span><span class="sxs-lookup"><span data-stu-id="b22e2-111">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="b22e2-112">Lync server に発行された証明書の証明書失効リスト (CRL) 配布ポイント (CDP) が、LDAP リソースではなく HTTP リソースを指していることを確認する必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b22e2-112">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="b22e2-113">ただし、クライアントコンピューターに最新の Windows 更新プログラムがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b22e2-113">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="b22e2-114">Lync server 関連の HTTP トラフィックを許可するように、エンタープライズで HTTP プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="b22e2-114">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="b22e2-115">必要に応じて、自動検出、Lync Web App、および WebTicket サービスの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="b22e2-115">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="b22e2-116">クライアントで、Windows 8.1 と Lync Windows ストアアプリの最新バージョンをインストールして、複数のドメインを使用するときに一般的に発生するサインインの問題を修正します (たとえば、SIP URI が **userA@domainZ.com** 、エッジサーバーが **sip.domainX.com**)。</span><span class="sxs-lookup"><span data-stu-id="b22e2-116">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="b22e2-117">組織が Lync Online または Microsoft 365 をサブスクライブしていて、自分のドメイン名を使用している場合は、Lync サーバーの自動検出のためにネットワークをセットアップするための特別な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b22e2-117">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="b22e2-118">ネットワーク構成の要件は、モバイルデバイスの Lync Windows ストアアプリと Lync で同じです。</span><span class="sxs-lookup"><span data-stu-id="b22e2-118">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b22e2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b22e2-119">See Also</span></span>


[<span data-ttu-id="b22e2-120">Lync Server 2013 での Lync Windows ストアアプリの展開</span><span class="sxs-lookup"><span data-stu-id="b22e2-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
