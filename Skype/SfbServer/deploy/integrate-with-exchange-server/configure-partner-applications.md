---
title: ビジネス サーバー 2015 と Exchange Server の Skype のパートナーのアプリケーションを構成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '概要: 2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバー用のサーバーの認証を構成します。'
ms.openlocfilehash: d9d2b32b637946555b906f24e7abbd5dda007d7f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216880"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="0f399-103">ビジネス サーバーと Exchange Server の Skype のパートナーのアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0f399-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="0f399-104">**の概要:** 2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバー用のサーバーの認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="0f399-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="0f399-105">サーバー間認証には、通常、相互に通信する必要がある 2 台のサーバーと、サードパーティのセキュリティ トークン サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f399-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="0f399-106">サーバー A とサーバー B は、通信する必要がある場合、それらのサーバーの両方の通常開始トークン サーバーに接続し、相互に信頼されたセキュリティ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="0f399-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="0f399-107">そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、サーバー A からサーバー B (またはサーバー B からサーバー A) に提示されます。</span><span class="sxs-lookup"><span data-stu-id="0f399-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="0f399-108">ただし、それは一般的な場合です。</span><span class="sxs-lookup"><span data-stu-id="0f399-108">However, that's a general rule.</span></span> <span data-ttu-id="0f399-109">ビジネス サーバー、Exchange Server 2016、Exchange Server 2013 では、SharePoint Server 2013 の Skype は、他と通信するときに、サード ・ パーティ製トークン サーバーを使用する必要はありません。これらのサーバー製品は、トークンに別のサーバーを必要とせずに互いに認めることができるセキュリティ トークンを作成できるためです。</span><span class="sxs-lookup"><span data-stu-id="0f399-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="0f399-110">(この機能は Exchange Server 2016、ビジネス サーバー、Exchange Server 2013 では、および SharePoint Server 2013 の Skype ではできるだけです。</span><span class="sxs-lookup"><span data-stu-id="0f399-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="0f399-111">その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0f399-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="0f399-112">Skype ビジネス サーバーと Exchange Server 間でサーバーからサーバーへの認証を設定するのには 2 つの操作を行う必要があります: 1) 各サーバーに適切な証明書を割り当てる必要があります2) 他のサーバーのパートナーのアプリケーションには、各サーバーを構成する必要があります: つまり、ビジネスのサーバーの Exchange Server では、パートナー アプリケーションの Skype を構成する必要があり、Skype のパートナー アプリケーションである Exchange Server を構成する必要がありますビジネス サーバーです。</span><span class="sxs-lookup"><span data-stu-id="0f399-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="0f399-113">Skype のビジネスのサーバーを Exchange Server のパートナーのアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0f399-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="0f399-114">2016 の Exchange Server や Exchange Server 2013 とパートナーのアプリケーション サーバーをビジネス用の Skype を構成する最も簡単な方法では、Exchange Server に付属している Windows PowerShell スクリプトを構成する EnterprisePartnerApplication.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f399-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="0f399-115">このスクリプトを実行するには、ビジネスのサーバー認証メタデータ ドキュメントの Skype の URL を指定する必要があります。通常、Skype のサフィックス/metadata/json/1 に続くビジネス サーバー プールの完全修飾ドメイン名になります。</span><span class="sxs-lookup"><span data-stu-id="0f399-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="0f399-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f399-116">For example:</span></span>
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="0f399-117">ビジネス パートナーのアプリケーション サーバー用には、Skype を構成するには、Exchange 管理シェルを開くし、(と仮定すると、Exchange は、ドライブ c: にインストールされているし、既定のフォルダーのパスを使用する) は、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f399-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="0f399-118">パートナー アプリケーションを構成した後、停止して、Exchange のメールボックスおよびクライアント アクセス サーバーのインターネット インフォメーション サービス (IIS) を再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f399-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="0f399-119">コマンドを使用して、次のようなコンピューター atl-exchange-001 のサービスを再起動する、IIS を再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="0f399-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="0f399-120">Exchange 管理シェル内で、または管理者特権で実行して、他のコマンド ウィンドウからこのコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0f399-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="0f399-121">ビジネス サーバーの Skype のパートナー アプリケーションである Exchange Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="0f399-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="0f399-122">2016 の Exchange Server や Exchange Server 2013 のパートナーのアプリケーション サーバーをビジネス用の Skype を構成した後は、ビジネス サーバーの Skype のパートナー アプリケーションである Exchange Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f399-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="0f399-123">これによってビジネス サーバー管理シェルには、Skype を使用して、exchange は認証メタデータ ドキュメントを指定します。通常サフィックス/metadata/json/1 の後に Exchange 自動検出サービスの URI になります。</span><span class="sxs-lookup"><span data-stu-id="0f399-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="0f399-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f399-124">For example:</span></span>
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="0f399-125">ビジネス サーバーの Skype は、パートナーのアプリケーションが[新しい CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps)コマンドレットを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="0f399-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="0f399-126">メタデータの URI を指定するだけでなく設定はアプリケーションの信頼レベルを完全にこれによって、Exchange 自体およびレルム内のすべての権限を持つユーザーを表す。</span><span class="sxs-lookup"><span data-stu-id="0f399-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="0f399-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f399-127">For example:</span></span>
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="0f399-128">代わりに、ビジネスのサーバーのサーバーからサーバーへの認証について Skype のスクリプト コードを変更することをコピーして、パートナーのアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f399-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="0f399-129">詳細については、[管理サーバーからサーバーへの認証 (OAuth) とビジネス サーバーの Skype のパートナーのアプリケーション](../../manage/authentication/server-to-server-and-partner-applications.md)の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f399-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="0f399-130">ビジネス サーバーと Exchange Server の両方の Skype のパートナーのアプリケーションを正常に構成した場合も正常に構成した 2 つの製品間でのサーバーからサーバーへの認証です。</span><span class="sxs-lookup"><span data-stu-id="0f399-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="0f399-131">Skype ビジネス サーバー用には、Windows PowerShell コマンドレットを使用すると、そのサーバーからサーバーへの認証が正しく構成されていることを確認する[テスト CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)ビジネス サーバー ・ ストレージ ・ サービスの Skype ができることが含まれています。Exchange Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="0f399-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="0f399-132">コマンドレットは、Exchange Server のユーザーのメールボックスに接続して、そのユーザーの会話の履歴フォルダーにアイテムを作成、し、その項目を削除する (必要に応じて) します。</span><span class="sxs-lookup"><span data-stu-id="0f399-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="0f399-133">Skype ビジネス サーバーと Exchange Server の統合をテストするには、ビジネス サーバー管理シェルには、Skype から次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f399-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="0f399-134">上記のコマンドでは、SipUri は Exchange Server のアカウントを持つユーザーの SIP アドレスを表します。コマンドは正常に有効なユーザー アカウントではありません。</span><span class="sxs-lookup"><span data-stu-id="0f399-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f399-135">このコマンドレットから 401 応答を受信する場合はおそらく Exchange の既定の構成には Oauth トークンを許可するためのサポートが含まれていないためです。</span><span class="sxs-lookup"><span data-stu-id="0f399-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="0f399-136">Oauth を使用して Exchange の詳細については、 [SharePoint 2013 と Skype ビジネス サーバーの構成の OAuth 認証](https://go.microsoft.com/fwlink/p/?LinkId=513103)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f399-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="0f399-137">テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0f399-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
