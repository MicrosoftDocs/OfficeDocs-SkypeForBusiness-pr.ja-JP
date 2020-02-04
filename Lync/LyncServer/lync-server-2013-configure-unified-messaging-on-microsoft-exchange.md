---
title: 'Lync Server 2013: Microsoft Exchange でユニファイドメッセージングを構成する'
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
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="77928-102">Lync Server 2013 向けの Microsoft Exchange でユニファイドメッセージングを構成する</span><span class="sxs-lookup"><span data-stu-id="77928-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77928-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="77928-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="77928-104">このトピックでは、エンタープライズ Voip で使用するために Microsoft Exchange Server で Exchange ユニファイドメッセージング (UM) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77928-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77928-105">このトピックのコマンドレットの例では、exchange 管理シェルの Exchange 2007 バージョンの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="77928-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="77928-106">Exchange 2010 または Exchange 2013 を実行している場合は、参照されている適切なドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="77928-107">Exchange Server UM を実行しているサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="77928-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="77928-108">各エンタープライズボイスの場所プロファイルに対して、UM セッション開始プロトコル (SIP) の URI ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="77928-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="77928-109">Exchange 管理コンソールを使用する場合は、セキュリティ設定がセキュリティ設定されている新しいダイヤルプランを作成します **(推奨)**。</span><span class="sxs-lookup"><span data-stu-id="77928-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="77928-110">セキュリティ設定の値を<STRONG>Sip セキュリティ</STRONG>に設定して、sip トラフィックのみの暗号化を必須にする場合は、前に説明したように、フロントエンドプールが暗号化を要求するように構成されている場合は、ダイヤルプランに対するこのセキュリティ設定は不十分であることに注意してください。つまり、プールは SIP と RTP の両方のトラフィックに</span><span class="sxs-lookup"><span data-stu-id="77928-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="77928-111">ダイヤルプランとプールのセキュリティ設定に互換性がない場合は、フロントエンドプールからの Exchange UM へのすべての呼び出しが失敗し、"互換性のないセキュリティ設定" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77928-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="77928-112">Exchange 管理シェルを使用している場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77928-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="77928-113">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-113">For details, see:</span></span>
    
      - <span data-ttu-id="77928-114">Office Communications Server 2007 については、「at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and UMDialplan: Exchange 2007 のヘルプ」で[http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)「ユニファイドメッセージング SIP URI ダイヤルプランを作成する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="77928-115">Exchange 2010 については、「at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674)と "New-UMDialplan: exchange 2010 のヘルプ" の「UM ダイヤル[http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)プランを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="77928-116">Exchange 2013 については、の「ユニファイ[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)ドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77928-117"><STRONG>SIPSecured</STRONG>または secure のセキュリティレベルを選択するかどうかは、セキュリティで保護されたリアルタイムトランスポートプロトコル (srtp) がメディア暗号化に対してアクティブ化されているか、無効になっているか<STRONG>によって</STRONG>異なります。</span><span class="sxs-lookup"><span data-stu-id="77928-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="77928-118">Lync Server 2010 と Exchange UM との統合については、Lync Server メディア構成の暗号化レベルに対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="77928-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="77928-119">Lync Server のメディア構成を表示するには、 <STRONG>CsMediaConfiguration</STRONG>コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="77928-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="77928-120">詳細については、「Lync Server 管理シェルドキュメントの CsMediaConfiguration」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="77928-121">適切な VoIP セキュリティ設定を選ぶ方法について詳しくは、「<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="77928-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="77928-122">次のコマンドレットを実行して、各 UM ダイヤルプランの完全修飾ドメイン名 (FQDN) を取得します。</span><span class="sxs-lookup"><span data-stu-id="77928-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="77928-123">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-123">For details, see:</span></span>
    
      - <span data-ttu-id="77928-124">Exchange 2007 については、「UMDialplan: Exchange 2007 のヘルプ」 [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="77928-125">Exchange 2010 については、「UMDialplan: Exchange 2010 のヘルプ」 [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="77928-126">Exchange 2013 については、の「ユニファイ[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)ドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="77928-127">各 UM ダイヤルプランのダイヤルプラン名を記録します。</span><span class="sxs-lookup"><span data-stu-id="77928-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="77928-128">使用している Exchange Server のバージョンによっては、ダイヤルプラン名が一致するように、各 UM ダイヤルプランの対応する Lync Server ダイヤルプランの名前として、後で各ダイヤルプラン名の FQDN を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="77928-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77928-129">UM ダイヤルプランが Exchange 2010 SP1 より<EM>前</EM>のバージョンの exchange で実行されている場合にのみ、Lync Server のダイヤルプラン名が um ダイヤルプラン名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77928-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="77928-130">次のように、Exchange UM を実行しているサーバーにダイヤルプランを追加します。</span><span class="sxs-lookup"><span data-stu-id="77928-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="77928-131">Exchange 管理コンソールの使用を選択した場合は、サーバーのプロパティシートからダイヤルプランを追加できます。</span><span class="sxs-lookup"><span data-stu-id="77928-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="77928-132">具体的な手順については、Exchange Server の製品に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="77928-133">Exchange 2007 については、at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)の「ユニファイドメッセージングサーバーをダイヤルプランに追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="77928-134">Exchange 2010 については、「の UM サーバーのプロパティを表示または[http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="77928-135">Exchange 2013 については、の「ユニファイ[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)ドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="77928-136">Exchange 管理シェルを使用している場合は、Exchange UM サーバーごとに次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="77928-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77928-137">次の手順を実行する前に、すべてのエンタープライズボイスユーザーが Exchange Server メールボックスで構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="77928-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="77928-138">Exchange 2007 の場合は、にある<A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>exchange Server 2007 TechNet ライブラリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="77928-139">Exchange 2010 の場合は、にある<A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>exchange Server 2010 TechNet ライブラリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="77928-140">手順1で作成したダイヤルプランごとにメールボックスポリシーを指定するときは、既定のポリシーまたは作成したポリシーのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="77928-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="77928-141">[Exchange \<インストールディレクトリ\>\\スクリプト] に移動し、exchange が単一フォレストに展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77928-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="77928-142">または、複数のフォレストに Exchange が展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="77928-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="77928-143">ここで、[フォレスト FQDN の指定は Lync Server が展開されているフォレストを指定します。</span><span class="sxs-lookup"><span data-stu-id="77928-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="77928-144">複数の IP ゲートウェイに関連付けられている UM ダイヤルプランが1つ以上ある場合は、手順6に進みます。</span><span class="sxs-lookup"><span data-stu-id="77928-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="77928-145">ダイヤルプランが1つの IP ゲートウェイのみに関連付けられている場合は、手順6をスキップします。</span><span class="sxs-lookup"><span data-stu-id="77928-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77928-146">Exchucutil を実行し<EM>た後</EM>、必ず<STRONG>Lync Server のフロントエンド</STRONG>サービス (rtcsrv) を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="77928-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="77928-147">そうしないと、Lync Server では、ユニファイドメッセージングはトポロジで検出されません。</span><span class="sxs-lookup"><span data-stu-id="77928-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="77928-148">Exchange 管理シェルまたは Exchange 管理コンソールのいずれかを使用して、ダイヤルプランに関連付けられているすべての IP ゲートウェイ以外の発信通話を無効にします。</span><span class="sxs-lookup"><span data-stu-id="77928-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77928-149">この手順は、外部ユーザーに対して Exchange Server ユニファイドメッセージングを実行しているサーバー (たとえば、再生中のシナリオの場合など) が企業ファイアウォールを確実に通過できるようにするために必要です。</span><span class="sxs-lookup"><span data-stu-id="77928-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77928-150">発信通話を許可する UM IP ゲートウェイを選択するときに、最も多くのトラフィックを処理する可能性が高いものを選択します。</span><span class="sxs-lookup"><span data-stu-id="77928-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="77928-151">Lync Server ディレクターのプールに接続する IP ゲートウェイ経由での送信トラフィックを許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="77928-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="77928-152">また、別のセントラルサイトまたはブランチサイトのプールも避けてください。</span><span class="sxs-lookup"><span data-stu-id="77928-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="77928-153">次のいずれかの方法を使用して、発信した着信が IP ゲートウェイを通過するのをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="77928-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="77928-154">Exchange 管理シェルを使用している場合は、次のコマンドを実行して各 IP ゲートウェイを無効にします。</span><span class="sxs-lookup"><span data-stu-id="77928-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="77928-155">Exchange 2007 については、「Set-UMIPGateway: Exchange 2007 の[http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)ヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="77928-156">Exchange 2010 については、「Set-UMIPGateway: Exchange 2010 の[http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)ヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="77928-157">Exchange 管理コンソールを使用している場合は、[**この IP ゲートウェイ経由で発信する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="77928-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77928-158">UM SIP URI ダイヤルプランが単一の IP ゲートウェイのみに関連付けられている場合は、このゲートウェイ経由での発信通話を許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="77928-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="77928-159">各 Lync Server のダイヤルプランに UM 自動応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="77928-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77928-160">自動応答の名前にスペースを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="77928-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="77928-161">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-161">For details, see:</span></span>
    
      - <span data-ttu-id="77928-162">Exchange 2007 の場合は、「New-UMAutoAttendant: Exchange 2007 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="77928-163">Exchange 2010 の場合は、「New-UMAutoAttendant: Exchange 2010 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="77928-164">エンタープライズ Voip の Lync Server ユーザーを有効にし、SIP Uri を知ったら、各ユーザーに対して次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77928-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="77928-165">UM ダイヤルプランを使用して、Exchange UM ユーザー (Exchange メールボックスで構成する必要がある各ユーザー) を関連付け、各ユーザーの SIP URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="77928-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77928-166">次のサンプルの<STRONG>SIPResourceIdentifier</STRONG>は、Lync Server ユーザーの SIP アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="77928-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="77928-167">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-167">For details, see:</span></span>
    
      - <span data-ttu-id="77928-168">Exchange 2007 の場合は、「Enable-UMMailbox: Exchange 2007 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="77928-169">Exchange 2010 の場合は、「Enable-UMMailbox: Exchange 2010 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77928-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

