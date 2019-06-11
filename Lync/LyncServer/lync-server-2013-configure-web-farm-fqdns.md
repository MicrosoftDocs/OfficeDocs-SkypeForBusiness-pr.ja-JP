---
title: 'Lync Server 2013: Web ファームの FQDN の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517e00baef63e3597c2f5b2b6621e62efb02ca62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="1f6b2-102">Lync Server 2013 向けの Web ファームの FQDN の構成</span><span class="sxs-lookup"><span data-stu-id="1f6b2-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f6b2-103">_**最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="1f6b2-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="1f6b2-104">Standard Edition server、フロントエンドプール、ディレクター、またはディレクターの構成をトポロジビルダーで定義した場合、外部 web サービスの完全修飾ドメイン名 (FQDN) を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1f6b2-105">Standard Edition server またはフロントエンドプールに所属しているクライアントのログオンプロセスでは、構成された web サービスの Fqdn は、インバンドプロビジョニングを通じて送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="1f6b2-106">外部 web サービスの URL を追加または変更する必要がある場合は、このトピックの手順を使用して、トポロジビルダーを使用して web サービスの構成を構成または再構成します。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="1f6b2-107">Web サービス用の外部プール FQDN を構成するには</span><span class="sxs-lookup"><span data-stu-id="1f6b2-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="1f6b2-108">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1f6b2-109">[トポロジビルダー] のコンソールツリーの、**標準エディションのフロントエンド**、 **Enterprise Edition のフロントエンド**、および**ディレクター**で、編集する必要があるプール名を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1f6b2-110">[ **Web services** ] セクションで、**外部 WEB サービスの FQDN**を追加または編集します。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="1f6b2-111">HTTP と HTTPS の両方の**リスニングポート**を確認し、調整します。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="1f6b2-112">既定値は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="1f6b2-113">**リスニングポート:** HTTP 8080、HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="1f6b2-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="1f6b2-114">公開された**ポート:** HTTP 80、HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="1f6b2-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="1f6b2-115">このポート\*\*\*\* は、外部 web サービスがリバースプロキシからの要求を受信するように構成されているポートであり、公開された**ポート**はリバースプロキシによって外部で公開されているポートであり、インバンドプロビジョニング中のクライアント。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="1f6b2-116">追加と更新が完了したら、[ **OK]** をクリックして操作を続けます。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="1f6b2-117">[ **Lync Server 2013**] を右クリックし、[**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f6b2-118">発行が正常に完了すると、追加の手順を実行する必要があることを知らせるリンクが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="1f6b2-119">リンクをクリックすると、[トポロジビルダー] で行った変更の影響を受けるサーバーの一覧が表示されます。このリンクをクリックすると、一覧の各サーバーで Lync Server 展開ウィザードを再実行して、追加、削除、または変更されたコンポーネントの構成を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="1f6b2-120">組織内の標準エディションサーバー、フロントエンドプール、ディレクター、またはディレクタープールごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1f6b2-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

