---
title: Lync Server パブリック IM 接続プロビジョニングサイトへのアクセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44692fd6267e23c98ecef1ca227cbde5289a44b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="646ed-102">Lync server 2013 からの Lync Server パブリック IM 接続プロビジョニングサイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="646ed-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="646ed-103">_**トピックの最終更新日:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="646ed-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="646ed-104">以前の PIC プロビジョニング方法と比較して、Lync と Skype の接続のプロビジョニングプロセスが変更されました。</span><span class="sxs-lookup"><span data-stu-id="646ed-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="646ed-105">このプロビジョニングプロセスは、完了するまでに最大で30日間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="646ed-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="646ed-106">このドキュメントの残りの手順を完了する前に、このプロセスを最初に開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="646ed-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="646ed-107">アカウントに対して Lync-Skype のプロビジョニングプロセスが完了すると、アカウントがアクティブ化され、対象ユーザーがパブリック IM 接続を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="646ed-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="646ed-108">Lync と Skype の接続をプロビジョニングするには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="646ed-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="646ed-109">Microsoft 契約番号</span><span class="sxs-lookup"><span data-stu-id="646ed-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="646ed-110">アクセスエッジサービスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="646ed-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="646ed-111">セッション開始プロトコル (SIP) ドメイン</span><span class="sxs-lookup"><span data-stu-id="646ed-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="646ed-112">追加のアクセスエッジサービスの Fqdn</span><span class="sxs-lookup"><span data-stu-id="646ed-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="646ed-113">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="646ed-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="646ed-114">2019年4月から、pic.lync.com web サイトを介して Skype フェデレーションを準備されているお客様の連絡先情報の収集と保存を停止します。</span><span class="sxs-lookup"><span data-stu-id="646ed-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="646ed-115">この変更は、pic.lync.com プロビジョニングシステムが Microsoft プライバシーポリシーに準拠していることを確認するために行われます。</span><span class="sxs-lookup"><span data-stu-id="646ed-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="646ed-116">この変更が有効になると、保留中のプロビジョニング変更に対する電子メール更新を提供することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="646ed-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="646ed-117">PIC プロビジョニングの変更は、通常、入力されてから24-48 時間以内に完了します。</span><span class="sxs-lookup"><span data-stu-id="646ed-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="646ed-118">準備要求の提出後、Skype フェデレーションの問題が依然として48時間発生している場合は、さらに詳しく調査するために Microsoft テクニカルサポートにご協力ください。</span><span class="sxs-lookup"><span data-stu-id="646ed-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="646ed-119">この変更の一環として、以前に入力したすべての連絡先情報は、2019年4月の終了後にシステムから削除されます。</span><span class="sxs-lookup"><span data-stu-id="646ed-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="646ed-120">Lync と Skype の接続のプロビジョニングプロセスを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="646ed-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="646ed-121">Microsoft Windows Live ID を使用<strong>https://pic.lync.com</strong>して、web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="646ed-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="646ed-122">[Microsoft ライセンス契約の種類] を選択します。</span><span class="sxs-lookup"><span data-stu-id="646ed-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="646ed-123">このチェックボックスをオンにして、Lync Server の製品使用権を読んで同意していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="646ed-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="646ed-124">[<strong>プロビジョニング要求を開始</strong>する] ページで、適切なリンクをクリックしてプロビジョニング要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="646ed-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="646ed-125">[<strong>プロビジョニング情報の指定</strong>] ページで、<strong>アクセスエッジサービスの FQDN</strong>を入力します。</span><span class="sxs-lookup"><span data-stu-id="646ed-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="646ed-126">たとえば、 <strong>sip.contoso.com</strong>のようになります。</span><span class="sxs-lookup"><span data-stu-id="646ed-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="646ed-127">2017年7月1日以降、Microsoft は、パブリック IM 接続用に展開されたフェデレーション DNS SRV レコードを使用して引き続き作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="646ed-128">少なくとも1つの SIP ドメイン名を入力し、[<strong>追加</strong>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="646ed-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="646ed-129">プロビジョニングプロセスを完了するには、少なくとも1つのアクセスエッジサーバーと1つの SIP ドメインが必要です。</span><span class="sxs-lookup"><span data-stu-id="646ed-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="646ed-130">SIP ドメインとアクセスエッジサーバーが、ネットワーク上でアクティブで、機能していて、到達可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="646ed-131"><strong>パブリック IM サービスプロバイダー</strong>の一覧で、[ <strong>Skype]</strong>を選択し、[<strong>次</strong>へ] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="646ed-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="646ed-132">プロビジョニング要求を送信した後は、アカウントがアクティブ化され、ユーザーがパブリック IM 接続を有効にするには、最大で30日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="646ed-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="646ed-133">フェデレーションとパブリック IM 接続の有効化 (PIC)</span><span class="sxs-lookup"><span data-stu-id="646ed-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="646ed-134">プロビジョニング要求を送信した後で、lync Server 環境と Lync-Skype 接続を構成するために必要な管理タスクに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="646ed-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="646ed-135">このセクションでは、Lync server 管理者が Lync Server を展開し、外部アクセスを構成したと仮定します。</span><span class="sxs-lookup"><span data-stu-id="646ed-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="646ed-136">Lync Server の外部アクセスの構成の詳細については、「」の「外部ユーザー [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772)アクセスを計画する」と「外部[https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)ユーザーアクセスを展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ed-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="646ed-137">Lync server 環境で Lync と Skype の接続を準備するには、Lync Server 管理者が次の3つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="646ed-138">1\.</span><span class="sxs-lookup"><span data-stu-id="646ed-138">1\.</span></span> <span data-ttu-id="646ed-139">フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="646ed-139">Configure Federation and PIC</span></span>

