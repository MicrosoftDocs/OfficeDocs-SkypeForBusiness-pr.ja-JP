---
title: 'Lync Server 2013: パブリック インスタント メッセージング接続の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="fceaa-102">Lync Server 2013 でのパブリック インスタント メッセージング接続の設定</span><span class="sxs-lookup"><span data-stu-id="fceaa-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fceaa-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="fceaa-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="fceaa-104">組織で AOL とのパブリックインスタントメッセージング (IM) 接続をサポートしたい場合は、Lync Server Deployment ウィザードを使って証明書を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="fceaa-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="fceaa-105">代わりに、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="fceaa-106">パブリックインスタントメッセージング接続の設定</span><span class="sxs-lookup"><span data-stu-id="fceaa-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="fceaa-107">フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="fceaa-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="fceaa-108">[Edge プール] を展開し、エッジサーバーまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="fceaa-109">[プロパティの編集] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fceaa-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="fceaa-110">[プロパティの編集] の [全般] で、[このエッジプールに対してフェデレーションを有効にする (ポート 5061)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="fceaa-111">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-111">Click OK.</span></span>

3.  <span data-ttu-id="fceaa-112">[アクション] をクリックし、[トポロジ] を選択し、[発行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="fceaa-113">トポロジの発行を求められたら、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="fceaa-114">発行が完了したら、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="fceaa-115">エッジサーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="fceaa-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="fceaa-116">[Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="fceaa-117">[実行] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-117">Click Run Again.</span></span>

5.  <span data-ttu-id="fceaa-118">Lync Server コンポーネントのセットアップで、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fceaa-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="fceaa-119">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fceaa-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="fceaa-120">展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="fceaa-121">[完了] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="fceaa-122">AOL とのパブリック IM 接続をサポートするために、エッジサーバーの外部インターフェイスの証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="fceaa-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="fceaa-123">必要なテンプレートが CA で利用できるようになったら、エッジサーバーから次の Windows PowerShell コマンドレットを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="fceaa-124">Lync Server で使用されるテンプレートの既定の証明書名は、Web サーバーです。</span><span class="sxs-lookup"><span data-stu-id="fceaa-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="fceaa-125">既定のテンプレート\<とは\>異なるテンプレートを使用する必要がある場合は、テンプレート名のみを指定します。</span><span class="sxs-lookup"><span data-stu-id="fceaa-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fceaa-126">組織で AOL とのパブリック IM 接続をサポートしたい場合は、証明書ウィザードの代わりに Windows PowerShell を使用して、アクセスエッジサービスの外部境界に証明書を割り当てるように要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fceaa-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="fceaa-127">これは、証明書ウィザードで証明書を要求するために使用される証明機関 (CA) Web サーバーテンプレートがクライアント EKU 構成をサポートしていないためです。</span><span class="sxs-lookup"><span data-stu-id="fceaa-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="fceaa-128">Windows PowerShell を使用して証明書を作成する前に、CA 管理者がクライアント EKU をサポートする新しいテンプレートを作成して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fceaa-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

