---
title: サーバー間認証 (OAuth) およびパートナーアプリケーションの管理
description: サーバー間認証 (OAuth) およびパートナーアプリケーションを管理します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6efa413ad1809bcff27373a38334d09a8fbfcad9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560403"
---
# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="6ac4e-103">Lync Server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="6ac4e-103">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ac4e-104">_**トピックの最終更新日:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="6ac4e-104">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="6ac4e-105">Microsoft Lync Server 2013 は、安全かつシームレスに、他のアプリケーションやサーバー製品と通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-105">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="6ac4e-106">たとえば、Lync Server 2013 を構成して、連絡先データやアーカイブデータを Microsoft Exchange Server 2013 に保存することができます。ただし、これは、Lync Server と Exchange が相互に安全に通信できる場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-106">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="6ac4e-107">同様に、Lync Server 会議を Microsoft SharePoint Server 内からスケジュールすることができます。ただし、これは、2台のサーバー (SharePoint と Lync Server) が相互に信頼している場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-107">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="6ac4e-108">Lync から Exchange への通信に対して1つの認証機構を使用することができますが、Lync から SharePoint への通信には個別のメカニズムを使用することもできますが、すべてのサーバー間の認証と承認に標準化された方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-108">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="6ac4e-109">単一の標準化された方法を使用してサーバー間認証を実行することは、Lync Server 2013 による方法です。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-109">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="6ac4e-110">2013リリースでは、Lync Server 2013 (および Exchange 2013 および Microsoft SharePoint Server を含むその他の Microsoft Server 製品) は、サーバー間の認証と承認のために OAuth (オープン認証) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-110">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="6ac4e-111">OAuth では、多くの主要な web サイトで使用される標準の認証プロトコルであるコンピューターから別のコンピューターにユーザーの資格情報とパスワードが渡されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-111">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="6ac4e-112">代わりに、認証と承認はセキュリティトークンの交換に基づいています。これらのトークンは、特定の時間に特定のリソースのセットへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-112">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="6ac4e-113">OAuth 認証には、通常、1つの承認サーバーと、互いに通信する必要がある2つの領域の3つの関係者が関与します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-113">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="6ac4e-114">(このドキュメントで後述するプロセスを使用して、認証サーバーを使用せずにサーバー間認証を実行することもできます)。セキュリティトークンは、通信する必要がある2つの領域に対して、認証サーバー (セキュリティトークンサーバーとも呼ばれる) によって発行されます。これらのトークンは、あるレルムから発信された通信が他のレルムによって信頼されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-114">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="6ac4e-115">たとえば、認証サーバーは、特定の Lync Server 2013 領域のユーザーが、指定された Exchange 2013 領域にアクセスできることを確認するトークンを発行することがあります。また、その逆もあります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-115">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6ac4e-116">領域とは、セキュリティ コンテナーのことです。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-116">A realm is simply a security container.</span></span> <span data-ttu-id="6ac4e-117">既定では、Lync Server 2013 は既定の SIP ドメインを OAuth 領域として使用します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-117">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="6ac4e-118">その他の SIP 名前空間は、OAuth 証明書のサブジェクト代替名リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-118">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="6ac4e-119">Lync Server 2013 は、3つのサーバー間認証シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-119">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="6ac4e-120">Lync Server 2013 では、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-120">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="6ac4e-121">Lync Server 2013 の社内インストールと、Exchange 2013 または Microsoft SharePoint Server の社内インストールとの間のサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-121">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="6ac4e-122">Microsoft 365 コンポーネントのペア (Microsoft Exchange と Microsoft Lync Server 間、microsoft Lync Server と microsoft SharePoint との間など) の間でサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-122">Configure server-to-server authentication between a pair of Microsoft 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="6ac4e-123">クロスプレミス環境 (つまり、オンプレミスサーバーと Microsoft 365 コンポーネントの間のサーバー間認証) でサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-123">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Microsoft 365 component).</span></span>

<span data-ttu-id="6ac4e-124">この時点では、Exchange 2013、SharePoint Server、Lync Server 2013 のみがサーバー間認証をサポートすることに注意してください。これらのサーバーのいずれかを実行していない場合、OAuth 認証を完全に実装することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-124">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="6ac4e-125">また、サーバー間認証を使用する必要がないことを指摘する必要があります。 Lync Server 2013 を展開するためには、サーバー間認証は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-125">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="6ac4e-126">Lync Server 2013 が他のサーバー (Exchange 2013 など) と通信する必要がない場合は、サーバー間認証は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-126">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="6ac4e-127">ただし、「統合連絡先ストア」などの Lync Server の新機能の一部を使用する場合は、サーバー間認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-127">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="6ac4e-128">統合連絡先ストアの場合、Lync server 2013 の連絡先情報は、Lync Server ではなく Exchange 2013 に格納されます。これにより、ユーザーは、Lync、Microsoft Outlook、または Microsoft Outlook Web Access 内から簡単にアクセスできる単一の連絡先セットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-128">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="6ac4e-129">統合連絡先ストアでは、Lync Server 2013 で情報を Exchange 2013 と共有する必要があるため、機能を展開するには、サーバー間認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-129">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="6ac4e-130">Exchange アーカイブを使用することを選択した場合も、サーバー間認証が必要になります。これにより、インスタントメッセージングセッションのトランスクリプトは、個別のデータベースレコードとしてではなく、Exchange 2013 メールとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-130">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="6ac4e-131">Microsoft 365 版の Lync Server を Exchange の対応するバージョンと通信するには、まず、Lync Server 2013 が承認サーバーからセキュリティトークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-131">For the Microsoft 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="6ac4e-132">Lync Server は、そのセキュリティトークンを使用して Exchange に自分自身を識別します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-132">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="6ac4e-133">Microsoft 365 バージョンの Exchange は、Lync Server 2013 と通信するために同じプロセスを経由する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-133">The Microsoft 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="6ac4e-134">ただし、2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合は、サードパーティのトークンサーバーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-134">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="6ac4e-135">Lync Server 2013 および Exchange 2013 などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証のために使用できる組み込みのトークンサーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-135">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="6ac4e-136">たとえば、Lync Server 2013 はセキュリティトークンを自ら発行して署名し、そのトークンを使用して Exchange 2013 と通信できます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-136">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="6ac4e-137">このような場合、サード パーティのトークン サーバーは不要です。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-137">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="6ac4e-138">Lync Server 2013 の社内実装に対してサーバー間認証を構成するには、次の2つの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-138">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="6ac4e-139">Lync Server の組み込みトークン発行者に証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-139">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="6ac4e-140">Lync Server 2013 が通信するサーバーを "パートナーアプリケーション" として構成します。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-140">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="6ac4e-141">たとえば、Lync Server 2013 が Exchange 2013 と通信する必要がある場合は、Exchange をパートナーアプリケーションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-141">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6ac4e-142">"パートナーアプリケーション" とは、サードパーティのセキュリティトークンサーバーを使用せずに、Lync Server 2013 がセキュリティトークンを直接交換できるアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-142">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="6ac4e-143">OAuth は製品のコア部分であり、無効化または削除することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ac4e-143">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6ac4e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ac4e-144">See Also</span></span>


[<span data-ttu-id="6ac4e-145">サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ac4e-145">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="6ac4e-146">クロスプレミス環境での Microsoft Lync Server 2013 の構成</span><span class="sxs-lookup"><span data-stu-id="6ac4e-146">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