<span data-ttu-id="646ed-140">Skype ユーザーが組織内の Lync ユーザーと通信できるようにするには、フェデレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="646ed-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="646ed-141">パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="646ed-142">フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="646ed-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="646ed-143">PIC フェデレーションは、Live Communications Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="646ed-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="646ed-144">PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="646ed-145">2\.</span><span class="sxs-lookup"><span data-stu-id="646ed-145">2\.</span></span> <span data-ttu-id="646ed-146">フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="646ed-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="646ed-147">Lync Server コントロールパネルを使用すると、管理者は1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="646ed-148">3\.</span><span class="sxs-lookup"><span data-stu-id="646ed-148">3\.</span></span> <span data-ttu-id="646ed-149">Lync の Skype PIC プロバイダー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="646ed-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="646ed-150">Lync Server 管理シェルを使用して、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ed-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="646ed-151">パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順の手順 2) を構成するまで、組織内の IM または会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="646ed-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="646ed-152">フェデレーションと PIC を構成するには、「」の「フェデレーションとパブリック IM 接続<A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>を有効または無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ed-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="646ed-153">フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成するには、「」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>の「パブリックユーザーアクセスを制御するようにポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ed-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="646ed-154">Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="646ed-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="646ed-155">次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="646ed-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="646ed-156">環境に PIC プロバイダがなく、新しい PIC プロバイダを作成している場合は、 <STRONG>enable-cspublicprovider</STRONG>コマンドレットを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="646ed-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="646ed-157">Lync Server 2013 CU5 &amp; lync desktop Client in OFFICE 2013 SP1 では、NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、lync ユーザーが skype の連絡先を追加することによって、Microsoft 以外 @msn のドメインを識別して skype 形式にルーティングする必要がある状況を改善しました ()。</span><span class="sxs-lookup"><span data-stu-id="646ed-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="646ed-158">これらの新しい設定では、NameDecorationRoutingDomain (msn.com に設定する必要があります) の [Skype 連絡先の追加] ダイアログボックスで、ユーザーの入力を自動的に書式設定することができます (NameDecorationExcludedDomainList 内のドメインが含まれていない場合)。現時点では、msn.com、live.com、Hotmail.com、outlook.com) をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="646ed-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="646ed-159">Lync クライアントから、PIC プロバイダーとして Skype を選択し、Microsoft アカウントを指定して Skype クライアントを追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="646ed-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="646ed-160">また、Microsoft アカウントを使用して合併およびログインした Skype ユーザーは、Lync ユーザーに対して連絡先要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="646ed-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="646ed-161">Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ed-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="646ed-162">Lync にクライアントを追加する方法の詳細については、「lync [Server 2013 でのエンドユーザーとしての lync 接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ed-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="646ed-163">ホストされるプロバイダーの変更の詳細については、「」の「ホストさ[https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)れた SIP フェデレーションプロバイダーを作成または編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ed-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="646ed-164">これで、サーバー上で実行する必要のある管理タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="646ed-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="646ed-165">これで、Lync と Skype の接続が設定されました。</span><span class="sxs-lookup"><span data-stu-id="646ed-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="646ed-166">追加情報</span><span class="sxs-lookup"><span data-stu-id="646ed-166">Additional Resources</span></span>

[<span data-ttu-id="646ed-167">エンドユーザーとしての lync Server 2013 での Lync と Skype の接続の使用</span><span class="sxs-lookup"><span data-stu-id="646ed-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="646ed-168">Lync Server 2013 での Lync と Skype の接続のプロビジョニングガイド</span><span class="sxs-lookup"><span data-stu-id="646ed-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

