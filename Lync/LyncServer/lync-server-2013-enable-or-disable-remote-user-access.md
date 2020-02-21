---
title: 'Lync Server 2013: リモートユーザーアクセスの有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73381280b2d87ff73daa79162571f1f729086b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="feb8f-102">Lync Server 2013 でのリモートユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="feb8f-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feb8f-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="feb8f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="feb8f-104">リモート ユーザーは、組織内の永続的な Active Directory ID を持つ、組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="feb8f-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="feb8f-105">リモートユーザーは、組織のネットワークに接続されていないときに、仮想プライベートネットワーク (VPN) を使用して、ネットワーク外部から Lync Server にサインインすることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="feb8f-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="feb8f-106">リモート ユーザーには自宅や外出先で作業する従業員のほか、エンタープライズ資格情報を付与された信頼できるベンダーなどのリモート作業者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="feb8f-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="feb8f-107">リモートユーザーに対してリモートユーザーアクセスを有効にした場合、サポートされているリモートユーザーはインターネット経由で接続し、Lync Server を使用して内部ユーザーと共同作業を行うために VPN を使用して接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="feb8f-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="feb8f-p102">リモート ユーザー アクセスをサポートするには、リモート ユーザー アクセスを有効にする必要があります。有効にする場合は、組織全体に対して有効にします。後でリモート ユーザー アクセスを一時的または永久に禁止する場合は、組織に対するリモート ユーザー アクセスを無効にできます。組織に対するリモート ユーザー アクセスを有効または無効にするには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="feb8f-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="feb8f-112">リモート ユーザー アクセスを有効にした時点では、アクセス エッジ サービスを実行するサーバーがリモート ユーザーとの通信をサポートするという指定が行われるだけです。</span><span class="sxs-lookup"><span data-stu-id="feb8f-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="feb8f-113">あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="feb8f-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="feb8f-114">Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。</span><span class="sxs-lookup"><span data-stu-id="feb8f-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="feb8f-115">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="feb8f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="feb8f-116">リモートユーザーアクセスを使用するためのポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを制御するようにポリシーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb8f-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="feb8f-117">組織に対するリモート ユーザー アクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="feb8f-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="feb8f-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="feb8f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="feb8f-119">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="feb8f-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="feb8f-120">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb8f-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="feb8f-121">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="feb8f-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="feb8f-122">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="feb8f-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="feb8f-123">[**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="feb8f-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="feb8f-124">組織に対してリモート ユーザー アクセスを有効にするには、[**リモート ユーザー アクセスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="feb8f-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="feb8f-125">組織に対してリモート ユーザー アクセスを無効にするには、[**リモート ユーザー アクセスを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="feb8f-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="feb8f-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="feb8f-126">Click **Commit**.</span></span>

<span data-ttu-id="feb8f-127">リモートユーザーが Lync Server を実行しているサーバーにサインインできるようにするには、リモートユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feb8f-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="feb8f-128">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 でリモートユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb8f-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="feb8f-129">Windows PowerShell コマンドレットを使用してリモートユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="feb8f-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="feb8f-130">リモートユーザーアクセスを管理するには、Windows PowerShell と Set-csaccessedgeconfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="feb8f-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="feb8f-131">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="feb8f-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="feb8f-132">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb8f-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="feb8f-133">リモートユーザーアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="feb8f-133">To enable remote user access</span></span>

  - <span data-ttu-id="feb8f-134">リモート ユーザー アクセスを有効にするには、**AllowOutsideUsers** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="feb8f-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="feb8f-135">リモートユーザーアクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="feb8f-135">To disable remote user access</span></span>

  - <span data-ttu-id="feb8f-136">リモート ユーザー アクセスを無効にするには、**AllowOutsideUsers** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="feb8f-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

