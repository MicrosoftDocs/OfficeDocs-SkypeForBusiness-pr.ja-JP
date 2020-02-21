---
title: 'Lync Server 2013: パッシブ認証の構成'
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
ms.openlocfilehash: 96c2c94bde12e6b8b77060a82f1990b673421de9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="e2aff-102">Lync Server 2013 のパッシブ認証の構成</span><span class="sxs-lookup"><span data-stu-id="e2aff-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2aff-103">_**トピックの最終更新日:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="e2aff-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="e2aff-104">次のセクションでは、累積的な更新プログラムで Lync Server 2013 を構成する方法について説明します。7月2013はパッシブ認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e2aff-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="e2aff-105">有効にした場合、2要素認証が有効になっている Lync ユーザーは、累積的な更新プログラム (7 月2013クライアント) で Lync 2013 を使用してサインインするために、物理または仮想スマートカードと有効な PIN を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2aff-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="e2aff-106">ユーザーがサービスレベルでレジストラーと Web サービスのパッシブ認証を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2aff-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="e2aff-107">グローバルレベルでレジストラーと Web サービスのパッシブ認証が有効になっている場合は、累積更新プログラム (7 月2013クライアントデスクトップクライアント) で Lync 2013 を使用してサインインしていないユーザーに対して、組織全体の認証エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2aff-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="e2aff-108">Web サービスの構成</span><span class="sxs-lookup"><span data-stu-id="e2aff-108">Web Service Configuration</span></span>

<span data-ttu-id="e2aff-109">次の手順では、パッシブ認証を有効にするディレクター、エンタープライズプール、Standard Edition サーバー用のカスタム web サービス構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="e2aff-110">**カスタム web サービス構成を作成するには**</span><span class="sxs-lookup"><span data-stu-id="e2aff-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="e2aff-111">累積的な更新プログラム (Lync 管理者アカウントを使用した7月2013のフロントエンドサーバー) で Lync Server 2013 にログインします。</span><span class="sxs-lookup"><span data-stu-id="e2aff-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="e2aff-112">Lync Server 2013 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="e2aff-113">Lync Server 管理シェルコマンドラインから、次のコマンドを実行することによって、パッシブ認証が有効になるディレクター、エンタープライズプール、Standard Edition サーバーごとに新しい Web サービス構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="e2aff-114">WsFedPassiveMetadataUri FQDN の値は、AD FS 2.0 サーバーのフェデレーションサービス名です。</span><span class="sxs-lookup"><span data-stu-id="e2aff-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="e2aff-115">フェデレーションサービス名の値は、AD FS 2.0 管理コンソールで、ナビゲーションウィンドウの [<STRONG>サービス</STRONG>] を右クリックし、[<STRONG>フェデレーションサービスのプロパティの編集</STRONG>] を選択すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2aff-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="e2aff-116">UseWsFedPassiveAuth および WsFedPassiveMetadataUri の値が正しく設定されていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="e2aff-117">クライアントの場合、パッシブ認証は、webticket 認証で最も推奨される認証方法です。</span><span class="sxs-lookup"><span data-stu-id="e2aff-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="e2aff-118">パッシブ認証を有効にするすべてのディレクター、エンタープライズプール、Standard Edition サーバーでは、次のコマンドを実行することによって、Lync Web サービスで他のすべての認証の種類を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2aff-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="e2aff-119">次のコマンドを実行して、他のすべての認証の種類が正常に無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="e2aff-120">プロキシの構成</span><span class="sxs-lookup"><span data-stu-id="e2aff-120">Proxy Configuration</span></span>

<span data-ttu-id="e2aff-121">Lync Web サービスで証明書認証が無効になっている場合、Lync クライアントは、レジストラーサービスへの認証に、Kerberos や NTLM などの優先度の低い認証の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="e2aff-122">ただし、Lync クライアントが webticket を取得できるようにするには、証明書認証が必要ですが、レジストラーサービスについては Kerberos と NTLM を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2aff-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="e2aff-123">次の手順では、パッシブ認証を有効にするエッジプール、エンタープライズプール、Standard Edition サーバーのカスタムプロキシ構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="e2aff-124">**カスタムプロキシ構成を作成するには**</span><span class="sxs-lookup"><span data-stu-id="e2aff-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="e2aff-125">Lync Server 管理シェルコマンドラインから、累積的な更新プログラムを使用して、各 Lync Server 2013 に対して新しいプロキシ構成を作成します。7月2013エッジプール、エンタープライズプール、Standard Edition サーバーを実行することでパッシブ認証が有効になります。次のコマンド:</span><span class="sxs-lookup"><span data-stu-id="e2aff-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="e2aff-126">次のコマンドを実行して、他のすべてのプロキシ認証の種類が正常に無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2aff-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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

