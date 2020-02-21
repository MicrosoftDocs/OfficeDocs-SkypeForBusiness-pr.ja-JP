---
title: Lync Server 2013 および Exchange Server 2013 でのパートナーアプリケーションの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="9c346-102">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 でのパートナーアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="9c346-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c346-103">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="9c346-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="9c346-p101">サーバー間認証には、通常、3 つのエンティティが関与します。相互に通信する必要がある 2 つのサーバーと、サードパーティのセキュリティ トークン サーバーです。通信する必要がある 2 つのサーバー (サーバー A とサーバー B など) は、通常、最初にトークン サーバーに接続して、相互に信頼されたセキュリティ トークンを取得します。そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、一方のサーバーからもう一方のサーバー (サーバー A からサーバー B、またはサーバー B からサーバー A) に提示されます。</span><span class="sxs-lookup"><span data-stu-id="9c346-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="9c346-107">ただし、それは一般的な場合です。</span><span class="sxs-lookup"><span data-stu-id="9c346-107">However, that's a general rule.</span></span> <span data-ttu-id="9c346-108">Lync Server 2013、Microsoft Exchange Server 2013、および Microsoft SharePoint Server 2013 では、相互に通信する際にサードパーティのトークンサーバーを使用する必要はありません。これは、これらのサーバー製品では、別のトークンサーバーを使用せずに相互に受け付けることができるセキュリティトークンを作成できるからです。</span><span class="sxs-lookup"><span data-stu-id="9c346-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="9c346-109">(この機能は、Lync Server 2013、Exchange 2013、および SharePoint Server 2013 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c346-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="9c346-110">その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9c346-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="9c346-111">Lync Server と Exchange の間のサーバー間認証をセットアップするには、2つのことを行う必要があります。 1) 各サーバーに適切な証明書を割り当てる必要があります。および 2) 各サーバーを、他のサーバーのパートナーアプリケーションとして構成する必要があります。つまり、Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成し、Lync 2013 Server のパートナーアプリケーションとして Exchange 2013 を構成する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9c346-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="9c346-112">Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成する</span><span class="sxs-lookup"><span data-stu-id="9c346-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="9c346-113">Exchange 2013 で Lync Server 2013 をパートナーアプリケーションとして構成する最も簡単な方法は、Exchange 2013 に付属する Windows PowerShell スクリプトを実行して、Configure-EnterprisePartnerApplication スクリプトを実行することです。</span><span class="sxs-lookup"><span data-stu-id="9c346-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="9c346-114">このスクリプトを実行するには、Lync Server 認証メタデータドキュメントの URL を指定する必要があります。これは通常、Lync Server 2013 プールの完全修飾ドメイン名の後にサフィックス/metadata/json/1. が続きます。</span><span class="sxs-lookup"><span data-stu-id="9c346-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="9c346-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c346-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="9c346-116">Lync Server をパートナーアプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C: にインストールされており、既定のフォルダーパスを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="9c346-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="9c346-117">パートナーアプリケーションを構成した後、Exchange メールボックスサーバーおよびクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止および再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9c346-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="9c346-118">IIS を再起動するには、次のようなコマンドを使用します。これにより、コンピュータ atl-fs-01 でサービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="9c346-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="9c346-119">このコマンドは、Exchange 管理シェルまたは管理者特権で実行されている他の任意のコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c346-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="9c346-120">Lync Server 2013 のパートナーアプリケーションとしての Exchange 2013 の構成</span><span class="sxs-lookup"><span data-stu-id="9c346-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="9c346-121">Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成した後、Exchange を Lync Server のパートナーアプリケーションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c346-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="9c346-122">これは、Lync Server 管理シェルを使用して、Exchange 用の認証メタデータドキュメントを指定することによって行うことができます。これは通常、Exchange 自動検出サービスの URI の後にサフィックス/metadata/json/1. が続きます。</span><span class="sxs-lookup"><span data-stu-id="9c346-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="9c346-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c346-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="9c346-124">Lync Server では、 [get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))コマンドレットを使用してパートナーアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c346-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="9c346-125">メタデータ URI の指定に加えて、アプリケーションの信頼レベルも完全に設定する必要があります。これにより、Exchange は、その領域内の権限のあるユーザーとその両方を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="9c346-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="9c346-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c346-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="9c346-127">または、Lync Server 2013 のサーバー間認証のドキュメントで検出されたスクリプトコードをコピーして変更することによって、パートナーアプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c346-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="9c346-128">詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c346-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="9c346-129">Lync Server と Exchange の両方に対してパートナーアプリケーションが正常に構成されている場合は、2つの製品間のサーバー間認証も正常に構成されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9c346-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="9c346-130">Lync Server 2013 には、Windows PowerShell コマンドレット[test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))が含まれています。このコマンドレットを使用すると、サーバー間認証が正しく構成されており、Lync Server Storage Service が Exchange 2013 に接続できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c346-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="9c346-131">このコマンドレットでは、Exchange 2013 ユーザーのメールボックスに接続して、そのユーザーの会話履歴フォルダーにアイテムを書き込み、必要に応じてそのアイテムを削除することによって、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c346-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="9c346-132">Lync Server 2013 と Exchange 2013 の統合をテストするには、Lync Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c346-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="9c346-133">上記のコマンドで、Si31> i は、Exchange 2013 上のアカウントを持つユーザーの SIP アドレスを表します。これは有効なユーザーアカウントではないので、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c346-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="9c346-134">テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9c346-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

