---
title: 'Lync Server 2013: パブリックインスタントメッセージング接続の設定'
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
ms.openlocfilehash: 4887e419e45f6b6fb165dc7efff407332f3e150a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="8fc1a-102">Lync Server 2013 でのパブリックインスタントメッセージング接続の設定</span><span class="sxs-lookup"><span data-stu-id="8fc1a-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fc1a-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8fc1a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8fc1a-p101">組織で AOL とのパブリック インスタント メッセージング (IM) 接続をサポートする必要がある場合は、Lync Server 展開ウィザードを使用して証明書を要求することはできません。代わりに、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="8fc1a-106">パブリック インスタント メッセージング接続の設定</span><span class="sxs-lookup"><span data-stu-id="8fc1a-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="8fc1a-p102">フロントエンド サーバーで、トポロジ ビルダーを開きます。エッジ プールを展開し、エッジ サーバーまたはエッジ サーバー プールを右クリックして、[プロパティの編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="8fc1a-p103">[全般] の下の [プロパティの編集] で、[このエッジ プールのフェデレーションの有効化 (ポート 5061)] を選択します。[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="8fc1a-p104">[アクション] をクリックし、[トポロジ]、[公開] の順にクリックします。トポロジの公開を確認するプロンプトが表示されたら、[次へ] をクリックします。公開が完了したら、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="8fc1a-p105">エッジ サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="8fc1a-p106">[Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行されたアクションが表示されます。展開が完了したら、[ログの表示] をクリックして、参照できるログ ファイルを表示します。 [完了] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="8fc1a-122">AOL とのパブリック IM 接続をサポートするために、エッジ サーバーの外部インターフェイス用に証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="8fc1a-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="8fc1a-123">必要なテンプレートが CA で利用できる場合、エッジ サーバーで次の Windows PowerShell コマンドレットを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="8fc1a-124">Lync Server で使用されるテンプレートの既定の証明書名は Web サーバーです。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="8fc1a-125">既定のテンプレート\<とは\>異なるテンプレートを使用する必要がある場合にのみ、テンプレート名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fc1a-126">組織で AOL とのパブリック IM 接続をサポートする必要がある場合は、証明書ウィザードではなく Windows PowerShell を使用して、アクセスエッジサービスの外部エッジに証明書を割り当てるよう要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="8fc1a-127">これは、証明書を要求するために証明書ウィザードが使用する証明機関 (CA) Web サーバー テンプレートが、クライアント EKU 構成をサポートしていないためです。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="8fc1a-128">Windows PowerShell を使用して証明書を作成する前に、CA 管理者はクライアント EKU をサポートする新しいテンプレートを作成して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

