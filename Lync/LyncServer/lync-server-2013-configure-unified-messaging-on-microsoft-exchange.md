---
title: 'Lync Server 2013: Microsoft Exchange でのユニファイドメッセージングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b39c10a3fb590acc99771663f5f6e23e3c3095e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520224"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="38cdf-102">Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="38cdf-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38cdf-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="38cdf-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="38cdf-104">このトピックでは、エンタープライズ Voip で使用するために Microsoft Exchange Server で Exchange ユニファイドメッセージング (UM) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38cdf-105">このトピックのコマンドレットの例では、exchange 2007 バージョンの Exchange 管理シェルの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="38cdf-106">Exchange 2010 または Exchange 2013 を実行している場合は、参照されている適切なドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="38cdf-107">Exchange Server UM を実行しているサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="38cdf-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="38cdf-108">エンタープライズ Voip の場所のプロファイルごとに、UM セッション開始プロトコル (SIP) の URI (Uniform Resource Identifier) ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="38cdf-109">Exchange 管理コンソールを使用する場合は、セキュリティ設定をセキュリティで **保護 (推奨)** した新しいダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="38cdf-110">セキュリティ設定の値を sip に対してセキュリティで <STRONG>保護</STRONG> された sip に設定した場合は、事前に推奨されているように、フロントエンドプールが暗号化を要求するように構成されている場合は、ダイヤルプランのこのセキュリティ設定が不十分であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="38cdf-111">ダイヤルプランおよびプールのセキュリティ設定に互換性がない場合、フロントエンドプールからの Exchange UM へのすべての呼び出しが失敗し、"互換性のないセキュリティ設定" があることを示すエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="38cdf-112">Exchange 管理シェルを使用する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="38cdf-113">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-113">For details, see:</span></span>
    
      - <span data-ttu-id="38cdf-114">Office Communications Server 2007 については、「ユニファイドメッセージング SIP URI ダイヤルプランを作成する方法」 [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) および「set-umdialplan: Exchange 2007 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="38cdf-115">Exchange 2010 については、「UM ダイヤルプランを作成する」 [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) および「set-umdialplan: Exchange 2010 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-115">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="38cdf-116">Exchange 2013 については、「」の「ユニファイドメッセージング」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-116">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38cdf-117"><STRONG>SIPSecured</STRONG>のセキュリティレベルを選択するか、セキュリティで<STRONG>保護</STRONG>するかは、メディア暗号化に対してセキュリティで保護されたリアルタイム転送プロトコル (srtp) をアクティブ化または非アクティブ化するかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="38cdf-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="38cdf-118">Lync Server 2010 と Exchange UM との統合については、これは Lync Server メディア構成の暗号化レベルに対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="38cdf-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="38cdf-119">Lync Server メディア構成は、 <STRONG>get-csmediaconfiguration</STRONG> コマンドレットを実行すると表示できます。</span><span class="sxs-lookup"><span data-stu-id="38cdf-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="38cdf-120">詳細については、「Lync Server Management Shell」のドキュメントの「Get-CsMediaConfiguration」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="38cdf-121">適切な VoIP セキュリティ設定の選択の詳細については、「 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="38cdf-122">次のコマンドレットを実行して、各 UM ダイヤルプランの完全修飾ドメイン名 (FQDN) を取得します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="38cdf-123">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-123">For details, see:</span></span>
    
      - <span data-ttu-id="38cdf-124">Exchange 2007 については、「Set-umdialplan: Exchange 2007 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="38cdf-125">Exchange 2010 については、「Set-umdialplan: Exchange 2010 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="38cdf-126">Exchange 2013 については、「」の「ユニファイドメッセージング」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-126">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="38cdf-127">各 UM ダイヤルプランのダイヤルプラン名を記録します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="38cdf-128">ご使用の Exchange Server のバージョンによっては、ダイヤルプランの名前が一致するように、各ダイヤルプラン名の FQDN を、各 UM ダイヤルプランの対応する Lync Server ダイヤルプランの名前として後で使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="38cdf-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38cdf-129">Lync Server ダイヤルプラン名は、UM ダイヤルプランが Exchange 2010 SP1 より <EM>前</EM> のバージョンの exchange 上で実行されている場合にのみ、um ダイヤルプラン名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38cdf-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="38cdf-130">Exchange UM を実行しているサーバーに、次のようにダイヤルプランを追加します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="38cdf-131">Exchange 管理コンソールを使用することを選択した場合は、サーバーのプロパティシートからダイヤルプランを追加できます。</span><span class="sxs-lookup"><span data-stu-id="38cdf-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="38cdf-132">具体的な手順については、Exchange Server 製品のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="38cdf-133">Exchange 2007 については、「」の「ユニファイドメッセージングサーバーをダイヤルプランに追加する方法」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="38cdf-134">Exchange 2010 については、「」の「UM サーバーのプロパティを表示または構成する」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="38cdf-135">Exchange 2013 については、「」の「ユニファイドメッセージング」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-135">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="38cdf-136">Exchange 管理シェルを使用する場合は、それぞれの Exchange UM サーバーに対して次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38cdf-137">次の手順を実行する前に、すべてのエンタープライズ Voip ユーザーが Exchange Server メールボックスで構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="38cdf-138">Exchange 2007 については、Exchange Server 2007 TechNet ライブラリの「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="38cdf-139">Exchange 2010 については、Exchange Server 2010 TechNet ライブラリの「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="38cdf-140">手順1で作成した各ダイヤルプランのメールボックスポリシーを指定する場合は、既定のポリシーまたは作成したポリシーのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="38cdf-141">\<Exchange installation directory\> \\ [スクリプト] に移動し、Exchange が単一のフォレストに展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="38cdf-142">Exchange が複数のフォレストに展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="38cdf-143">フォレスト FQDN には、Lync Server を展開するフォレストを指定します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="38cdf-144">複数の IP ゲートウェイに関連付けられている1つまたは複数の UM ダイヤルプランがある場合は、手順6に進みます。</span><span class="sxs-lookup"><span data-stu-id="38cdf-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="38cdf-145">ダイヤルプランが1つの IP ゲートウェイのみに関連付けられている場合は、手順6をスキップします。</span><span class="sxs-lookup"><span data-stu-id="38cdf-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38cdf-146">exchucutil.ps1 を実行した<EM></EM>後で、<STRONG>Lync サーバー フロントエンド</STRONG> サービス (rtcsrv.exe) を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="38cdf-147">それ以外の場合、Lync Server はトポロジ内のユニファイドメッセージングを検出しません。</span><span class="sxs-lookup"><span data-stu-id="38cdf-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="38cdf-148">Exchange 管理シェルまたは Exchange 管理コンソールのいずれかを使用して、各ダイヤルプランに関連付けられている1つを除くすべての IP ゲートウェイの発信呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="38cdf-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38cdf-149">この手順は、Exchange Server ユニファイドメッセージングを実行しているサーバーから外部ユーザーへの発信呼び出しを確実に行うために必要です (たとえば、電話で再生するシナリオの場合と同様)。</span><span class="sxs-lookup"><span data-stu-id="38cdf-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38cdf-150">送信呼び出しを許可する UM IP ゲートウェイを選択するときには、最も多くのトラフィックを処理する可能性があるものを選択します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="38cdf-151">Lync Server director のプールに接続する IP ゲートウェイ経由の送信トラフィックを許可しません。</span><span class="sxs-lookup"><span data-stu-id="38cdf-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="38cdf-152">別の中央サイトまたはブランチサイトにあるプールも避けてください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="38cdf-153">次のいずれかの方法を使用して、発信呼び出しが IP ゲートウェイを通過するのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="38cdf-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="38cdf-154">Exchange 管理シェルを使用する場合は、次のコマンドを実行して各 IP ゲートウェイを無効にします。</span><span class="sxs-lookup"><span data-stu-id="38cdf-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="38cdf-155">Exchange 2007 については、「Set-UMIPGateway: Exchange 2007 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="38cdf-156">Exchange 2010 については、「Set-UMIPGateway: Exchange 2010 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="38cdf-157">Exchange 管理コンソールを使用する場合は、[ **この IP ゲートウェイ経由の送信呼び出しを許可** する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="38cdf-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38cdf-158">UM SIP URI ダイヤルプランが1つの IP ゲートウェイのみに関連付けられている場合は、このゲートウェイ経由の発信呼び出しを許可しません。</span><span class="sxs-lookup"><span data-stu-id="38cdf-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="38cdf-159">各 Lync Server ダイヤルプランに対して UM 自動応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38cdf-160">自動応答の名前にスペースを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="38cdf-161">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-161">For details, see:</span></span>
    
      - <span data-ttu-id="38cdf-162">Exchange 2007 については、「New-UMAutoAttendant: Exchange 2007 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="38cdf-163">Exchange 2010 については、「New-UMAutoAttendant: Exchange 2010 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="38cdf-164">Lync Server ユーザーのエンタープライズ Voip を有効にし、その SIP Uri を認識した後、各ユーザーに対して次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38cdf-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="38cdf-165">UM ダイヤルプランを使用して Exchange UM ユーザー (Exchange のメールボックスで構成する必要がある各ユーザー) を関連付け、各ユーザーの SIP URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="38cdf-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38cdf-166">次の例の <STRONG>SIPResourceIdentifier</STRONG> は、Lync Server ユーザーの SIP アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="38cdf-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="38cdf-167">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38cdf-167">For details, see:</span></span>
    
      - <span data-ttu-id="38cdf-168">Exchange 2007 については、「Enable-UMMailbox: Exchange 2007 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="38cdf-169">Exchange 2010 については、「Enable-UMMailbox: Exchange 2010 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 。</span><span class="sxs-lookup"><span data-stu-id="38cdf-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

