---
title: 'Lync Server 2013: 既存のネットワークサイトを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="289f4-102">Lync Server 2013 で既存のネットワークサイトを削除する</span><span class="sxs-lookup"><span data-stu-id="289f4-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="289f4-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="289f4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="289f4-104">[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。</span><span class="sxs-lookup"><span data-stu-id="289f4-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="289f4-105">Lync Server 2013 コントロールパネルを使用して、サイトを構成し、それらを地域と関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="289f4-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="289f4-106">たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="289f4-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="289f4-107">サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。</span><span class="sxs-lookup"><span data-stu-id="289f4-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="289f4-108">Lync Server コントロールパネルからネットワークサイトの作成、変更、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="289f4-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="289f4-109">既存のネットワークサイトを削除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="289f4-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="289f4-110">ネットワークサイトの作成または変更の詳細については、「 [Lync Server 2013 でネットワークサイトを作成または変更する](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289f4-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="289f4-111">ネットワークサイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="289f4-111">To delete a network site</span></span>

1.  <span data-ttu-id="289f4-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="289f4-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="289f4-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="289f4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="289f4-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="289f4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="289f4-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="289f4-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="289f4-116">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="289f4-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="289f4-117">一度に複数のサイトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="289f4-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="289f4-118">この操作を行うには、ctrl キーを押しながら複数のサイトを選び、CTRL キーを押しながら選択します。</span><span class="sxs-lookup"><span data-stu-id="289f4-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="289f4-119">または、すべてのサイトを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="289f4-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="289f4-120">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="289f4-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="289f4-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="289f4-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="289f4-122">ネットワークサイトがネットワークサブネットに関連付けられている場合は、そのサイトを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="289f4-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="289f4-123">サブネットに関連付けられているサイトを削除しようとすると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="289f4-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="289f4-124">サイトがいずれかのサブネットに関連付けられているかどうかを確認するには、サイトをクリックし、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="289f4-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

