---
title: 'Lync Server 2013: Lync と Skype の接続の有効化'
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
ms.openlocfilehash: d2b950b8ff778ee48014dc951d89baafab59510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="464aa-102">Lync Server 2013 での Lync と Skype の接続の有効化</span><span class="sxs-lookup"><span data-stu-id="464aa-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="464aa-103">_**トピックの最終更新日:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="464aa-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="464aa-104">プロビジョニング要求を送信した後で、lync Server 環境と Lync-Skype 接続を構成するために必要な管理タスクに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="464aa-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="464aa-105">このセクションでは、Lync server 管理者が Lync Server を展開し、外部アクセスを構成したと仮定します。</span><span class="sxs-lookup"><span data-stu-id="464aa-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="464aa-106">Lync Server の外部アクセスの構成の詳細については、「lync server [2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464aa-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="464aa-107">Lync server 環境で Lync と Skype の接続を準備するには、Lync Server 管理者が次の3つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="464aa-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="464aa-108">1\.</span><span class="sxs-lookup"><span data-stu-id="464aa-108">1\.</span></span> <span data-ttu-id="464aa-109">フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="464aa-109">Configure Federation and PIC</span></span>

<span data-ttu-id="464aa-110">Skype ユーザーが組織内の Lync ユーザーと通信できるようにするには、フェデレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="464aa-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="464aa-111">パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="464aa-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="464aa-112">フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="464aa-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="464aa-113">![PIC の表示](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC の表示")</span><span class="sxs-lookup"><span data-stu-id="464aa-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="464aa-114">PIC フェデレーションは、Live Communications Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="464aa-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="464aa-115">PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。</span><span class="sxs-lookup"><span data-stu-id="464aa-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="464aa-116">2\.</span><span class="sxs-lookup"><span data-stu-id="464aa-116">2\.</span></span> <span data-ttu-id="464aa-117">フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="464aa-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="464aa-118">Lync Server コントロールパネルを使用すると、管理者は1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="464aa-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="464aa-119">![ポリシー](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "ポリシー")</span><span class="sxs-lookup"><span data-stu-id="464aa-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="464aa-120">3\.</span><span class="sxs-lookup"><span data-stu-id="464aa-120">3\.</span></span> <span data-ttu-id="464aa-121">Lync の Skype PIC プロバイダー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="464aa-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="464aa-122">Lync Server 管理シェルを使用して、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="464aa-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="464aa-123">パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために少なくとも1つのポリシー (この手順の前の手順 2) を構成するまで、組織内の IM またはオーディオまたはビデオ会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="464aa-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="464aa-124">フェデレーションと PIC を構成するには、「」の「フェデレーションとパブリック IM 接続[http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)を有効または無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464aa-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="464aa-125">フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成するには、「」 [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)の「パブリックユーザーアクセスを制御するようにポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464aa-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="464aa-126">**既存の Messenger または Skype PIC プロバイダーを編集して Skype 用に構成するには**</span><span class="sxs-lookup"><span data-stu-id="464aa-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="464aa-127">Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="464aa-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="464aa-128">次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="464aa-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="464aa-129">環境に PIC プロバイダがなく、新しい PIC プロバイダを作成している場合は、 <STRONG>enable-cspublicprovider</STRONG>コマンドレットを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="464aa-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="464aa-130">Lync Server 2013 CU5 &amp; lync desktop Client in OFFICE 2013 SP1 では、NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、lync ユーザーが skype の連絡先を追加することによって、Microsoft 以外 @msn のドメインを識別して skype 形式にルーティングする必要がある状況を改善しました ()。</span><span class="sxs-lookup"><span data-stu-id="464aa-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="464aa-131">これらの新しい設定では、NameDecorationRoutingDomain (msn.com に設定する必要があります) の [Skype 連絡先の追加] ダイアログボックスで、ユーザーの入力を自動的に書式設定することができます (NameDecorationExcludedDomainList 内のドメインが含まれていない場合)。現時点では、msn.com、live.com、Hotmail.com、outlook.com) をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="464aa-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="464aa-132">Lync クライアントから、PIC プロバイダーとして Skype を選択し、Microsoft アカウントを指定して Skype クライアントを追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="464aa-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="464aa-133">また、Microsoft アカウントを使用して合併およびログインした Skype ユーザーは、Lync ユーザーに対して連絡先要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="464aa-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="464aa-134">Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464aa-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="464aa-135">Lync にクライアントを追加する方法の詳細については、「lync [Server 2013 でのエンドユーザーとしての lync 接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464aa-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="464aa-136">![Skype 連絡先を追加する](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype 連絡先を追加する")</span><span class="sxs-lookup"><span data-stu-id="464aa-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="464aa-137">ホストされるプロバイダーの変更の詳細については、「」の「ホストさ[http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)れた SIP フェデレーションプロバイダーを作成または編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="464aa-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="464aa-138">これで、サーバー上で実行する必要のある管理タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="464aa-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="464aa-139">これで、Lync と Skype の接続が設定されました。</span><span class="sxs-lookup"><span data-stu-id="464aa-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

