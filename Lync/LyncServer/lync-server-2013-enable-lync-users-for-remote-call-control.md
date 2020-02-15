---
title: 'Lync Server 2013: リモート通話コントロールの Lync ユーザーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baa6f18e92eb284cce8610ba576b30dd6d2f320
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="d4e65-102">Lync Server 2013 で Lync ユーザーのリモート通話コントロールを有効にする</span><span class="sxs-lookup"><span data-stu-id="d4e65-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4e65-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d4e65-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d4e65-104">サーバーベースのインバンドプロビジョニングポリシーを使用して、リモート通話コントロールの Lync ユーザーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d4e65-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="d4e65-105">インバンドプロビジョニングの設定は、Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドラインインターフェイスを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="d4e65-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="d4e65-106">これらのツールは、以前のリリースでグループポリシー設定を管理するために使用された Windows Management Instrumentation (WMI) スナップインに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="d4e65-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="d4e65-107">ユーザーが Lync で独自のリモート通話コントロールの設定を構成できるようにする場合は、 **Line SERVER uri**と**line uri**値を指定せずに、サーバー上のユーザーのリモート通話コントロール設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d4e65-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="d4e65-108">適切な**回線サーバーの uri**と**回線 uri**の値をユーザーに伝えるようにして、これらの設定を構成するための指示をユーザーに提供してください。</span><span class="sxs-lookup"><span data-stu-id="d4e65-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="d4e65-109">Lync Server でリモート通話コントロールを手動で構成する手順については、Microsoft Office web サイトの<http://go.microsoft.com/fwlink/p/?linkid=210132> 「Lync クライアントドキュメント」の「電話のオプションと番号を設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4e65-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="d4e65-110">既存の Communications Server 2007 R2 または Communications Server 2007 の展開を使用している場合、Communicator 2007 R2 および Communicator 2007 クライアントは、side-by-side 移行時にグループポリシーを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="d4e65-111">ただし、ポリシー設定が Lync クライアントに引き継がれるようにするには、対応する Lync Server のインバンドプロビジョニング設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4e65-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4e65-112">ユーザーのリモート通話コントロールを有効にするには、ユーザーに行 URI と回線サーバー URI の両方を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4e65-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="d4e65-113">「 <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 のリモート通話コントロールの展開タスク</A>」で説明されているように、これらの設定には、必ずゲートウェイで必要な構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4e65-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="d4e65-114">回線サーバー URI のドメインが、ゲートウェイへの静的ルートを構成する際に MatchUri パラメーターで指定した宛先ドメインと同じであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4e65-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="d4e65-115">回線 URI は、"TEL:" プレフィックス (たとえば、tel: + 14255550150) を使用して、ユーザーに対して e.164 形式で割り当てられた電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="d4e65-116">内線番号を構成する場合は、tel: + 14255550150; ext = 111 の形式にします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="d4e65-117">以前にユーザーの回線 URI を構成していて、値が変更されていない場合は、リモート通話コントロールに対してユーザーを有効にするときに、回線 URI を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4e65-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="d4e65-118">管理シェルを使用して、Lync で有効になっているユーザーのリモート通話コントロールを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d4e65-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="d4e65-119">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または、**設定-CsUser**コマンドレットを割り当てた役割ベースのアクセス制御の役割としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="d4e65-120">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d4e65-121">**Set-CsUser** コマンドレットを使用して、Lync で有効にされている既存のユーザーのリモート通話コントロールを構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d4e65-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="d4e65-122">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="d4e65-123">Lync Server コントロール パネルを使用して、リモート通話コントロールに対してユーザーを構成するには</span><span class="sxs-lookup"><span data-stu-id="d4e65-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d4e65-124">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4e65-125">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d4e65-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4e65-126">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4e65-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4e65-127">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d4e65-128">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) のアカウント名、SIP アドレス、または必要なユーザーアカウントの回線 Uri (Uniform resource identifier) の全体 (または最初の部分) を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="d4e65-129">表中の変更するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="d4e65-130">**[編集]** メニューの **[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="d4e65-131">**[テレフォニー]** で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="d4e65-132">リモート通話コントロールを有効にして、ユーザーが Lync 2013 から自社の構内交換機 (PBX) 電話を制御できるようにして、PC 間の音声通話と PC 間通話を行うには、[**リモート通話コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="d4e65-133">**[回線 URI]** でユーザーの電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="d4e65-134">**[回線サーバー URI]** で、SIP/CSTA ゲートウェイの SIP URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="d4e65-135">リモート通話コントロールを有効にするが、PC 間の音声通話を無効にし、ユーザーのみが Lync 2013 からの PBX 電話を制御できるようにするには、[**リモート通話コントロールのみ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="d4e65-136">**[回線 URI]** でユーザーの電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="d4e65-137">**[回線サーバー URI]** で、SIP/CSTA ゲートウェイの SIP URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4e65-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="d4e65-138">終了したら、**[確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e65-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

