---
title: 'フェーズ 8: 従来のプールを使用停止にする'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58ec7d07725ee75e5f20897894f465ac9fb269a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="6eec2-102">フェーズ 8: 従来のプールを使用停止にする</span><span class="sxs-lookup"><span data-stu-id="6eec2-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eec2-103">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="6eec2-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="6eec2-104">次のトピックでは、Lync Server 2010 の従来の展開での DNS エントリの更新、コンテンツ管理サーバーの移動、プールの使用停止、およびサーバーとプールの非アクティブ化と削除に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6eec2-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="6eec2-105">このセクションに記載された手順をすべて実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6eec2-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="6eec2-106">ドキュメントを読んで、どの使用停止の手順を実行すればよいかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="6eec2-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="6eec2-107">Lync server 2010 サーバーとサーバーの役割を削除する方法、および Lync Server 2010 の展開を使用停止にするためのステップバイステップガイドについては、「」を参照してください[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)。「Microsoft lync server 2010 をアンインストールし、サーバーの役割を削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eec2-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6eec2-108">従来の環境を使用停止にする前に、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行およびアップグレードの詳細については、「」を参照してください。<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="6eec2-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6eec2-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6eec2-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="6eec2-110">DNS SRV レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="6eec2-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="6eec2-111">Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動する</span><span class="sxs-lookup"><span data-stu-id="6eec2-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="6eec2-112">電話会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="6eec2-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="6eec2-113">アーカイブサーバーの関連付けを削除する</span><span class="sxs-lookup"><span data-stu-id="6eec2-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="6eec2-114">監視サーバーの関連付けを削除する</span><span class="sxs-lookup"><span data-stu-id="6eec2-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="6eec2-115">Enterprise Edition フロントエンドサーバーまたは Standard Edition フロントエンドサーバーを削除する</span><span class="sxs-lookup"><span data-stu-id="6eec2-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="6eec2-116">バックエンドサーバー上の SQL Server インスタンスとデータベースを削除する</span><span class="sxs-lookup"><span data-stu-id="6eec2-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

