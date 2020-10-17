---
title: 'Lync Server 2013: web ファームの Fqdn の構成'
description: 'Lync Server 2013: web ファームの Fqdn を構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566663"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="cb0a7-103">Lync Server 2013 用に web ファーム Fqdn を構成する</span><span class="sxs-lookup"><span data-stu-id="cb0a7-103">Configure web farm FQDNs for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb0a7-104">_**トピックの最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="cb0a7-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="cb0a7-105">トポロジビルダーで、Standard Edition サーバー、フロントエンドプール、ディレクター、またはディレクタープールの構成を定義した場合は、外部 web サービスの完全修飾ドメイン名 (FQDN) を構成します。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-105">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="cb0a7-106">Standard Edition サーバーまたはフロントエンドプールに所属しているクライアントのログオンプロセス時に、構成された web サービスの Fqdn は、インバンドプロビジョニングの方法で送信されます。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-106">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="cb0a7-107">外部 web サービスの URL を追加または変更する必要がある場合は、このトピックの手順を使用して、トポロジビルダーを使用して web サービス構成を構成または再構成します。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-107">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="cb0a7-108">Web サービスで使用する外部プールの FQDN を構成するには</span><span class="sxs-lookup"><span data-stu-id="cb0a7-108">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="cb0a7-109">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="cb0a7-110">トポロジビルダーで、[ **Standard Edition フロントエンド**]、[ **Enterprise Edition フロントエンド**]、および [ **ディレクター**] の下にあるコンソールツリーで、編集する必要があるプール名を右クリックし、[ **プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-110">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="cb0a7-111">[**Web サービス**] セクションで、[**外部 Web サービスの FQDN**] を追加または編集します。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-111">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="cb0a7-p102">HTTP および HTTPS 両方の [**リッスン ポート**] を確認して調整します。既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="cb0a7-114">**リッスン ポート:** HTTP 8080、HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="cb0a7-114">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="cb0a7-115">**公開ポート:** HTTP 80、HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="cb0a7-115">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="cb0a7-116">[**リッスン ポート**] は外部 Web サービスがリバース プロキシからの要求を受信するように構成されているポートであり、[**公開ポート**] はリバース プロキシによって外部に公開されているポートで、インバンド プロビジョニングの間にクライアントに通知されます。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-116">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="cb0a7-117">追加および更新が終了したら、[**OK**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-117">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="cb0a7-118">[ **Lync Server 2013**] を右クリックし、[ **発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-118">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cb0a7-119">公開が正常に完了した後、実行する必要のある追加手順があることを示すリンクが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-119">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="cb0a7-120">リンクをクリックすると、表示された各サーバーで Lync Server 展開ウィザードを再実行して、追加、削除、または変更されたコンポーネントの構成を更新する必要があるトポロジビルダーで行われた変更の影響を受けるサーバーの一覧が開きます。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-120">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="cb0a7-121">組織内の Standard Edition サーバー、フロントエンドプール、ディレクター、またはディレクタープールごとに、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cb0a7-121">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

