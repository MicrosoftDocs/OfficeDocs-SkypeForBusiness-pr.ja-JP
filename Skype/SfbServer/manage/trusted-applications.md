---
title: 信頼できるアプリケーションの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 信頼済みアプリケーションは、Skype for Business Server によって信頼される Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103163"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="260b6-103">Skype for Business Server で信頼できるアプリケーションを管理する</span><span class="sxs-lookup"><span data-stu-id="260b6-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="260b6-104">信頼 *済みアプリケーション* は、Skype for Business Server によって信頼される Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="260b6-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="260b6-105">UCMA アプリケーションの詳細については、「Unified Communications Managed API 3.0 Core SDK Documentation」を参照してください https://go.microsoft.com/fwlink/p/?linkId=210320 。</span><span class="sxs-lookup"><span data-stu-id="260b6-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="260b6-106">サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="260b6-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="260b6-107">この記事では、新しい信頼できるアプリケーション サーバーを構成し、信頼できるアプリケーションの一覧を表示し、信頼できるアプリケーション情報を表示する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="260b6-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="260b6-108">新しい信頼できるアプリケーション サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="260b6-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="260b6-109">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="260b6-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="260b6-110">トポロジ ビルダーの開始: [スタート] を **クリックし**、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server トポロジ ビルダー]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="260b6-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="260b6-111">[**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="260b6-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="260b6-112">[トポロジに **名前を付けて保存** ] ダイアログ ボックスで、使用するトポロジ ビルダー ファイルをクリックし、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="260b6-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="260b6-113">左側のウィンドウで、[信頼済みアプリケーション サーバー] を **右** クリックし、[新しい信頼されたアプリケーション プール **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="260b6-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="260b6-114">信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="260b6-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="260b6-115">[次 **ホップの選択] ページ** で、一覧から Skype for Business Server フロントエンド プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="260b6-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="260b6-116">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="260b6-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="260b6-117">トップ ノード **の Skype for Business Server** を選択し、[操作] メニューの [トポロジの公開]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="260b6-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="260b6-118">信頼 **済みアプリケーション プールが** 正常に作成され、正しいフロントエンド プールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="260b6-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="260b6-119">信頼できるアプリケーションの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="260b6-119">View a list of trusted applications</span></span>

<span data-ttu-id="260b6-120">Skype for Business Server コントロール パネルを使用して、Skype for Business Server 環境に展開した信頼できるアプリケーションの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="260b6-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="260b6-121">信頼済みアプリケーションは、Skype for Business Server によって信頼される Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="260b6-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="260b6-122">この信頼関係は、次の一覧に要約されます。</span><span class="sxs-lookup"><span data-stu-id="260b6-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="260b6-123">信頼されたアプリケーションは、Skype for Business Server による認証に対してチャレンジされません。</span><span class="sxs-lookup"><span data-stu-id="260b6-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="260b6-124">信頼済みアプリケーションは、Skype for Business Server によって SIP トランザクション、接続、またはボイス オーバー インターネット プロトコル (VoIP) 呼び出しに対して調整されません。</span><span class="sxs-lookup"><span data-stu-id="260b6-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="260b6-125">信頼されたアプリケーションは、任意のユーザーを偽装し、名簿に表示されることなく会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="260b6-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="260b6-126">信頼できるアプリケーションは、高可用性と回復性を備えています。</span><span class="sxs-lookup"><span data-stu-id="260b6-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="260b6-127">Skype for Business Server コントロール パネルでは、アプリケーションの名前、実行するプール、および使用するポートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="260b6-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="260b6-128">信頼できるアプリケーションの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="260b6-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="260b6-129">CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="260b6-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="260b6-130">Skype for Business Server で使用できる定義済みの管理役割の詳細については、「役割ベースのアクセス制御 [(RBAC)」を参照してください](../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="260b6-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="260b6-131">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="260b6-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="260b6-132">左側のナビゲーション バーで、[トポロジ] **をクリックし**、[信頼されたアプリケーション] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="260b6-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="260b6-133">[信頼できる **アプリケーション] ページ** で、必要に応じて列見出しをクリックしてアプリケーションを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="260b6-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="260b6-134">信頼できるアプリケーション情報の表示</span><span class="sxs-lookup"><span data-stu-id="260b6-134">View trusted application information</span></span>

<span data-ttu-id="260b6-135">信頼できるアプリケーションに関する情報を表示するには、Windows PowerShell **Get-CsTrustedApplication コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="260b6-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="260b6-136">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="260b6-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="260b6-137">信頼されたアプリケーションを表示するには</span><span class="sxs-lookup"><span data-stu-id="260b6-137">To view trusted applications</span></span>

<span data-ttu-id="260b6-138">信頼できるすべてのアプリケーションを表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="260b6-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="260b6-139">このコマンドは、信頼されたアプリケーションごとに次のような情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="260b6-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="260b6-140">詳細については、「[Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="260b6-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span></span>