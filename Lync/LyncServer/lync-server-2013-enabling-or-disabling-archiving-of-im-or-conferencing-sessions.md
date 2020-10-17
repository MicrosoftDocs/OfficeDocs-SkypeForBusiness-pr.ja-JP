---
title: IM または電話会議セッションのアーカイブを有効または無効にする
description: IM または電話会議セッションのアーカイブを有効または無効にします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9861024bbd4f4a1558287139a37559f782fcf008
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546533"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="30e8c-103">Lync Server 2013 での IM または電話会議セッションのアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="30e8c-103">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30e8c-104">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="30e8c-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="30e8c-105">Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用して、IM、会議セッション、またはその両方のアーカイブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-105">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="30e8c-106">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="30e8c-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="30e8c-107">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="30e8c-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="30e8c-108">特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="30e8c-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="30e8c-109">アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="30e8c-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="30e8c-110">指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e8c-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="30e8c-111">アーカイブを使用するには、アーカイブポリシーを構成して、内部通信、外部通信、または Lync Server 2013 に所属するユーザーの両方に対してアーカイブを有効にするかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e8c-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="30e8c-112">既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="30e8c-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="30e8c-113">ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開に対して、また必要に応じて特定のサイトやプールに対して、適切なアーカイブ構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e8c-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="30e8c-114">アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e8c-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="30e8c-115">Microsoft Exchange 統合を使用してアーカイブデータおよびファイルを Exchange 2013 サーバーに保存し、すべてのユーザーが Exchange 2013 サーバーに所属している場合は、アーカイブを展開した後に、SQL Server データベース構成をトポロジから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e8c-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="30e8c-116">これを行うには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e8c-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="30e8c-117">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でのアーカイブデータベースオプションの変更</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e8c-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="30e8c-118">IM または電話会議セッションのアーカイブを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="30e8c-118">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="30e8c-119">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30e8c-120">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="30e8c-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30e8c-121">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e8c-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30e8c-122">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="30e8c-123">アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[ **編集**]、[ **詳細の表示**] の順にクリックして、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30e8c-123">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="30e8c-124">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、**[IM セッションのアーカイブ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-124">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="30e8c-125">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-125">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="30e8c-126">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-126">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="30e8c-127">**[確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30e8c-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30e8c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="30e8c-128">See Also</span></span>


[<span data-ttu-id="30e8c-129">組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理</span><span class="sxs-lookup"><span data-stu-id="30e8c-129">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="30e8c-130">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</span><span class="sxs-lookup"><span data-stu-id="30e8c-130">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

