---
title: 'Lync Server 2013: パッシブ認証を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="d99ae-102">Lync Server 2013 のパッシブ認証を構成する</span><span class="sxs-lookup"><span data-stu-id="d99ae-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d99ae-103">_**最終更新日:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="d99ae-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="d99ae-104">以下のセクションでは、累積更新プログラムを使って Lync Server 2013 を構成する方法について説明します。2013年7月パッシブ認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d99ae-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="d99ae-105">有効にした後、2要素認証が有効になっている Lync ユーザーは、物理または仮想スマートカードと有効な PIN を使用して、Lync 2013 で累積更新プログラムを使ってサインインする必要があります。これは、2013年7月のクライアントです。</span><span class="sxs-lookup"><span data-stu-id="d99ae-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="d99ae-106">レジストラーと Web サービスのパッシブ認証はサービス レベルで有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d99ae-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="d99ae-107">グローバルレベルでレジストラーと Web サービスのパッシブ認証が有効になっている場合、累積更新プログラムを使って Lync 2013 でサインインしていないユーザーに対して、組織全体の認証エラーが発生する可能性があります。これは、2013年7月のクライアントデスクトップクライアントです。</span><span class="sxs-lookup"><span data-stu-id="d99ae-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="d99ae-108">Web サービス構成設定</span><span class="sxs-lookup"><span data-stu-id="d99ae-108">Web Service Configuration</span></span>

<span data-ttu-id="d99ae-109">次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーにカスタムの Web サービス構成設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="d99ae-110">**カスタムの Web サービス構成設定を作成するには**</span><span class="sxs-lookup"><span data-stu-id="d99ae-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="d99ae-111">累積更新プログラムで Lync Server 2013 にログインします。 Lync 管理者アカウントを使用して、2013年7月のフロントエンドサーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="d99ae-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="d99ae-112">Lync Server 2013 Management Shell を起動します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="d99ae-113">Lync Server 管理シェルコマンドラインで、次のコマンドを実行して、各ディレクター、エンタープライズプール、および標準エディションサーバー用の新しい Web サービス構成を作成します。これにより、パッシブ認証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d99ae-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="d99ae-p103">WsFedPassiveMetadataUri の FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。フェデレーション サービス名の値は、AD FS 2.0 管理コンソールでナビゲーション ウィンドウの [<STRONG>サービス</STRONG>] を右クリックし、[<STRONG>Edit Federation Service Properties</STRONG>] を選択すると確認できます。</span><span class="sxs-lookup"><span data-stu-id="d99ae-p103">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="d99ae-116">次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="d99ae-117">クライアントでは、パッシブ認証は WebTicket 認証の最も望ましくない方法です。</span><span class="sxs-lookup"><span data-stu-id="d99ae-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="d99ae-118">パッシブ認証を有効にするすべてのディレクター、エンタープライズプール、および標準エディションのサーバーについては、次のコマンドを実行して、Lync Web サービスで他のすべての認証の種類を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d99ae-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="d99ae-119">次のコマンドを実行して、他のすべての認証の種類が正常に無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="d99ae-120">プロキシ構成設定</span><span class="sxs-lookup"><span data-stu-id="d99ae-120">Proxy Configuration</span></span>

<span data-ttu-id="d99ae-121">Lync Web サービスの証明書認証が無効になっている場合、Lync クライアントは、より優先度の低い認証の種類 (Kerberos、NTLM など) を使用してレジストラーサービスを認証します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="d99ae-122">ただし、証明書の認証は、Lync クライアントが webticket を取得できるようにするために必要ですが、レジストラーサービスについては、Kerberos と NTLM を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d99ae-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="d99ae-123">次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーにカスタムのプロキシ構成設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="d99ae-124">**カスタムのプロキシ構成設定を作成するには**</span><span class="sxs-lookup"><span data-stu-id="d99ae-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="d99ae-125">Lync Server 管理シェルコマンドラインから、累積更新プログラムを使用して、各 Lync Server 2013 に対して新しいプロキシ構成を作成します。 2013 Edge プール、エンタープライズプール、Standard Edition Server は、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="d99ae-126">次のコマンドを実行して、他のすべてのプロキシ認証の種類が無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d99ae-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

