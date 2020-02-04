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
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="956d6-102">Lync Server 2013 での Lync と Skype の接続の有効化</span><span class="sxs-lookup"><span data-stu-id="956d6-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="956d6-103">_**最終更新日:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="956d6-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="956d6-104">プロビジョニング要求を送信した後は、Lync Server 環境と Lync-Skype の接続を構成するために必要な管理タスクに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="956d6-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="956d6-105">このセクションでは、Lync Server の管理者が Lync Server を展開し、外部アクセスを構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="956d6-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="956d6-106">Lync Server の外部アクセスの構成の詳細については、「 [lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956d6-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="956d6-107">Lync で lync を使用するための lync Server 環境を準備するには、Lync Server の管理者が次の3つの作業を完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="956d6-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="956d6-108">1 \.</span><span class="sxs-lookup"><span data-stu-id="956d6-108">1\.</span></span> <span data-ttu-id="956d6-109">フェデレーションと PIC を構成する</span><span class="sxs-lookup"><span data-stu-id="956d6-109">Configure Federation and PIC</span></span>

<span data-ttu-id="956d6-110">組織内の Lync ユーザーと Skype ユーザーとの通信を可能にするには、フェデレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="956d6-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="956d6-111">パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956d6-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="956d6-112">フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されています。</span><span class="sxs-lookup"><span data-stu-id="956d6-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="956d6-113">![PIC の表示](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC の表示")</span><span class="sxs-lookup"><span data-stu-id="956d6-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="956d6-114">PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="956d6-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="956d6-115">PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2 があります。</span><span class="sxs-lookup"><span data-stu-id="956d6-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="956d6-116">2 \.</span><span class="sxs-lookup"><span data-stu-id="956d6-116">2\.</span></span> <span data-ttu-id="956d6-117">フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="956d6-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="956d6-118">Lync Server コントロールパネルを使用して、管理者は、1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが社内の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956d6-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="956d6-119">![ポリシー](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "ポリシー")</span><span class="sxs-lookup"><span data-stu-id="956d6-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="956d6-120">3 \.</span><span class="sxs-lookup"><span data-stu-id="956d6-120">3\.</span></span> <span data-ttu-id="956d6-121">Lync の Skype PIC プロバイダー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="956d6-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="956d6-122">Lync Server 管理シェルを使用する場合、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956d6-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="956d6-123">パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順では、前の手順 2) を構成するまで、組織内の IM またはビデオ会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="956d6-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="956d6-124">フェデレーションと PIC を構成するには、で[http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)「フェデレーションとパブリック IM 接続を有効または無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956d6-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="956d6-125">フェデレーションさ[http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)れたユーザーアクセスをサポートするために、少なくとも1つのポリシーを構成するには、「パブリックユーザーアクセスを制御するためのポリシーの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956d6-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="956d6-126">**既存の Messenger または Skype PIC プロバイダーを編集して、Skype 用に設定するには**</span><span class="sxs-lookup"><span data-stu-id="956d6-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="956d6-127">Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="956d6-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="956d6-128">次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="956d6-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="956d6-129">環境に PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、 <STRONG>CsPublicProvider</STRONG>コマンドレットを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="956d6-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="956d6-130">Lync Server 2013 CU5 以降&amp; lync デスクトップクライアントに OFFICE 2013 SP1 で追加されました。 lync ユーザーが skype の連絡先を追加するには、Microsoft 以外のドメインを "装飾" して、skype (ユーザー (contoso) @msn の形式であることを確認し、ルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="956d6-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="956d6-131">こうした新しい設定により、ユーザーが [Skype 連絡先の追加] ダイアログ ボックスに入力したアドレスに NameDecorationExcludedDomainList のドメイン (現在は msn.com、live.com、Hotmail.com、outlook.com に対応できます) が含まれない場合は、このアドレスの NameDecorationRoutingDomain による自動書式設定 (msn.com に設定する必要があります) が可能になります。</span><span class="sxs-lookup"><span data-stu-id="956d6-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="956d6-132">Lync クライアントから、PIC プロバイダとして Skype を選択できるようになりました。 Skype クライアントを追加するには、お客様の Microsoft アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="956d6-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="956d6-133">さらに、Microsoft アカウントで統合してログインした Skype ユーザーは、連絡先要求を Lync ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="956d6-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="956d6-134">Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956d6-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="956d6-135">Lync にクライアントを追加する方法の詳細については、「lync を[使用したユーザーとしての Lync Server 2013 での lync の接続](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956d6-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="956d6-136">![Skype コンタクトを追加](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype コンタクトを追加")</span><span class="sxs-lookup"><span data-stu-id="956d6-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="956d6-137">ホストさ[http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)れているプロバイダーの変更の詳細については、の「ホステッド SIP フェデレーションプロバイダーを作成または編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956d6-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="956d6-138">これで、サーバー上で実行する必要がある管理タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="956d6-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="956d6-139">これで Lync と Skype の接続が設定されました。</span><span class="sxs-lookup"><span data-stu-id="956d6-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

