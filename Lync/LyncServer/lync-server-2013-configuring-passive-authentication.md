---
title: 'Lync Server 2013: パッシブ認証の構成'
description: 'Lync Server 2013: パッシブ認証の構成。'
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
ms.openlocfilehash: 52a83c1413dcac18fb37ff0fe308266a3d7aeab4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548293"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="5db2d-103">Lync Server 2013 のパッシブ認証の構成</span><span class="sxs-lookup"><span data-stu-id="5db2d-103">Configuring Lync Server 2013 passive authentication</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db2d-104">_**トピックの最終更新日:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="5db2d-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="5db2d-105">次のセクションでは、累積的な更新プログラムで Lync Server 2013 を構成する方法について説明します。7月2013はパッシブ認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5db2d-105">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="5db2d-106">有効にした場合、2要素認証が有効になっている Lync ユーザーは、累積的な更新プログラム (7 月2013クライアント) で Lync 2013 を使用してサインインするために、物理または仮想スマートカードと有効な PIN を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db2d-106">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5db2d-107">ユーザーがサービスレベルでレジストラーと Web サービスのパッシブ認証を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5db2d-107">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="5db2d-108">グローバルレベルでレジストラーと Web サービスのパッシブ認証が有効になっている場合は、累積更新プログラム (7 月2013クライアントデスクトップクライアント) で Lync 2013 を使用してサインインしていないユーザーに対して、組織全体の認証エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5db2d-108">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="5db2d-109">Web サービスの構成</span><span class="sxs-lookup"><span data-stu-id="5db2d-109">Web Service Configuration</span></span>

<span data-ttu-id="5db2d-110">次の手順では、パッシブ認証を有効にするディレクター、エンタープライズプール、Standard Edition サーバー用のカスタム web サービス構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-110">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="5db2d-111">**カスタム web サービス構成を作成するには**</span><span class="sxs-lookup"><span data-stu-id="5db2d-111">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="5db2d-112">累積的な更新プログラム (Lync 管理者アカウントを使用した7月2013のフロントエンドサーバー) で Lync Server 2013 にログインします。</span><span class="sxs-lookup"><span data-stu-id="5db2d-112">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="5db2d-113">Lync Server 2013 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-113">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="5db2d-114">Lync Server 管理シェルコマンドラインから、次のコマンドを実行することによって、パッシブ認証が有効になるディレクター、エンタープライズプール、Standard Edition サーバーごとに新しい Web サービス構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-114">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="5db2d-115">WsFedPassiveMetadataUri FQDN の値は、AD FS 2.0 サーバーのフェデレーションサービス名です。</span><span class="sxs-lookup"><span data-stu-id="5db2d-115">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="5db2d-116">フェデレーションサービス名の値は、AD FS 2.0 管理コンソールで、ナビゲーションウィンドウの [ <STRONG>サービス</STRONG> ] を右クリックし、[ <STRONG>フェデレーションサービスのプロパティの編集</STRONG>] を選択すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="5db2d-116">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="5db2d-117">UseWsFedPassiveAuth および WsFedPassiveMetadataUri の値が正しく設定されていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-117">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="5db2d-118">クライアントの場合、パッシブ認証は、webticket 認証で最も推奨される認証方法です。</span><span class="sxs-lookup"><span data-stu-id="5db2d-118">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="5db2d-119">パッシブ認証を有効にするすべてのディレクター、エンタープライズプール、Standard Edition サーバーでは、次のコマンドを実行することによって、Lync Web サービスで他のすべての認証の種類を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db2d-119">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="5db2d-120">次のコマンドを実行して、他のすべての認証の種類が正常に無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-120">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="5db2d-121">プロキシの構成</span><span class="sxs-lookup"><span data-stu-id="5db2d-121">Proxy Configuration</span></span>

<span data-ttu-id="5db2d-122">Lync Web サービスで証明書認証が無効になっている場合、Lync クライアントは、レジストラーサービスへの認証に、Kerberos や NTLM などの優先度の低い認証の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-122">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="5db2d-123">ただし、Lync クライアントが webticket を取得できるようにするには、証明書認証が必要ですが、レジストラーサービスについては Kerberos と NTLM を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db2d-123">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="5db2d-124">次の手順では、パッシブ認証を有効にするエッジプール、エンタープライズプール、Standard Edition サーバーのカスタムプロキシ構成を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-124">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="5db2d-125">**カスタムプロキシ構成を作成するには**</span><span class="sxs-lookup"><span data-stu-id="5db2d-125">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="5db2d-126">Lync Server 管理シェルコマンドラインから、累積的な更新プログラム (次のコマンドを実行することにより、7月2013エッジプール、エンタープライズプール、Standard Edition サーバー) 2013 の新しいプロキシ構成を作成し、パッシブ認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5db2d-126">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="5db2d-127">次のコマンドを実行して、他のすべてのプロキシ認証の種類が正常に無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5db2d-127">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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

