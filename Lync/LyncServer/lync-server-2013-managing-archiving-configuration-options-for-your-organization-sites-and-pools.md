---
title: 'Lync Server 2013: 組織、サイト、およびプールのアーカイブ構成オプションの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498364"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="6158f-102">組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理</span><span class="sxs-lookup"><span data-stu-id="6158f-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6158f-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6158f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6158f-104">Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用してアーカイブの実装方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6158f-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="6158f-105">これには、次のアーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6158f-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="6158f-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="6158f-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="6158f-107">特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="6158f-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="6158f-108">アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="6158f-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="6158f-109">Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブ構成**] ページを使用して、グローバルレベル、サイトレベル、およびプールレベルで構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="6158f-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="6158f-110">指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6158f-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6158f-111">アーカイブを使用するには、アーカイブポリシーを構成して、Lync Server 2013 に所属するすべてのユーザーに対して、内部通信、外部通信、または両方のアーカイブを有効にするかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6158f-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="6158f-112">既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="6158f-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="6158f-113">Microsoft Exchange 統合を使用する場合は、exchange 2013 に所属するすべてのユーザーのアーカイブをサポートするように Exchange 2013 を有効にし、構成する必要があります。メールボックスが In-Place 保持に配置されています。</span><span class="sxs-lookup"><span data-stu-id="6158f-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="6158f-114">アーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6158f-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="6158f-115">アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6158f-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="6158f-116">**Windows PowerShell コマンドレットを使用してアーカイブ構成情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="6158f-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="6158f-117">Windows PowerShell と **set-csarchivingconfiguration** コマンドレットを使用して、アーカイブ構成情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6158f-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="6158f-118">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6158f-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6158f-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="6158f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="6158f-120">Lync Server 管理シェルで、次のコマンドを使用して、すべてのアーカイブ構成設定に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="6158f-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="6158f-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6158f-121">In This Section</span></span>

  - [<span data-ttu-id="6158f-122">Lync Server 2013 でのアーカイブ構成を作成して、特定のサイトまたはプールのアーカイブを管理する</span><span class="sxs-lookup"><span data-stu-id="6158f-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="6158f-123">Lync Server 2013 での IM または電話会議セッションのアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6158f-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="6158f-124">Lync Server 2013 でのアーカイブされたデータの削除を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6158f-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="6158f-125">アーカイブが失敗した場合に IM および web 会議セッションを禁止または許可するために Lync Server 2013 の重要モードを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6158f-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="6158f-126">Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6158f-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="6158f-127">Lync Server 2013 と Exchange ストレージの統合を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6158f-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="6158f-128">Lync Server 2013 でのアーカイブ構成の削除</span><span class="sxs-lookup"><span data-stu-id="6158f-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6158f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6158f-129">See Also</span></span>


[<span data-ttu-id="6158f-130">Lync Server 2013 アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="6158f-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

