---
title: 'Lync Server 2013: リモート通話コントロールの静的ルートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535574a47a9ea77b5db20e45dcdcbb62fab2e4b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="c6971-102">Lync Server 2013 でリモート通話コントロールの静的ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="c6971-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6971-103">_**トピックの最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="c6971-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="c6971-104">リモート通話コントロールを使用するには、すべての Lync Server プールが、そのプールから、構内交換 (PBX) に接続する SIP/CSTA ゲートウェイへのパスで構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6971-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="c6971-105">このパスでは、各プールに、PBX への通話に関連付けられた SIP 通話制御メッセージをプロキシする、各ゲートウェイに対して1つの静的ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6971-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="c6971-106">リモート通話コントロールのグローバル静的ルートを構成する場合、プールレベルで静的ルートを使用して構成されていない各プールは、グローバル静的ルートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6971-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="c6971-107">リモート通話コントロール用の静的ルートを構成するには</span><span class="sxs-lookup"><span data-stu-id="c6971-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="c6971-108">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバー、または、**新しい-CsStaticRoute**コマンドレットを割り当てた役割ベースのアクセス制御 (RBAC) の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="c6971-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="c6971-109">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6971-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c6971-110">静的ルートを作成して $TLSRoute または $TCPRoute 変数に挿入するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c6971-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="c6971-p102">ドメインの子ドメインを照合するために、MatchUri パラメーターでワイルドカード値を指定できます。 たとえば、<STRONG>\*.contoso.net</STRONG> と入力すると、 末尾が <STRONG>contoso.net</STRONG> のドメインが照合されます。</span><span class="sxs-lookup"><span data-stu-id="c6971-p102">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter. For example, <STRONG>\*.contoso.net</STRONG>. That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="c6971-114">トランスポート層セキュリティ (TLS) 接続の場合、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c6971-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="c6971-115">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6971-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="c6971-116">UseDefaultCertificate を False に設定する場合、TLSCertIssuer および TLSCertSerialNumber パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6971-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="c6971-117">これらのパラメーターは、それぞれ、静的ルートで使用される証明書を発行した証明機関 (CA) の名前とその TLS 証明書のシリアル番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6971-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="c6971-118">これらのパラメーターの詳細については、コマンドプロンプトで次のように入力して、「Lync Server Management Shell Help」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6971-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="c6971-119">伝送制御プロトコル (TCP) 接続の場合、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c6971-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="c6971-120">完全修飾ドメイン名 (FQDN) を指定する場合は、まず、ドメイン ネーム システム (DNS) A レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6971-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="c6971-121">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6971-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="c6971-122">以下では、静的ルートのオプション パラメーターの既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="c6971-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="c6971-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="c6971-123">Enabled = True</span></span>
        
          - <span data-ttu-id="c6971-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="c6971-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="c6971-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="c6971-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="c6971-126">これらの既定値は変更しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6971-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="c6971-127">ただし、これらのパラメーターのいずれかを変更する必要がある場合は、コマンドプロンプトで次のように入力して、「Lync Server Management Shell Help」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6971-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="c6971-128">中央管理ストアで新しく作成された静的ルートを保持するには、必要に応じて次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6971-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6971-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6971-129">See Also</span></span>


[<span data-ttu-id="c6971-130">Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する</span><span class="sxs-lookup"><span data-stu-id="c6971-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="c6971-131">Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義</span><span class="sxs-lookup"><span data-stu-id="c6971-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

