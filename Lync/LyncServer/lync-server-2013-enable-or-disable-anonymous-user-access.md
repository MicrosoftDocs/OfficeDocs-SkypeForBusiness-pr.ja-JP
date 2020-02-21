---
title: 'Lync Server 2013: 匿名ユーザーアクセスの有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 076cfd8b787c85ba94d3538c5510d7c12ca11b22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="2d9af-102">Lync Server 2013 で匿名ユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="2d9af-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d9af-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2d9af-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2d9af-104">匿名ユーザーは、組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインにユーザーアカウントを持たないユーザーですが、社内の会議にリモートで参加するよう招待することができます。</span><span class="sxs-lookup"><span data-stu-id="2d9af-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="2d9af-105">会議への匿名参加を許可することにより、匿名ユーザー (つまり、会議キーまたは会議キーで本人のみが確認されるユーザー) が会議に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2d9af-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="2d9af-106">匿名参加を許可するには、組織に対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d9af-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="2d9af-107">後で匿名ユーザーによるアクセスを一時的または完全に禁止する場合は、組織に対して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d9af-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="2d9af-108">このセクションの手順を使用して、組織の匿名ユーザーアクセスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d9af-109">組織で匿名ユーザーアクセスを有効にすることで、アクセスエッジサービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートすることを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="2d9af-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="2d9af-110">匿名ユーザーは、少なくとも1つの会議ポリシーを構成して、1人以上のユーザーまたはユーザーグループに適用するまでは、組織内のすべての会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="2d9af-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="2d9af-111">匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成された会議ポリシーが割り当てられているユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="2d9af-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="2d9af-112">匿名ユーザーの招待をサポートするための会議ポリシーの構成の詳細については、「 <A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 の会議ポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9af-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="2d9af-113">組織の匿名ユーザーアクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="2d9af-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="2d9af-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d9af-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d9af-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2d9af-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9af-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2d9af-117">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="2d9af-118">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2d9af-119">[**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2d9af-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="2d9af-120">組織で匿名ユーザーアクセスを有効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="2d9af-121">組織の匿名ユーザーアクセスを無効にするには、[**匿名ユーザーとの通信を有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="2d9af-122">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d9af-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d9af-123">Windows PowerShell コマンドレットを使用して匿名ユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="2d9af-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2d9af-124">匿名ユーザーアクセスを管理するには、Windows PowerShell と**set-csaccessedgeconfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9af-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="2d9af-125">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2d9af-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2d9af-126">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9af-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="2d9af-127">匿名ユーザーアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="2d9af-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="2d9af-128">匿名ユーザーアクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d9af-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="2d9af-129">匿名ユーザーアクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="2d9af-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="2d9af-130">匿名ユーザーアクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d9af-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d9af-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d9af-131">See Also</span></span>


[<span data-ttu-id="2d9af-132">Lync Server 2013 の会議ポリシー設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="2d9af-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

