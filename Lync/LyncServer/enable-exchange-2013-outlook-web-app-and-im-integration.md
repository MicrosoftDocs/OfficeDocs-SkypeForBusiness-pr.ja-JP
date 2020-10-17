---
title: Exchange 2013 の Outlook Web App および IM 統合を有効にする
description: Exchange 2013 Outlook Web App および IM 統合を有効にします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551123"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="23bc5-103">Exchange 2013 の Outlook Web App および IM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="23bc5-103">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23bc5-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="23bc5-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="23bc5-105">Exchange 2013 Outlook Web Access (OWA) および Lync Server 2013 とのインスタントメッセージング (IM) の統合を有効にするには、Exchange 2013 クライアントアクセスサーバー (CAS) サーバーを、信頼されたアプリケーションサーバーとして Lync Server 2013 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23bc5-105">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="23bc5-106">信頼済みアプリケーション プールを作成するには</span><span class="sxs-lookup"><span data-stu-id="23bc5-106">To create a trusted application pool</span></span>

1.  <span data-ttu-id="23bc5-107">Lync Server 2013 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-107">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="23bc5-108">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-108">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="23bc5-109">これで、プールを作成する siteName に対応する siteID が取得されます。</span><span class="sxs-lookup"><span data-stu-id="23bc5-109">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="23bc5-110">詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [取得-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23bc5-110">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="23bc5-111">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-111">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="23bc5-112">詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [「new-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23bc5-112">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="23bc5-113">Exchange Server の FQDN を Exchange OWA 証明書のサブジェクト名 (SN) またはサブジェクトの別名 (SAN) として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23bc5-113">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="23bc5-114">Exchange OWA で、プールの FQDN も信頼されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-114">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23bc5-115">CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバー上に併置されて <EM>いない</EM> 場合は、この手順の残りの手順をスキップして、このトピックで後述する「EXCHANGE 2013 CAS サーバーの信頼されたアプリケーションを作成する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-115">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="23bc5-116">CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバー上に併置されている場合は、この手順の手順を実行します。このトピックで後述する「Exchange 2013 CAS サーバーの信頼されたアプリケーションを作成する」の手順を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="23bc5-116">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="23bc5-117">**Enable-CsTopology** を実行します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-117">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="23bc5-118">トポロジ ビルダーを開き、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="23bc5-118">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="23bc5-119">左側のウィンドウで、[**信頼済みアプリケーション サーバー**] が表示されるまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-119">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="23bc5-120">[**信頼済みアプリケーション サーバー**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-120">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="23bc5-121">これで、Exchange 2013 CAS サーバーが信頼済みアプリケーションサーバーとして表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="23bc5-121">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="23bc5-122">Exchange 2013 CAS サーバーの信頼されたアプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="23bc5-122">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="23bc5-123">Lync Server 2013 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-123">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="23bc5-124">CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバーに併置されて *いない* 場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-124">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="23bc5-125">詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [「new-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23bc5-125">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="23bc5-126">**Enable-CsTopology** を実行します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-126">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="23bc5-127">トポロジ ビルダーの左側のウィンドウで、[**信頼済みアプリケーション サーバー**] が表示されるまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-127">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="23bc5-128">[**信頼済みアプリケーション サーバー**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="23bc5-128">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="23bc5-129">これで、Exchange 2013 CAS サーバーが信頼済みアプリケーションサーバーとして表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="23bc5-129">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

