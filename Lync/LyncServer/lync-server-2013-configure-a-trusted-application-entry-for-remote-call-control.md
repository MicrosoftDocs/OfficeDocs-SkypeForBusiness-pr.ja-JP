---
title: リモート通話コントロールの信頼済みアプリケーション エントリを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="9a9ba-102">Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する</span><span class="sxs-lookup"><span data-stu-id="9a9ba-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a9ba-103">_**最終更新日:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="9a9ba-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="9a9ba-104">Lync Server で着信をルーティングするために静的ルートを適用するには、SIP/CSTA ゲートウェイが信頼済みアプリケーションとして構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9a9ba-105">以前のバージョンの Lync Server 展開からユーザーを移行する場合は、次の手順を実行する前に、SIP/CSTA ゲートウェイ用に作成した既存の信頼済みアプリケーションエントリ (以前は承認済みのホストエントリ) をすべて削除していることを確認してください。このトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="9a9ba-106">詳細については、「 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013 で従来の承認済みホストを削除する (オプション)</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="9a9ba-107">伝送制御プロトコル (TCP) 接続を使用して新しいリモート通話コントロールを展開する予定がある場合は、同じように、既存の信頼できるアプリケーションとプールで [<STRONG>サービスの利用制限</STRONG>を設定する] をオンにする必要があります。新しい信頼済みアプリケーションの TCP ポート。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="9a9ba-108">SIP/CSTA ゲートウェイの信頼されたアプリケーションエントリを構成するには</span><span class="sxs-lookup"><span data-stu-id="9a9ba-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="9a9ba-109">Lync Server 管理シェルが、RTCUniversalServerAdmins グループのメンバーとして、または**CsTrustedApplicationPool**コマンドレットを割り当てた役割ベースのアクセス制御 (RBAC) ロールとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="9a9ba-110">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a9ba-111">信頼できるアプリケーションエントリを作成するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="9a9ba-112">トランスポート層セキュリティ (TLS) 接続の場合は、コマンドプロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="9a9ba-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="9a9ba-114">伝送制御プロトコル (TCP) 接続の場合は、コマンドプロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="9a9ba-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="9a9ba-116">信頼できるアプリケーションをプールに追加するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="9a9ba-117">TLS 接続の場合は、コマンドプロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="9a9ba-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="9a9ba-119">TCP 接続の場合は、コマンドプロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="9a9ba-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="9a9ba-121">トポロジに加えた公開された変更を実装するには、コマンドプロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a9ba-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a9ba-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a9ba-122">See Also</span></span>


[<span data-ttu-id="9a9ba-123">Lync Server 2013 でのリモート通話コントロールの静的ルートの構成</span><span class="sxs-lookup"><span data-stu-id="9a9ba-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="9a9ba-124">Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義</span><span class="sxs-lookup"><span data-stu-id="9a9ba-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

