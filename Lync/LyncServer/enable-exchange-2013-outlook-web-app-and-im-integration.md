---
title: Exchange 2013 Outlook Web App と IM の統合を有効にする
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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="26eff-102">Exchange 2013 Outlook Web App と IM の統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="26eff-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26eff-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="26eff-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="26eff-104">Exchange 2013 Outlook Web Access (OWA) およびインスタントメッセージング (IM) と Lync Server 2013 との統合を有効にするには、信頼されたアプリケーションサーバーとして、Exchange 2013 クライアントアクセスサーバー (CAS) サーバーを Lync Server 2013 トポロジに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26eff-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="26eff-105">信頼されたアプリケーションプールを作成するには</span><span class="sxs-lookup"><span data-stu-id="26eff-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="26eff-106">Lync Server 2013 Management Shell を起動します。</span><span class="sxs-lookup"><span data-stu-id="26eff-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="26eff-107">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="26eff-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="26eff-108">これにより、プールを作成している siteName の siteID が返されます。</span><span class="sxs-lookup"><span data-stu-id="26eff-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="26eff-109">詳細については、「Lync Server 2013 管理シェルのドキュメントの[入手-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26eff-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="26eff-110">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="26eff-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="26eff-111">詳細については、「Lync Server 2013 管理シェルドキュメントの「[新規-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26eff-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="26eff-112">Exchange Server の FQDN は、Exchange OWA 証明書のサブジェクト名 (SN)、またはサブジェクトの代替名 (SAN) として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26eff-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="26eff-113">Exchange OWA で、プールの FQDN も信頼されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="26eff-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="26eff-114">使用している CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているサーバーと同じサーバーに併置されて<EM>いない</EM>場合は、この手順の残りの手順をスキップして、このトピックで後述する「EXCHANGE 2013 CAS サーバー用の信頼済みアプリケーションを作成する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="26eff-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="26eff-115">使用している CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているサーバー上にある場合は、この手順を実行して、このトピックで後述する「Exchange 2013 CAS サーバー用に信頼されたアプリケーションを作成する」の手順を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="26eff-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="26eff-116">**Enable-CsTopology を**実行します。</span><span class="sxs-lookup"><span data-stu-id="26eff-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="26eff-117">トポロジビルダーを開き、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="26eff-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="26eff-118">左側のウィンドウで、**信頼できるアプリケーションサーバー**に到達するまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="26eff-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="26eff-119">[信頼されている**アプリケーションサーバー** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="26eff-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="26eff-120">これで、信頼できるアプリケーションサーバーとして表示された Exchange 2013 CAS サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26eff-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="26eff-121">Exchange 2013 CAS サーバー用の信頼できるアプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="26eff-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="26eff-122">Lync Server 2013 Management Shell を起動します。</span><span class="sxs-lookup"><span data-stu-id="26eff-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="26eff-123">CAS サーバーが Exchange 2013 ユニファイドメッセージング (UM) を実行しているサーバー上に*ない*場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="26eff-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="26eff-124">詳細については、「Lync Server 2013 管理シェルドキュメントの「 [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26eff-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="26eff-125">**Enable-CsTopology を**実行します。</span><span class="sxs-lookup"><span data-stu-id="26eff-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="26eff-126">[Topology Builder] の左側のウィンドウで、**信頼できるアプリケーションサーバー**に到達するまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="26eff-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="26eff-127">[信頼されている**アプリケーションサーバー** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="26eff-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="26eff-128">これで、信頼できるアプリケーションサーバーとして表示された Exchange 2013 CAS サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26eff-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

