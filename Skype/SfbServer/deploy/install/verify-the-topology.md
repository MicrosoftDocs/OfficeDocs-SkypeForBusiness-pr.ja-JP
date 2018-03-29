---
title: Skype for Business Server 2015 でのトポロジの確認
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '概要: ビジネス サーバー トポロジの Skype を確認する方法を学習して、Active Directory サーバーが期待どおりに作業しています。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 983ecf8b78a12898d18f04f7ec5c26c5271cf79a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="verify-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="f4227-104">Skype for Business Server 2015 でのトポロジの確認</span><span class="sxs-lookup"><span data-stu-id="f4227-104">Verify the topology in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f4227-105">**の概要:**ビジネス サーバー トポロジの Skype を確認する方法について説明し、Active Directory サーバーが期待どおりに作業しています。</span><span class="sxs-lookup"><span data-stu-id="f4227-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="f4227-106">[マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からサーバー 2015 をビジネス用には、Skype の無料試用版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f4227-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="f4227-107">公開トポロジは、トポロジ内のサーバーのそれぞれにインストールされているサーバーのビジネス システムのコンポーネントの Skype がある場合は後に、、トポロジが正常に動作していることを確認する準備が整ったら。</span><span class="sxs-lookup"><span data-stu-id="f4227-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="f4227-108">これには、構成が伝達されているすべての Active Directory サーバーにドメイン全体のビジネス用の Skype は、ドメインでは使用が認識できるように確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4227-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="f4227-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4227-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="f4227-110">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4227-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="f4227-111">トポロジの確認は 8 つの手順の 8 番目です。</span><span class="sxs-lookup"><span data-stu-id="f4227-111">Verifying the topology is step 8 of 8.</span></span>
  
![概要図](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="f4227-113">フロントエンド プール展開をテストする</span><span class="sxs-lookup"><span data-stu-id="f4227-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="f4227-114">最後に、フロント エンド プールをテストし、ビジネス クライアント用の Skype が互いに通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4227-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="f4227-115">ユーザーを追加してクライアント接続を確認する</span><span class="sxs-lookup"><span data-stu-id="f4227-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="f4227-116">(ビジネス サーバーのコントロール パネルの Skype がインストールされている) ビジネス サーバー展開の Skype の**CSAdministrator**グループに管理者の役割の Active Directory ユーザー オブジェクトを追加するのには、Active Directory のコンピューターとユーザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4227-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4227-117">CsAdministors グループに適切なユーザーとグループを追加しない場合、というビジネス サーバーのコントロール パネルの Skype を開くときに、エラーが表示されるが"権限がありません: 役割ベースのアクセス制御 (RBAC) の承認エラーのためアクセスが拒否されました."</span><span class="sxs-lookup"><span data-stu-id="f4227-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="f4227-118">ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてからもう一度ログオンし、新しいグループ割り当てを登録します。</span><span class="sxs-lookup"><span data-stu-id="f4227-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4227-119">ユーザー アカウントは、Skype をビジネスのサーバーを実行するサーバーのローカル管理者にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4227-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="f4227-120">ビジネス サーバーのコントロール パネルの Skype がインストールされているコンピューターにログオンする管理者アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4227-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="f4227-121">ビジネス サーバーのコントロール パネルでの Skype を起動し、求められた場合、資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f4227-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="f4227-122">Skype ビジネス サーバーのコントロール パネルの配置情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4227-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="f4227-123">左側のナビゲーション ・ バーでは、**トポロジ**をクリックし、し、サービスの状態が緑の矢印を持つコンピューターを表示し、レプリケーションの状態の緑のチェック マークが展開され、オンライン ビジネスのサーバー ロールの各 Skype の横にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4227-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="f4227-124">左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4227-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="f4227-125">**ビジネス サーバー ユーザーの Skype を新しい**ページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4227-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="f4227-p105">検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。[検索] オプションの内容を決定した後、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4227-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="f4227-129">[検索結果] ウィンドウで、追加するユーザーを選択して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4227-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="f4227-130">**ビジネス サーバー ユーザーの Skype を新しい**ページで、選択したユーザーは、**ユーザー**の表示には。</span><span class="sxs-lookup"><span data-stu-id="f4227-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="f4227-131">[**ユーザーのプールへの割り当て**] リストで、ユーザーの所属先となるサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4227-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="f4227-132">オブジェクトの構成に使用できるオプションの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f4227-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="f4227-133">**ユーザーの SIP URI を生成します。**</span><span class="sxs-lookup"><span data-stu-id="f4227-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="f4227-134">**テレフォニー**</span><span class="sxs-lookup"><span data-stu-id="f4227-134">**Telephony**</span></span>
    
    - <span data-ttu-id="f4227-135">**回線 URI**</span><span class="sxs-lookup"><span data-stu-id="f4227-135">**Line URI**</span></span>
    
    - <span data-ttu-id="f4227-136">**会議ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="f4227-137">**クライアント バージョン ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="f4227-138">**PIN ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="f4227-139">**外部アクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-139">**External access policy**</span></span>
    
    - <span data-ttu-id="f4227-140">**アーカイブ ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="f4227-141">**場所のポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-141">**Location policy**</span></span>
    
    - <span data-ttu-id="f4227-142">**クライアント ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f4227-142">**Client policy**</span></span>
    
    <span data-ttu-id="f4227-143">基本的な機能をテストするには、**生成ユーザーの SIP URI**の設定 (他のオプションで使用して既定の構成設定) を使用し、クリックする**を有効にする**には、図に示すようにオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4227-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![コントロール パネルでユーザーを有効にします。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="f4227-p107">概要ページが表示されます。このページの [**有効にする**] の列に、ユーザーが使用できることを示すチェック マークが表示されます。[**SIP アドレス**] の列に、ユーザーのサインインの構成に必要なアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4227-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Skype for Business Server コントロール パネルにユーザーが追加されました。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="f4227-148">あるユーザーはドメインに参加しているコンピューターにログオンし、他のユーザーはドメイン内の他のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4227-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="f4227-149">上の 2 つのクライアント コンピューターでは、それぞれのビジネス クライアント用の Skype をインストールし、両方のユーザーがビジネスのサーバーの Skype にサインインできるし、互いにインスタント メッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="f4227-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

