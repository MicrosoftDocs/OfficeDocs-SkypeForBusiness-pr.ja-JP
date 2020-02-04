---
title: 'Lync Server 2013: 禁止された外部ドメイン向けサポートの構成'
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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="8338a-102">Lync Server 2013 での禁止された外部ドメイン向けサポートの構成</span><span class="sxs-lookup"><span data-stu-id="8338a-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8338a-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8338a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8338a-104">フェデレーションパートナーのサポートを構成している場合は、どのドメインを組織とのフェデレーションからブロックするかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8338a-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="8338a-105">ブロックされたドメインの一覧はブロックリスト (許可されていない明示的なエントリの一覧) として機能し、このオプションを有効にしている場合はフェデレーションドメインの検出に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8338a-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="8338a-106">詳細については、「 [Lync Server 2013 でフェデレーションパートナーの検出を有効または無効](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8338a-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="8338a-107">1つ以上の外部ドメインをブロックして組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="8338a-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="8338a-108">そのためには、ブロックされたドメインの一覧にドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="8338a-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="8338a-109">ブロックされたドメインの一覧に外部ドメインを追加するには</span><span class="sxs-lookup"><span data-stu-id="8338a-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="8338a-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8338a-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8338a-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8338a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8338a-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8338a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8338a-113">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8338a-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="8338a-114">[**フェデレーションドメイン**] をクリックし、[**新規作成**] をクリックして、[**禁止ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8338a-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="8338a-115">**新しいフェデレーションドメイン**で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8338a-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="8338a-116">[ **Domain name (または FQDN)**] に、ブロックするフェデレーションパートナードメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8338a-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8338a-117">名前の長さは、256文字以下にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8338a-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="8338a-118">フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8338a-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="8338a-119">たとえば、 <STRONG>contoso.com</STRONG>と入力すると、検索によってドメイン<STRONG>it.contoso.com</STRONG>も返されます。</span><span class="sxs-lookup"><span data-stu-id="8338a-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="8338a-120">フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="8338a-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="8338a-121">Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="8338a-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="8338a-122">省略[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8338a-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="8338a-123">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8338a-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="8338a-124">ブロックするフェデレーションパートナーごとに、手順 4 ~ 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8338a-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="8338a-125">フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8338a-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="8338a-126">詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8338a-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="8338a-127">さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8338a-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="8338a-128">詳細については、「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8338a-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

