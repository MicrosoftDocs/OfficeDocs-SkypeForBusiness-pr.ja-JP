---
title: 信頼されたアプリケーションを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 信頼されたアプリケーションは、ビジネスのサーバーの Skype によって信頼されているマイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 のコア SDK に基づいてアプリケーションです。
ms.openlocfilehash: b4bad58d93ca231a9405734dd148cee675c5d1ea
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222892"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="13a7d-103">Skype のビジネス サーバー用の信頼されたアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="13a7d-104">の*信頼されたアプリケーション*は、ビジネスのサーバーの Skype によって信頼されているマイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 のコア SDK に基づいてアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="13a7d-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="13a7d-105">UCMA アプリケーションに関する詳細については、ある「ユニファイド コミュニケーション マネージ API 3.0 コア SDK ドキュメント」を参照してください。 http://go.microsoft.com/fwlink/p/?linkId=210320.</span><span class="sxs-lookup"><span data-stu-id="13a7d-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="13a7d-106">正常に発行を有効にするなどを追加するか、サーバーの役割を削除すると、トポロジを無効にする、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13a7d-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="13a7d-107">この資料を使用して、新しい信頼されたアプリケーション サーバーを構成する、信頼されたアプリケーションの一覧を表示および信頼されたアプリケーションの情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="13a7d-108">新しい信頼されたアプリケーション サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="13a7d-109">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="13a7d-110">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、 **Skype**、 **Skype**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="13a7d-111">**既存の展開からトポロジをダウンロード**するを選択し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="13a7d-112">**トポロジに名前を付けて**保存] ダイアログ ボックスで、トポロジ ビルダーを使用して、ファイルをクリックし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="13a7d-113">左側のウィンドウで**信頼済みアプリケーション サーバー**] を右クリックし、[**新しい信頼されたアプリケーション プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="13a7d-114">1 台のサーバーまたは複数のサーバーでは、され、[**次へ**] をクリックするかどうかは、[信頼されたアプリケーション プールの**プールの FQDN**を入力します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="13a7d-115">**次ホップの選択**] ページで、ボックスの一覧からビジネス サーバーのフロント エンド プールの Skype を選択します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="13a7d-116">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="13a7d-117">**Skype**ビジネス サーバーは、最上位のノードを選択し、**アクション**] メニューから **[トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="13a7d-118">**信頼されたアプリケーション プール**が正常に作成され、適切なフロント エンド プールに関連付けられているされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13a7d-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="13a7d-119">信頼されたアプリケーションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-119">View a list of trusted applications</span></span>

<span data-ttu-id="13a7d-120">ビジネス サーバーのコントロール パネルの Skype を使用するにはビジネスのサーバー環境に、Skype で展開している信頼されたアプリケーションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="13a7d-121">信頼されたアプリケーションは、ビジネスのサーバーの Skype によって信頼されているマイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 のコア SDK に基づいてアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="13a7d-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="13a7d-122">この信頼関係は、次の一覧に集約されます。</span><span class="sxs-lookup"><span data-stu-id="13a7d-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="13a7d-123">信頼されたアプリケーションない課題に直面して認証のため Skype ビジネス サーバーのです。</span><span class="sxs-lookup"><span data-stu-id="13a7d-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="13a7d-124">信頼されたアプリケーションは帯域が制限されない Skype によってビジネス サーバーの SIP トランザクション、接続、または発信の音声のインターネット プロトコル (VoIP) の呼び出しをします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="13a7d-125">信頼されたアプリケーションは、任意のユーザーを偽装することができ、名簿に表示されることがなく会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="13a7d-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="13a7d-126">信頼されたアプリケーションは、可用性と耐障害性です。</span><span class="sxs-lookup"><span data-stu-id="13a7d-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="13a7d-127">ビジネス サーバーのコントロール パネルの Skype では、アプリケーション、それらを実行している、プールを使用するポートの名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="13a7d-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="13a7d-128">信頼されたアプリケーションの一覧を表示するのには</span><span class="sxs-lookup"><span data-stu-id="13a7d-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="13a7d-129">CsServerAdministrator、CsAdministrator、CsHelpDesk、CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="13a7d-130">詳細については、Skype のビジネス サーバーで使用できる定義済みの管理者の役割は、[役割ベースのアクセス制御 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13a7d-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="13a7d-131">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="13a7d-132">左側のナビゲーション ・ バーでは、**トポロジ**をクリックし、**信頼されたアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="13a7d-133">[**信頼されたアプリケーション**] ページで、必要な場合、アプリケーションを並べ替えるには列見出しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="13a7d-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="13a7d-134">信頼されたアプリケーションの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-134">View trusted application information</span></span>

<span data-ttu-id="13a7d-135">Windows PowerShell と**Get CsTrustedApplication**コマンドレットを使用して、信頼されたアプリケーションに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="13a7d-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="13a7d-136">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="13a7d-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="13a7d-137">信頼されたアプリケーションを表示するのには</span><span class="sxs-lookup"><span data-stu-id="13a7d-137">To view trusted applications</span></span>

<span data-ttu-id="13a7d-138">すべての信頼されたアプリケーションを表示するに、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="13a7d-139">このコマンドは、信頼されたアプリケーションごとに次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="13a7d-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="13a7d-140">詳細については、 [Get CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13a7d-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>