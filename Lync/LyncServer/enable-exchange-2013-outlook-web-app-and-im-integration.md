---
title: Exchange 2013 の Outlook Web App および IM 統合を有効にする
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
ms.openlocfilehash: da4289f663d62d1638c0f669e17a5e318e0788d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="3d24c-102">Exchange 2013 の Outlook Web App および IM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="3d24c-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d24c-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3d24c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3d24c-104">Exchange 2013 Outlook Web Access (OWA) および Lync Server 2013 とのインスタントメッセージング (IM) の統合を有効にするには、Exchange 2013 クライアントアクセスサーバー (CAS) サーバーを、信頼されたアプリケーションサーバーとして Lync Server 2013 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d24c-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="3d24c-105">信頼済みアプリケーション プールを作成するには</span><span class="sxs-lookup"><span data-stu-id="3d24c-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="3d24c-106">Lync Server 2013 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3d24c-107">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="3d24c-108">これで、プールを作成する siteName に対応する siteID が取得されます。</span><span class="sxs-lookup"><span data-stu-id="3d24c-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="3d24c-109">詳細については、「Lync Server 2013 Management Shell」のドキュメントの「[取得-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d24c-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="3d24c-110">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="3d24c-111">詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [「new-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d24c-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="3d24c-112">Exchange Server の FQDN を Exchange OWA 証明書のサブジェクト名 (SN) またはサブジェクトの別名 (SAN) として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d24c-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="3d24c-113">Exchange OWA で、プールの FQDN も信頼されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3d24c-114">CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバー上に併置されて<EM>いない</EM>場合は、この手順の残りの手順をスキップして、このトピックで後述する「EXCHANGE 2013 CAS サーバーの信頼されたアプリケーションを作成する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="3d24c-115">CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバー上に併置されている場合は、この手順の手順を実行します。このトピックで後述する「Exchange 2013 CAS サーバーの信頼されたアプリケーションを作成する」の手順を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="3d24c-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="3d24c-116">**Enable-CsTopology** を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="3d24c-117">トポロジ ビルダーを開き、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3d24c-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="3d24c-118">左側のウィンドウで、[**信頼済みアプリケーション サーバー**] が表示されるまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="3d24c-119">[**信頼されたアプリケーション サーバー**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="3d24c-120">これで、Exchange 2013 CAS サーバーが信頼済みアプリケーションサーバーとして表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3d24c-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="3d24c-121">Exchange 2013 CAS サーバーの信頼されたアプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="3d24c-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="3d24c-122">Lync Server 2013 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3d24c-123">CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバーに併置されて*いない*場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="3d24c-124">詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [「new-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d24c-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="3d24c-125">**Enable-CsTopology** を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="3d24c-126">トポロジ ビルダーの左側のウィンドウで、[**信頼済みアプリケーション サーバー**] が表示されるまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="3d24c-127">[**信頼済みアプリケーション サーバー**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d24c-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="3d24c-128">これで、Exchange 2013 CAS サーバーが信頼済みアプリケーションサーバーとして表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3d24c-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

