---
title: 'Lync Server 2013: 許可されている外部ドメインのサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51190fd787fde408913b71d4a5ce6f1d002a6d28
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="c18b9-102">Lync Server 2013 で許可された外部ドメインのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="c18b9-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c18b9-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c18b9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c18b9-104">フェデレーションパートナーのサポートを構成した場合は、組織とフェデレーションできる特定のドメインを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c18b9-104">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="c18b9-105">1つ以上の特定の外部ドメインを許可されたフェデレーションドメインとして構成します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-105">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="c18b9-106">これを行うには、許可されるドメインの一覧に各ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-106">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="c18b9-107">組織に対してパートナーの検出が有効になっている場合でも、ドメインが1000以上のユーザーと通信する必要があるか、または1秒あたり20件を超えるメッセージを送信する必要があるフェデレーションパートナーである場合に、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-107">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="c18b9-108">パートナー検出が組織で有効になっていない場合は、許可されたドメインリストに追加した外部ドメインのユーザーのみが、組織内のユーザーとの IM および会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="c18b9-108">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="c18b9-109">フェデレーションドメインのアクセスを、フェデレーションパートナーのアクセスエッジサービスを実行している特定のサーバーに制限する場合は、許可されたドメインの一覧で、各ドメインのアクセスエッジサービスを実行するサーバーのドメイン名を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c18b9-109">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c18b9-110">この手順では、特定のドメインのサポートを構成する方法について説明しますが、フェデレーションユーザーのサポートを実装するには、組織のフェデレーションユーザーのサポートを有効にし、ポリシーを構成して適用して、どのユーザーが操作できるかを制御する必要もあります。フェデレーションユーザーと共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c18b9-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="c18b9-111">フェデレーションユーザーのサポートの有効化の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスの有効化または無効化</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18b9-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="c18b9-112">フェデレーションを制御するポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18b9-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="c18b9-113">許可されたドメインの一覧に外部ドメインを追加するには</span><span class="sxs-lookup"><span data-stu-id="c18b9-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="c18b9-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c18b9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c18b9-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c18b9-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c18b9-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18b9-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c18b9-117">左側のナビゲーションバーで [**外部ユーザーアクセス**] をクリックし、[**フェデレーションドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c18b9-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="c18b9-118">[**フェデレーションドメイン**] ページで、[**新規**] をクリックし、[**許可さ**れたドメイン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c18b9-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="c18b9-119">[**新規フェデレーション ドメイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="c18b9-120">[**ドメイン名 (または FQDN)**] で、フェデレーションパートナードメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c18b9-121">この名前は一意である必要があり、アクセスエッジサービスを実行しているこのサーバーで許可されているドメインとして既に存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="c18b9-121">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="c18b9-122">名前の長さは、最大 256 文字です。</span><span class="sxs-lookup"><span data-stu-id="c18b9-122">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="c18b9-p105">フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、<STRONG>contoso.com</STRONG> と入力すると、検索によりドメイン <STRONG>it.contoso.com</STRONG> も戻されます。</span><span class="sxs-lookup"><span data-stu-id="c18b9-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="c18b9-125">フェデレーション パートナー ドメインを同時に禁止および許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="c18b9-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="c18b9-126">Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="c18b9-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="c18b9-127">アクセスエッジサービスを実行している特定のサーバーのユーザーに対して、このフェデレーションドメインのアクセスを制限する場合は、アクセスエッジサービス **(fqdn)** で、アクセスエッジサービスを実行しているフェデレーションドメインのサーバーの fqdn を入力します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="c18b9-128">追加情報を提供する場合は、[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="c18b9-129">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c18b9-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="c18b9-130">許可するフェデレーションパートナードメインごとに、手順 4 ~ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c18b9-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="c18b9-131">フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18b9-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="c18b9-132">詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18b9-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="c18b9-133">また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18b9-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="c18b9-134">詳細については、「 [Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18b9-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

