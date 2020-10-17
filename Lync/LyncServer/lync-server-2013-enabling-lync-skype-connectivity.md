---
title: 'Lync Server 2013: Lync-Skype 接続の有効化'
description: 'Lync Server 2013: Lync-Skype 接続を有効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31856299b05af7d6b8e934d6e9784d1571b7e29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558493"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="74921-103">Lync Server 2013 での Lync-Skype 接続の有効化</span><span class="sxs-lookup"><span data-stu-id="74921-103">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74921-104">_**トピックの最終更新日:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="74921-104">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="74921-105">プロビジョニング要求を送信した後は、Lync Server 環境および Lync-Skype 接続を構成するために必要な管理タスクに集中できます。</span><span class="sxs-lookup"><span data-stu-id="74921-105">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="74921-106">このセクションでは、Lync server 管理者が Lync Server を展開し、外部アクセスを構成したと仮定します。</span><span class="sxs-lookup"><span data-stu-id="74921-106">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="74921-107">Lync Server の外部アクセスの構成の詳細については、「lync server [2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md) 」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74921-107">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="74921-108">Lync server 環境で Lync-Skype 接続を準備するには、Lync Server 管理者が次の3つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74921-108">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="74921-109">1\.</span><span class="sxs-lookup"><span data-stu-id="74921-109">1\.</span></span> <span data-ttu-id="74921-110">フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="74921-110">Configure Federation and PIC</span></span>

<span data-ttu-id="74921-111">Skype ユーザーが組織内の Lync ユーザーと通信できるようにするには、フェデレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="74921-111">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="74921-112">パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74921-112">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="74921-113">フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="74921-113">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="74921-114">![PIC の表示](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC の表示")</span><span class="sxs-lookup"><span data-stu-id="74921-114">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74921-115">PIC フェデレーションは、Live Communications Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="74921-115">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="74921-116">PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。</span><span class="sxs-lookup"><span data-stu-id="74921-116">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="74921-117">2\.</span><span class="sxs-lookup"><span data-stu-id="74921-117">2\.</span></span> <span data-ttu-id="74921-118">フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="74921-118">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="74921-119">Lync Server コントロールパネルを使用すると、管理者は1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74921-119">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="74921-120">![ポリシー](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span><span class="sxs-lookup"><span data-stu-id="74921-120">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="74921-121">3\.</span><span class="sxs-lookup"><span data-stu-id="74921-121">3\.</span></span> <span data-ttu-id="74921-122">Lync の Skype PIC プロバイダー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="74921-122">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="74921-123">Lync Server 管理シェルを使用して、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74921-123">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74921-124">パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために少なくとも1つのポリシー (この手順の前の手順 2) を構成するまで、組織内の IM またはオーディオまたはビデオ会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="74921-124">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="74921-125">フェデレーションと PIC を構成するには、「」の「フェデレーションとパブリック IM 接続を有効または無効にする」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) 。</span><span class="sxs-lookup"><span data-stu-id="74921-125">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="74921-126">フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成するには、「」の「パブリックユーザーアクセスを制御するようにポリシーを構成する」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) 。</span><span class="sxs-lookup"><span data-stu-id="74921-126">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="74921-127">**既存の Messenger または Skype PIC プロバイダーを編集して Skype 用に構成するには**</span><span class="sxs-lookup"><span data-stu-id="74921-127">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="74921-128">Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="74921-128">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="74921-129">次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="74921-129">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74921-130">環境に PIC プロバイダがなく、新しい PIC プロバイダを作成している場合は、 <STRONG>enable-cspublicprovider</STRONG> コマンドレットを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74921-130">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74921-131">Lync Server 2013 CU5 &amp; lync desktop client In Office 2013 SP1 では、NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、lync ユーザーが skype の連絡先を追加することによって、Microsoft 以外 @msn のドメインを識別して skype 形式にルーティングする必要がある状況を改善しました ()。</span><span class="sxs-lookup"><span data-stu-id="74921-131">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="74921-132">これらの新しい設定によって、NameDecorationRoutingDomain (現在は msn.com、live.com、Hotmail.com、outlook.com) のドメインが含まれていない場合は、[Skype 連絡先の追加] ダイアログボックスの [Skype 連絡先の追加] ダイアログボックスで、ユーザーの入力を自動書式設定することができます (msn.com に設定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="74921-132">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="74921-133">Lync クライアントから、PIC プロバイダーとして Skype を選択し、Microsoft アカウントを指定して Skype クライアントを追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74921-133">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="74921-134">また、Microsoft アカウントを使用して合併およびログインした Skype ユーザーは、Lync ユーザーに対して連絡先要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="74921-134">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="74921-135">Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74921-135">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="74921-136">Lync にクライアントを追加する方法の詳細については、「 [Lync Server 2013 でのエンドユーザーとしての Lync-Skype 接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74921-136">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="74921-137">![Skype 連絡先を追加する](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype 連絡先を追加する")</span><span class="sxs-lookup"><span data-stu-id="74921-137">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="74921-138">ホストされるプロバイダーの変更の詳細については、「」の「ホストされた SIP フェデレーションプロバイダーを作成または編集する」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。</span><span class="sxs-lookup"><span data-stu-id="74921-138">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="74921-139">これで、サーバー上で実行する必要のある管理タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="74921-139">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="74921-140">これで Lync-Skype 接続がセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="74921-140">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

