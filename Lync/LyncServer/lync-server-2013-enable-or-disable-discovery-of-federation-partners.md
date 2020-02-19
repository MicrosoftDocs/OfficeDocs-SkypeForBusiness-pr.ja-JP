---
title: 'Lync Server 2013: フェデレーションパートナーの検出の有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ea73efafb912ad5c1e6dfa6b61b74eb9c817403
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="2c81b-102">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="2c81b-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c81b-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2c81b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2c81b-p101">エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。 このトピックの手順を使用して、この構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="2c81b-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c81b-106">次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2c81b-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="2c81b-107">フェデレーションを有効にする方法の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c81b-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="2c81b-108">組織に対してフェデレーション ドメインの自動検出を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="2c81b-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="2c81b-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2c81b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2c81b-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2c81b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c81b-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c81b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2c81b-112">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c81b-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="2c81b-113">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c81b-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2c81b-114">[**アクセス エッジ構成の編集**] で、[**フェデレーション ユーザーとの通信を有効にする**] の [**パートナー ドメインの検出を有効にする**] チェック ボックスをオンまたはオフにして、パートナー ドメインの自動検出を有効また無効にします。</span><span class="sxs-lookup"><span data-stu-id="2c81b-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="2c81b-115">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c81b-115">Click **Commit**.</span></span>

<span data-ttu-id="2c81b-116">フェデレーションユーザーが Lync Server 展開内のユーザーと共同作業できるようにするには、フェデレーションユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c81b-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="2c81b-117">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 でのフェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c81b-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="2c81b-118">特定のフェデレーションドメインのアクセス制御の詳細については、「操作」のドキュメントの「 [MANAGE sip フェデレーションドメイン](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)を lync server 2013 で管理する」、「[組織の sip フェデレーションプロバイダーを lync server 2013 で管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)する」、および「 [LYNC server 2013 で Xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c81b-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2c81b-119">Windows PowerShell コマンドレットを使用したフェデレーションパートナーの検出の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="2c81b-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2c81b-120">フェデレーションパートナーの検出は、Windows PowerShell と Set-csaccessedgeconfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="2c81b-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="2c81b-121">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c81b-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2c81b-122">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c81b-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="2c81b-123">フェデレーションパートナーの検出を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2c81b-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="2c81b-124">フェデレーションパートナーの検出を有効にするには、 **Enablepartnerdiscovery**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c81b-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="2c81b-125">このプロパティの値を変更するには、DNS SRV ルーティングを有効にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c81b-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="2c81b-126">フェデレーションパートナーの検出を無効にするには</span><span class="sxs-lookup"><span data-stu-id="2c81b-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="2c81b-127">フェデレーションパートナーの検出を無効にするには、 **Enablepartnerdiscovery**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c81b-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

