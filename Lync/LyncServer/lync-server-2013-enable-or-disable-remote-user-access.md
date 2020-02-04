---
title: 'Lync Server 2013: リモート ユーザー アクセスの有効化または無効化'
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
ms.openlocfilehash: 476cc3b90a2fdb603303789f3f9bfceb67766f5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="d8e00-102">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="d8e00-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8e00-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d8e00-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d8e00-104">リモートユーザーは組織内のユーザーで、組織内に Active Directory id が固定されています。</span><span class="sxs-lookup"><span data-stu-id="d8e00-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="d8e00-105">リモートユーザーは、組織のネットワークに接続されていないときに仮想プライベートネットワーク (VPN) を使用して、ネットワークの外部から Lync Server にサインインすることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d8e00-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="d8e00-106">リモートユーザーには、自宅や外出先で作業している従業員や、信頼できるベンダーなど、企業の資格情報が付与されている信頼できる社員が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8e00-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="d8e00-107">リモートユーザーに対してリモートユーザーアクセスを有効にすると、サポートされているリモートユーザーはインターネット経由で接続し、Lync Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8e00-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="d8e00-108">リモートユーザーアクセスをサポートするには、リモートユーザーアクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e00-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="d8e00-109">リモートユーザーアクセスを有効にすると、組織全体で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8e00-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="d8e00-110">後でリモートユーザーのアクセスを一時的または完全に禁止する必要がある場合は、組織に対して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8e00-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="d8e00-111">組織のリモートユーザーアクセスを有効または無効にするには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8e00-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8e00-112">リモートユーザーアクセスを有効にすることは、アクセスエッジサービスを実行しているサーバーがリモートユーザーとの通信をサポートしていることを示しますが、リモートユーザーは、を構成するまで、組織内のインスタントメッセージング (IM) または会議に参加することはできません。リモートユーザーアクセスの使用を管理するためのポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="d8e00-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="d8e00-113">1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8e00-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d8e00-114">Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="d8e00-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d8e00-115">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="d8e00-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="d8e00-116">リモートユーザーアクセスを使用するためのポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e00-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="d8e00-117">組織のリモートユーザーアクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="d8e00-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="d8e00-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d8e00-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8e00-119">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8e00-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d8e00-120">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d8e00-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d8e00-121">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8e00-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="d8e00-122">[**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8e00-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d8e00-123">[ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8e00-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="d8e00-124">組織のリモートユーザーアクセスを有効にするには、[**リモートユーザーアクセスを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d8e00-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="d8e00-125">組織のリモートユーザーアクセスを無効にするには、[**リモートユーザーアクセスを有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d8e00-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="d8e00-126">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8e00-126">Click **Commit**.</span></span>

<span data-ttu-id="d8e00-127">リモートユーザーが Lync Server を実行しているサーバーにサインインできるようにするには、リモートユーザーのアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e00-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="d8e00-128">詳細については、「展開ドキュメントまたは運用ドキュメントの「 [Lync Server 2013 でリモートユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e00-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d8e00-129">Windows PowerShell コマンドレットを使用したリモートユーザーアクセスの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="d8e00-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d8e00-130">リモートユーザーアクセスを管理するには、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8e00-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d8e00-131">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8e00-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d8e00-132">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e00-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="d8e00-133">リモートユーザーアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d8e00-133">To enable remote user access</span></span>

  - <span data-ttu-id="d8e00-134">リモートユーザーアクセスを有効にするには、 **Allowoutsideusers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d8e00-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="d8e00-135">リモートユーザーアクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="d8e00-135">To disable remote user access</span></span>

  - <span data-ttu-id="d8e00-136">リモートユーザーアクセスを無効にするには、 **Allowoutsideusers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d8e00-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

