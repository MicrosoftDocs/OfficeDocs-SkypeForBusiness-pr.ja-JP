---
title: 'Lync Server 2013: 既存のネットワークサイトの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d37e08eddac5b6166043a45d7e669c7e0ecd71a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525384"
---
# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="27583-102">Lync Server 2013 での既存のネットワークサイトの削除</span><span class="sxs-lookup"><span data-stu-id="27583-102">Deleting an existing network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27583-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="27583-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="27583-104">ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="27583-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="27583-105">Lync Server 2013 コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="27583-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="27583-106">たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="27583-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="27583-107">CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27583-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="27583-108">Lync Server コントロールパネルから、ネットワークサイトの作成、変更、および削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="27583-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="27583-109">既存のネットワーク サイトを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27583-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="27583-110">ネットワークサイトの作成または変更の詳細については、「 [Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-creating-or-modifying-network-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27583-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="27583-111">ネットワーク サイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="27583-111">To delete a network site</span></span>

1.  <span data-ttu-id="27583-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="27583-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="27583-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="27583-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="27583-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27583-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="27583-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27583-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="27583-116">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="27583-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="27583-p103">1 つ以上のサイトを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のサイトを選択します。 また、すべてのサイトを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27583-p103">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="27583-120">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27583-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="27583-121">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27583-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="27583-p104">ただし、ネットワーク サイトがネットワーク サブネットに関連付けられている場合は、サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがサブネットに関連付けられているかどうかを確認するには、そのサイトをクリックして、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27583-p104">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

