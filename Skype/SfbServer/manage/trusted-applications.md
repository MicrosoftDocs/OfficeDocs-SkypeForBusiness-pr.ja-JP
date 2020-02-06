---
title: 信頼できるアプリケーションを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 信頼されたアプリケーションは、Skype for Business Server によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817078"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="d5aa2-103">Skype for Business Server で信頼済みアプリケーションを管理する</span><span class="sxs-lookup"><span data-stu-id="d5aa2-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="d5aa2-104">信頼された*アプリケーション*は、Skype For business Server によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (ucma) 3.0 コア SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="d5aa2-105">UCMA アプリケーションの詳細については、の「ユニファイドコミュニケーションマネージ API 3.0 Core http://go.microsoft.com/fwlink/p/?linkId=210320SDK ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="d5aa2-106">トポロジの公開、有効化、または無効化を成功させるには、サーバーの役割を追加または削除するときに、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="d5aa2-107">この記事では、新しい信頼できるアプリケーションサーバーを構成する方法、信頼されたアプリケーションの一覧を表示する方法、信頼されているアプリケーションの情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="d5aa2-108">新しい信頼できるアプリケーションサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="d5aa2-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="d5aa2-109">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d5aa2-110">トポロジビルダーを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="d5aa2-111">[**既存の展開からトポロジをダウンロード**] を選び、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="d5aa2-112">[名前を付け**てトポロジを保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="d5aa2-113">左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="d5aa2-114">信頼されているアプリケーションプールの**プール FQDN**を入力し、それが単一サーバーか複数サーバーかを選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="d5aa2-115">**[次ホップの選択**] ページで、一覧から [Skype For business Server のフロントエンドプール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="d5aa2-116">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="d5aa2-117">トップノードの**Skype For Business Server**を選び、[**操作**] メニューの [トポロジの**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="d5aa2-118">**信頼できるアプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="d5aa2-119">信頼できるアプリケーションの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="d5aa2-119">View a list of trusted applications</span></span>

<span data-ttu-id="d5aa2-120">Skype for Business Server コントロールパネルを使用して、Skype for business Server 環境に展開した信頼済みアプリケーションの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="d5aa2-121">信頼されたアプリケーションは、Skype for Business Server によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="d5aa2-122">この信頼関係は、次の一覧にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="d5aa2-123">信頼されたアプリケーションは、Skype for Business Server による認証の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="d5aa2-124">Skype for Business Server は、SIP トランザクション、接続または発信ボイスオーバーインターネットプロトコル (VoIP) 通話に対して、信頼されているアプリケーションを調整しません。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="d5aa2-125">信頼されたアプリケーションは、選手名簿に表示されることなく、任意のユーザーを偽装し、会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="d5aa2-126">信頼性の高いアプリケーションは、高可用性と回復性を備えています。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="d5aa2-127">Skype for Business Server コントロールパネルには、アプリケーションの名前、実行しているプール、および使用しているポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="d5aa2-128">信頼されているアプリケーションの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="d5aa2-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="d5aa2-129">CsServerAdministrator、CsAdministrator、CsHelpDesk、CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="d5aa2-130">Skype for Business Server で利用可能な定義済みの管理者ロールの詳細については、「[ロールベースのアクセス制御 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="d5aa2-131">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="d5aa2-132">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**信頼済みアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="d5aa2-133">[**信頼済みアプリケーション**] ページで、必要に応じて、アプリケーションを並べ替える列見出しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="d5aa2-134">信頼できるアプリケーション情報の表示</span><span class="sxs-lookup"><span data-stu-id="d5aa2-134">View trusted application information</span></span>

<span data-ttu-id="d5aa2-135">Windows PowerShell と**CsTrustedApplication**コマンドレットを使用して、信頼されているアプリケーションに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="d5aa2-136">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="d5aa2-137">信頼済みアプリケーションを表示するには</span><span class="sxs-lookup"><span data-stu-id="d5aa2-137">To view trusted applications</span></span>

<span data-ttu-id="d5aa2-138">すべての信頼済みアプリケーションを表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="d5aa2-139">このコマンドは、信頼されたアプリケーションごとに次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="d5aa2-140">詳細については、「 [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5aa2-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
