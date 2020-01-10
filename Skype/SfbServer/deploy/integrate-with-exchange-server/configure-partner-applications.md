---
title: Skype for Business Server 2015 および Exchange Server でパートナーアプリケーションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server のサーバー認証を構成します。'
ms.openlocfilehash: 004b9c1926f00cd869658ae0b90679897d20516b
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001257"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="da70c-103">Skype for Business Server および Exchange Server でパートナーアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="da70c-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="da70c-104">**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server 用にサーバー認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="da70c-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="da70c-105">サーバー間認証には、通常、相互に通信する必要がある 2 台のサーバーと、サードパーティのセキュリティ トークン サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="da70c-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="da70c-106">サーバー A とサーバー B が通信する必要がある場合は、通常、どちらのサーバーも、トークンサーバーに連絡し、相互に信頼されたセキュリティトークンを取得することから始まります。</span><span class="sxs-lookup"><span data-stu-id="da70c-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="da70c-107">そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、サーバー A からサーバー B (またはサーバー B からサーバー A) に提示されます。</span><span class="sxs-lookup"><span data-stu-id="da70c-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="da70c-108">ただし、それは一般的な場合です。</span><span class="sxs-lookup"><span data-stu-id="da70c-108">However, that's a general rule.</span></span> <span data-ttu-id="da70c-109">Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 は、相互に通信するときに、サードパーティのトークンサーバーを使用する必要はありません。これは、これらのサーバー製品では、個別のトークンサーバーを必要とせずに、相互に受け入れ可能なセキュリティトークンを作成できるためです。</span><span class="sxs-lookup"><span data-stu-id="da70c-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="da70c-110">(この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="da70c-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="da70c-111">その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="da70c-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="da70c-112">Skype for Business Server と Exchange Server の間のサーバー間認証をセットアップするには、2つの操作を行う必要があります。 1) 各サーバーに適切な証明書を割り当てる必要があります。さらに、2) 各サーバーを他のサーバーのパートナーアプリケーションとして構成する必要があります。つまり、Skype for Business Server を Exchange Server のパートナーアプリケーションとして構成する必要があります。つまり、Skype のパートナーアプリケーションとして Exchange server を構成する必要があります。Business Server の場合。</span><span class="sxs-lookup"><span data-stu-id="da70c-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="da70c-113">Skype for Business Server を Exchange Server のパートナーアプリケーションとして構成する</span><span class="sxs-lookup"><span data-stu-id="da70c-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="da70c-114">Exchange server 2016 または Exchange Server 2013 とのパートナーアプリケーションとして Skype for Business Server を構成する最も簡単な方法は、Configure-EnterprisePartnerApplication スクリプトを実行することです。これは、Exchange Server に付属する Windows PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="da70c-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="da70c-115">このスクリプトを実行するには、Skype for Business Server authentication metadata ドキュメントの URL を指定する必要があります。通常、これは、Skype for Business サーバープールの完全修飾ドメイン名に続けてサフィックス/metadata/json/1. を指定します。</span><span class="sxs-lookup"><span data-stu-id="da70c-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="da70c-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da70c-116">For example:</span></span>
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="da70c-117">Skype for Business Server をパートナーアプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされていること、および既定のフォルダーパスを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="da70c-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="da70c-118">パートナーアプリケーションを構成した後、Exchange メールボックスとクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止して再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da70c-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="da70c-119">次のようなコマンドを使用して、IIS を再起動することができます。これは、コンピューターの atl-exchange-001 のサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="da70c-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="da70c-120">このコマンドは、Exchange 管理シェルから、または他のコマンドウィンドウで、管理者特権で実行できます。</span><span class="sxs-lookup"><span data-stu-id="da70c-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="da70c-121">Skype for Business Server のパートナーアプリケーションとなるように Exchange Server を構成する</span><span class="sxs-lookup"><span data-stu-id="da70c-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="da70c-122">Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナーアプリケーションとして構成した後、Exchange Server を Skype for Business Server のパートナーアプリケーションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da70c-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="da70c-123">これを行うには、Skype for Business Server 管理シェルを使用し、Exchange の認証メタデータドキュメントを指定します。通常、これは Exchange 自動検出サービスの URI に続けてサフィックス/metadata/json/1. を指定します。</span><span class="sxs-lookup"><span data-stu-id="da70c-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="da70c-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da70c-124">For example:</span></span>
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="da70c-125">Skype for Business Server では、 [CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps)コマンドレットを使用してパートナーアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="da70c-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="da70c-126">メタデータ URI の指定に加えて、アプリケーションの信頼レベルも完全に設定する必要があります。これにより、Exchange は、レルム内の権限を持つすべてのユーザーを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="da70c-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="da70c-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="da70c-127">For example:</span></span>
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="da70c-128">または、Skype for Business Server server のサーバー間認証ドキュメントにあるスクリプトコードをコピーして変更することで、パートナーアプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da70c-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="da70c-129">詳細については、「 [Skype For Business server のサーバー間認証 (OAuth) とパートナーアプリケーションを管理](../../manage/authentication/server-to-server-and-partner-applications.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da70c-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="da70c-130">Skype for Business Server と Exchange Server の両方に対してパートナーアプリケーションが正常に設定されている場合は、2つの製品間のサーバー間認証も正常に構成されています。</span><span class="sxs-lookup"><span data-stu-id="da70c-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="da70c-131">Skype for Business Server には Windows PowerShell コマンドレット[CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)が含まれています。これにより、サーバー間認証が正しく構成されていること、および skype For Business Server ストレージサービスが Exchange server に接続できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="da70c-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="da70c-132">このコマンドレットでは、これを行うには、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、そのアイテムを削除します (必要に応じて)。</span><span class="sxs-lookup"><span data-stu-id="da70c-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="da70c-133">Skype for business Server と Exchange Server の統合をテストするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da70c-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="da70c-134">上記のコマンドでは、Si24> は Exchange Server のアカウントを持つユーザーの SIP アドレスを表します。このコマンドは、無効なユーザアカウントであるため失敗します。</span><span class="sxs-lookup"><span data-stu-id="da70c-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da70c-135">このコマンドレットから401応答を受信した場合は、おそらく、Exchange の既定の構成に Oauth トークンの受け入れのサポートが含まれていないことが原因として考えられます。</span><span class="sxs-lookup"><span data-stu-id="da70c-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="da70c-136">Exchange での Oauth の使用について詳しくは、「 [SharePoint 2013 および Skype For Business Server での oauth 認証の構成](https://go.microsoft.com/fwlink/p/?LinkId=513103)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="da70c-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="da70c-137">テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="da70c-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
