---
title: 'Lync Server 2013: 既存のレジストラー構成設定の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11830fa7047a9a732b10888b392a367dc36451c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534374"
---
# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bf100-102">Lync Server 2013 で既存のレジストラー構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="bf100-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf100-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf100-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf100-104">レジストラーを使用して、プロキシ サーバーの認証プロトコルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf100-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="bf100-105">使用可能なプロトコルの詳細については、「 [Create レジストラー configuration settings In Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf100-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf100-p102">サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。 エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。 これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。 エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf100-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="bf100-110">既存のレジストラーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf100-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="bf100-111">既存のレジストラー構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="bf100-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="bf100-112">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bf100-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bf100-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf100-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf100-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf100-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf100-115">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf100-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="bf100-116">[**レジストラー**] ページでサービスをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf100-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bf100-117">[**レジストラー設定の編集**] で、クライアントの機能や環境内のサポートに合わせて、次のうち 1 つまたは複数を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf100-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="bf100-118">[**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。</span><span class="sxs-lookup"><span data-stu-id="bf100-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="bf100-119">[**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。</span><span class="sxs-lookup"><span data-stu-id="bf100-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="bf100-120">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="bf100-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="bf100-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf100-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

