---
title: 'Lync Server 2013: ブロックされた外部ドメインのサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1b7b1da08a8c573b782474d7f2deb4ea9358a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="79568-102">Lync Server 2013 で禁止された外部ドメインのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="79568-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79568-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="79568-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="79568-104">フェデレーション パートナーに対するサポートが構成されている場合、組織とのフェデレーションを禁止するドメインを管理できます。</span><span class="sxs-lookup"><span data-stu-id="79568-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="79568-105">このオプションが有効な場合は、禁止されているドメインの一覧は禁止リスト (許可されていない明示的なエントリの一覧) として機能し、フェデレーション ドメインの検出時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="79568-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="79568-106">詳細については、「 [Lync Server 2013 でのフェデレーションパートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79568-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="79568-p102">1 つまたは複数の外部ドメインの組織への接続を禁止します。この構成を実行するには、ドメインを禁止ドメインの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="79568-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="79568-109">外部ドメインを禁止ドメインの一覧に追加するには</span><span class="sxs-lookup"><span data-stu-id="79568-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="79568-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="79568-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79568-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79568-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79568-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79568-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79568-113">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79568-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="79568-114">[**フェデレーション ドメイン**] をクリックし、[**新規**] をクリックし、[**禁止ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79568-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="79568-115">[**新規フェデレーション ドメイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="79568-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="79568-116">[**ドメイン名 (または FQDN)**] で、禁止するフェデレーション パートナー ドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="79568-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="79568-117">名前の長さは、最大 256 文字です。</span><span class="sxs-lookup"><span data-stu-id="79568-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="79568-p104">フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、<STRONG>contoso.com</STRONG> と入力すると、検索によりドメイン <STRONG>it.contoso.com</STRONG> も戻されます。</span><span class="sxs-lookup"><span data-stu-id="79568-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="79568-120">フェデレーション パートナー ドメインを同時に禁止および許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="79568-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="79568-121">Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="79568-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="79568-122">(オプション) [**コメント**] で、この構成について他のシステム管理者と共有する必要のある情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="79568-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="79568-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79568-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="79568-124">禁止するフェデレーション パートナーごとに、ステップ 4 ～ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="79568-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="79568-125">フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79568-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="79568-126">詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79568-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="79568-127">また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79568-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="79568-128">詳細については、「 [Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79568-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

