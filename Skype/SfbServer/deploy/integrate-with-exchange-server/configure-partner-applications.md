---
title: Skype for Business Server 2015 および Exchange Server でパートナー アプリケーションを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server のサーバー間認証を構成します。'
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834047"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="a587a-103">Skype for Business Server および Exchange Server でパートナー アプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="a587a-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="a587a-104">**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server のサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="a587a-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="a587a-105">サーバー間認証では、通常、相互に通信する必要がある 2 台のサーバーとサードパーティのセキュリティ トークン サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a587a-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="a587a-106">サーバー A とサーバー B が通信する必要がある場合は、通常、両方のサーバーがトークン サーバーに接続し、相互に信頼できるセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="a587a-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="a587a-107">その後、サーバー A は、そのセキュリティ トークンをサーバー B (またはその逆) に、その信頼性と信頼性を保証する方法として提示します。</span><span class="sxs-lookup"><span data-stu-id="a587a-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="a587a-108">ただし、それは一般的な場合です。</span><span class="sxs-lookup"><span data-stu-id="a587a-108">However, that's a general rule.</span></span> <span data-ttu-id="a587a-109">Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 は、お客様が通信するときにサードパーティのトークン サーバーを使用する必要があります。これは、これらのサーバー製品が、別のトークン サーバーを必要とせずに、お客様が受け入れ可能なセキュリティ トークンを作成できるためです。</span><span class="sxs-lookup"><span data-stu-id="a587a-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="a587a-110">(この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a587a-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="a587a-111">その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a587a-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="a587a-112">Skype for Business Server と Exchange Server の間でサーバー間認証を設定するには、1) 各サーバーに適切な証明書を割り当てる必要があります。2) 各サーバーを他のサーバーのパートナー アプリケーションとして構成する必要があります。つまり、Skype for Business Server を Exchange Server のパートナー アプリケーションとして構成し、skype for Business Server のパートナー アプリケーションとして Exchange Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a587a-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="a587a-113">Skype for Business Server をパートナー アプリケーションとして構成Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a587a-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="a587a-114">Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成する最も簡単な方法は、Configure-EnterprisePartnerApplication.ps1 スクリプト (Exchange Server に組み込む Windows PowerShell スクリプト) を実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="a587a-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="a587a-115">このスクリプトを実行するには、Skype for Business Server 認証メタデータ ドキュメントの URL を指定する必要があります。これは通常、Skype for Business Server プールの完全修飾ドメイン名の後にサフィックス /metadata/json/1 が続きます。</span><span class="sxs-lookup"><span data-stu-id="a587a-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="a587a-116">例:</span><span class="sxs-lookup"><span data-stu-id="a587a-116">For example:</span></span>
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="a587a-117">Skype for Business Server をパートナー アプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange が C ドライブにインストールされ、既定のフォルダー パスが使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="a587a-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="a587a-118">パートナー アプリケーションを構成した後、Exchange メールボックスおよびクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止して再起動してください。</span><span class="sxs-lookup"><span data-stu-id="a587a-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="a587a-119">次のようなコマンドを使用して IIS を再起動できます。これにより、コンピューター atl-exchange-001 上のサービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="a587a-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="a587a-120">このコマンドは、Exchange 管理シェル 内から実行するか、管理者特権で実行する他のコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a587a-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="a587a-121">Skype for Business Exchange Serverパートナー アプリケーションとして構成する</span><span class="sxs-lookup"><span data-stu-id="a587a-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="a587a-122">Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成した後、skype for Business Server のパートナー アプリケーションとして Exchange Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a587a-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="a587a-123">これは、Skype for Business Server 管理シェルを使用して、Exchange の認証メタデータ ドキュメントを指定することで実行できます。これは通常、Exchange 自動検出サービスの URI の後にサフィックス /metadata/json/1 が続きます。</span><span class="sxs-lookup"><span data-stu-id="a587a-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="a587a-124">例:</span><span class="sxs-lookup"><span data-stu-id="a587a-124">For example:</span></span>
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="a587a-125">Skype for Business Server では、パートナー アプリケーションは [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) コマンドレットを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="a587a-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="a587a-126">メタデータ URI を指定する以外に、アプリケーション信頼レベルを Full に設定する必要があります。これにより、Exchange 自体と領域内の承認されたユーザーの両方を表す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a587a-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="a587a-127">例:</span><span class="sxs-lookup"><span data-stu-id="a587a-127">For example:</span></span>
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="a587a-128">または、Skype for Business Server のサーバー間認証のドキュメントにあるスクリプト コードをコピーして変更することで、パートナー アプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a587a-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="a587a-129">詳細については、Skype for Business Server のサーバー間認証 [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) およびパートナー アプリケーションの管理に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a587a-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="a587a-130">Skype for Business Server と Exchange Server の両方に対してパートナー アプリケーションを正常に構成した場合は、2 つの製品間のサーバー間認証も正常に構成されています。</span><span class="sxs-lookup"><span data-stu-id="a587a-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="a587a-131">Skype for Business Server には、Windows PowerShell コマンドレット [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) が含まれています。これにより、サーバー間認証が正しく構成され、Skype for Business Server ストレージ サービスが Exchange Server に接続可能な状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a587a-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="a587a-132">このコマンドレットでは、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、(必要に応じて) そのアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="a587a-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="a587a-133">Skype for Business Server と Exchange Server の統合をテストするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a587a-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="a587a-134">上のコマンドでは、SipUri は、アカウントを持つユーザーの SIP アドレスを表Exchange Server。コマンドは失敗しますが、これは有効なユーザー アカウントではありません。</span><span class="sxs-lookup"><span data-stu-id="a587a-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a587a-135">このコマンドレットから 401 応答を受け取った場合は、Exchange の既定の構成に Oauth トークンの受け入れサポートが含けられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a587a-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="a587a-136">Exchange での Oauth の使用の詳細については [、「SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=513103)と Skype for Business Server で OAuth 認証を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a587a-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="a587a-137">テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a587a-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
