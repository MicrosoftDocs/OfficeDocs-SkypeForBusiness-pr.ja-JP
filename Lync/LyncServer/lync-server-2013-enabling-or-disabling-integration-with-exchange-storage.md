---
title: 'Lync Server 2013: Exchange 記憶域との統合を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d2ded7e4cf586faf1f15ea6205aa23802413dc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="6d311-102">Lync Server 2013 と Exchange ストレージの統合を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6d311-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d311-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6d311-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6d311-104">Lync Server 2013 コントロールパネルで、[アーカイブ構成] を使って、Exchange ストレージとの統合を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6d311-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="6d311-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d311-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="6d311-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="6d311-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="6d311-107">作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。</span><span class="sxs-lookup"><span data-stu-id="6d311-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="6d311-108">アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」を参照してください。「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)(計画ドキュメント、展開)」を参照してください。ドキュメント、または操作のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="6d311-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="6d311-109">Microsoft Exchange 記憶域との統合を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="6d311-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="6d311-110">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d311-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d311-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d311-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d311-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d311-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d311-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d311-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="6d311-114">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d311-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="6d311-115">Exchange 2013 ストレージとの統合を有効にするには、[ **Microsoft Exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6d311-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="6d311-116">Exchange 2013 ストレージとの統合を無効にするには、[ **Microsoft Exchange 統合**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="6d311-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="6d311-117">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d311-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d311-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d311-118">See Also</span></span>


[<span data-ttu-id="6d311-119">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="6d311-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="6d311-120">組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="6d311-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

