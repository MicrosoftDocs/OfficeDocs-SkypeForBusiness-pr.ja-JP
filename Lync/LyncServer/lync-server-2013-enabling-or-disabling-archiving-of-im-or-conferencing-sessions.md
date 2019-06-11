---
title: IM または会議セッションのアーカイブを有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65712cf15ae73ec7cdb49dc7652348085a4c93d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="caaf0-102">Lync Server 2013 での IM または会議セッションのアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="caaf0-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caaf0-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="caaf0-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="caaf0-104">Lync Server 2013 コントロールパネルで、[アーカイブ構成] を使って、IM、会議セッション、またはその両方のアーカイブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="caaf0-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="caaf0-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="caaf0-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="caaf0-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="caaf0-107">作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。</span><span class="sxs-lookup"><span data-stu-id="caaf0-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="caaf0-108">アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="caaf0-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="caaf0-109">アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」を参照してください。「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)(計画ドキュメント、展開)」を参照してください。ドキュメント、または操作のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="caaf0-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="caaf0-110">アーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または Lync Server 2013 を使用しているユーザーに対してアーカイブを有効にするかを指定するようにアーカイブポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caaf0-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="caaf0-111">既定では、内部または外部の通信でアーカイブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="caaf0-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="caaf0-112">すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開に適したアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caaf0-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="caaf0-113">アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caaf0-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="caaf0-114">Microsoft Exchange 統合を使用して Exchange 2013 サーバー上のアーカイブデータとファイルを保存し、すべてのユーザーが Exchange 2013 サーバー上にある場合は、アーカイブを展開した後に、SQL Server データベースの構成を削除する必要があります。を選びます。</span><span class="sxs-lookup"><span data-stu-id="caaf0-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="caaf0-115">この操作を行うには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caaf0-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="caaf0-116">詳細については、「運用ドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でアーカイブデータベースのオプションを変更する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caaf0-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="caaf0-117">IM または会議セッションのアーカイブを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="caaf0-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="caaf0-118">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="caaf0-119">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="caaf0-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="caaf0-120">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caaf0-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="caaf0-121">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="caaf0-122">アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックしてから次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="caaf0-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="caaf0-123">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="caaf0-124">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="caaf0-125">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="caaf0-126">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caaf0-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="caaf0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="caaf0-127">See Also</span></span>


[<span data-ttu-id="caaf0-128">組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="caaf0-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="caaf0-129">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="caaf0-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

