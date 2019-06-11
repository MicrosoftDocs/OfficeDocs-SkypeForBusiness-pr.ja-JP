---
title: 'Lync Server 2013: アーカイブに失敗した場合に、IM および web 会議セッションをブロックまたは許可するために、クリティカルモードを有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="ed891-102">アーカイブに失敗した場合に IM および web 会議セッションをブロックまたは許可するための、Lync Server 2013 でのクリティカルモードの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="ed891-102">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed891-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ed891-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ed891-104">Lync Server 2013 コントロールパネルで、[アーカイブ構成] を使って、重要なモードを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ed891-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable critical mode.</span></span> <span data-ttu-id="ed891-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed891-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="ed891-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="ed891-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="ed891-107">作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。</span><span class="sxs-lookup"><span data-stu-id="ed891-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="ed891-108">アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ed891-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="ed891-109">アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」を参照してください。「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)(計画ドキュメント、展開)」を参照してください。ドキュメント、または操作のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="ed891-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed891-110">アーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または Lync Server 2013 を使用しているユーザーに対してアーカイブを有効にするかを指定するようにアーカイブポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed891-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="ed891-111">既定では、内部または外部の通信でアーカイブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="ed891-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="ed891-112">すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開用に適切なアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed891-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="ed891-113">アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed891-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="ed891-114">Exchange Server の統合機能を使用して exchange 2013 サーバー上のアーカイブデータとファイルを保存し、すべてのユーザーが Exchange 2013 サーバー上にある場合は、アーカイブを展開した後に、SQL Server データベースの設定を削除する必要があります。トポロジ。</span><span class="sxs-lookup"><span data-stu-id="ed891-114">If you decide after you deploy Archiving that you want to use Exchange Server integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="ed891-115">この操作を行うには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed891-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="ed891-116">詳細については、「運用ドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でアーカイブデータベースのオプションを変更する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed891-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="ed891-117">アーカイブに失敗した場合に、IM および web 会議セッションのブロックを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="ed891-117">To enable or disable blocking of IM and web conferencing sessions if archiving fails</span></span>

1.  <span data-ttu-id="ed891-118">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ed891-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ed891-119">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed891-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed891-120">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ed891-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed891-121">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed891-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="ed891-122">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed891-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>

5.  <span data-ttu-id="ed891-123">障害が発生したときのアーカイブの動作を設定するには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="ed891-123">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>

6.  <span data-ttu-id="ed891-124">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed891-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ed891-125">Windows PowerShell コマンドレットを使用して重要モードを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ed891-125">Enabling and Disabling Critical Mode by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ed891-126">**CsArchivingConfiguration**コマンドレットを使用して、重要なモードを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ed891-126">You can enable or disable critical mode using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="ed891-127">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="ed891-127">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ed891-128">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed891-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-critical-mode"></a><span data-ttu-id="ed891-129">クリティカルモードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="ed891-129">To enable critical mode</span></span>

  - <span data-ttu-id="ed891-130">クリティカルモードを有効にするには、Blockonアーカイブエラープロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed891-130">To enable critical mode, set the value of the BlockOnArchiveFailure property to True ($True).</span></span> <span data-ttu-id="ed891-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed891-131">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a><span data-ttu-id="ed891-132">重要モードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="ed891-132">To disable critical mode</span></span>

  - <span data-ttu-id="ed891-133">重要モードを無効にするには、Blockonアーカイブエラープロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed891-133">To disable critical mode, set the value of the BlockOnArchiveFailure property to False ($False).</span></span> <span data-ttu-id="ed891-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed891-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

<span data-ttu-id="ed891-135">詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed891-135">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed891-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed891-136">See Also</span></span>


[<span data-ttu-id="ed891-137">Lync Server 2013 でアーカイブデータベースのオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="ed891-137">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)  


[<span data-ttu-id="ed891-138">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="ed891-138">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="ed891-139">組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="ed891-139">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

